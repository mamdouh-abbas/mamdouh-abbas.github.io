---
layout: post
title: "Rails Exception Handler, complete example part 1"
keywords: ruby rails exception error handler
tags: ruby rails exception handler
description: How to handle exceptions in your rails application using rails exception handler gem, step by step tutorial guide.
published: true
---

TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

   {% for category in page.categories %} {{ category }} {% endfor %}

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

All these steps in this tutorial video :

<iframe width="100%" height="350" src="https://www.youtube.com/embed/wZoroa-I23I" frameborder="0" allowfullscreen></iframe>

<i style="color:red;">Great Note</i>, Every time you change any file in `config/initializers`, You must restart `server`.
