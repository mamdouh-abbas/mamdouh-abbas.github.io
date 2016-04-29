---
layout: post
title: "Rails Exception Handler, complete example part 2" 
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

<h4>6- Dealing With `ErrorMessage` Model.</h4>

As shown in this tutorial video :

<iframe width="100%" height="350" src="https://www.youtube.com/embed/fHPkjvPq_sY" frameborder="0" allowfullscreen></iframe>

<i style="color:red;">Great Note</i>, Every time you change any file in `config/initializers`, You must restart `server`.
