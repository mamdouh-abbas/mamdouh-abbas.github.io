---
layout: post
title: "Rails Exception Handler, Exception Handler Gem"
keywords: ruby rails exception error handler
tags: ruby rails exception handler
description: How to handle exceptions in your rails application using rails exception handler gem, step by step tutorial guide.
published: true
---

TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

   {% for category in page.categories %} {{ category }} {% endfor %}

   Series:

<ul>
   <li><a href="/2016/04/22/Rails_Exception_Handler_complete_example_part2.html">Dealing With Missing Layout</a></li>
   <li><a href="/2016/04/22/Rails_Exception_Handler_complete_example_part3.html">Creating Exception Page</a></li>
   <li><a href="/2016/04/22/Rails_Exception_Handler_complete_example_part4.html">Storing User Information</a></li>
 </ul>

 <h4>1- Using Rails Exception Handler Gem.</h4>

 First, Add rails_exception_handler to Gemfile.

{% highlight ruby %}
gem 'rails_exception_handler', "~> 2"
{% endhighlight %}

Then, Make `bundle install`.

<h4>2- Generate an initializer.</h4>

{% highlight ruby %}
rails g rails_exception_handler:install
{% endhighlight %}

Open config/initializers/rails_exception_handler.rb, and choose the environments you want to handle exceptions with.

{% highlight ruby %}
config.environments = [:production, :test, :development]
{% endhighlight %}


Also, You can use another layout in the case of missing application layout using home layout in `views/layouts` or any other layout as `error` in our tutorial. 

{% highlight ruby %}
config.fallback_layout = 'error'
{% endhighlight %}

You can change the error message generated with exception as:

{% highlight ruby %}
config.responses = {
  :default => "<h1>500</h1><p>Internal server error</p>",
  :not_found => "<h1>Ops, The page you write is not found</h1><p>Page not found</p>"
}
{% endhighlight %}

Also, You can map the relation between the error type and the message related as:

{% highlight ruby %}
config.responses = {
    'ActiveRecord::RecordNotFound' => :not_found,
    'ActionController::RoutingError' => :not_found,
    'AbstractController::ActionNotFound' => :not_found
  }
{% endhighlight %}

<h4>3- Storing the exception</h4>

{% highlight ruby %}
config.storage_strategies = [:active_record]
 config.active_record_store_in = {
  :database => 'development', # Production in the production environment
  :record_table => 'error_messages' # The table name will be created.
 }
{% endhighlight %}

Note, We will create `error_messages` table in the same database.

Then, Create a migration file for `error_message` as :

{% highlight ruby %}
rails g migration error_message
{% endhighlight %}

Then, Edit the generated file to be :

{% highlight ruby %}
class ErrorMessages < ActiveRecord::Migration
  def change
     create_table :error_messages do |t|
      t.text :class_name
      t.text :message
      t.text :trace
      t.text :params
      t.text :target_url
      t.text :referer_url
      t.text :user_agent
      t.string :user_info
      t.string :app_name
      t.string :doc_root

      t.timestamps
    end
  end
end
{% endhighlight %}

Then, Make migration: 

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

<h4>4- Delete Error Pages From Public Folder.</h4>

This is `important` step.

You must delete or rename `404`,`422`,`500` error pages form public folder.

<h4>5- Create a Model To Deal With `error_message` Table .</h4>

In `app/model` folder create `error_message.rb` file and type:

{% highlight ruby %}
class ErrorMessage < ActiveRecord::Base
end
{% endhighlight %}

<h4>6-Storing Exceptions In Database.</h4>

First, You must decide if you will store exceptions into the save application database or in another database.

If you decided to store exceptoins in another database, then you have to create state that in `/config/database.yml`.

But, We will use our database in this tutorial, and `database.yml` as it is and the `/config/initializers/rails_exception_handler.rb` will be:

{% highlight ruby %}
RailsExceptionHandler.configure do |config|
  config.environments = [:development, :test, :production]                # Defaults to [:production]
  config.fallback_layout = 'error'                                         # Defaults to 'application'
  # config.after_initialize do
  #   # This block will be called after the initialization is done.
  #   # Usefull for interaction with authentication mechanisms, which should
  #   # only happen when the exception handler is enabled.
  # end
  # config.filters = [                                                      # No filters are  enabled by default
  #   :all_404s,
  #   :no_referer_404s,
  #   :anon_404s,
  #   {:user_agent_regxp => /\b(ApptusBot|TurnitinBot|DotBot|SiteBot)\b/i},
  #   {:target_url_regxp => /\.php/i},
  #   {:referer_url_regxp => /problematicreferer/i}
  # ]
  #
  # !!! IMPORTANT !!!
  # You must remove public/500.html and public/404.html for these to have any effect
  config.responses = {
    :default => "<h1>500</h1><p>Internal server error</p>",
    :not_found => "<h1>Ops, The page you write is not found</h1><p>Page not found</p>"
  }

  # All errors are mapped to the :default response unless overridden here
  config.response_mapping = {
    'ActiveRecord::RecordNotFound' => :not_found,
    'ActionController::RoutingError' => :not_found,
    'AbstractController::ActionNotFound' => :not_found
  }

  config.storage_strategies = [:active_record] # Available options: [:active_record, :rails_log, :remote_url => {:target => 'http://example.com'}]

  # Change database/table for the active_record storage strategy
  config.active_record_store_in = {
   :database => 'development', # your database is development in this example but must be `production` in production environment
   #and you must state the name if you will use another database.
   :record_table => 'error_messages' #the name of the table
  }


  config.store_request_info do |storage,request|
    storage[:target_url] =    request.url
    storage[:referer_url] =   request.referer
    storage[:params] =        request.params.inspect
    storage[:user_agent] =    request.user_agent
  end

  config.store_exception_info do |storage,exception|
    storage[:class_name] =   exception.class.to_s
    storage[:message] =      exception.to_s
    storage[:trace] =        exception.backtrace.join("\n")
  end

  config.store_environment_info do |storage,env|
    storage[:doc_root] =      env['DOCUMENT_ROOT']
  end

  config.store_global_info do |storage|
    storage[:app_name] =     Rails.application.class.parent_name
    storage[:created_at] =   Time.now
  end
  #config.store_user_info = {:method => :current_user, :field => :email} # Helper method for easier access to current_user
end

{% endhighlight %}

All these steps in this tutorial video :

<iframe width="100%" height="350" src="https://www.youtube.com/embed/wZoroa-I23I" frameborder="0" allowfullscreen></iframe>

<br>
<a target="_blank" href="https://github.com/mamdouh-abbas-farh/exception_handler" title="source on github">Source on github.com</a>

<i style="color:red;">Great Note</i>, Every time you change any file in `config/initializers`, You must restart `server`.
