---
layout: post
title: "Rails Exception Handler, complete example part 4"
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

<h4>8- How to save User Information In `error_messages` table.</h4>

As shown in this tutorial video :

<iframe width="100%" height="350" src="https://www.youtube.com/embed/VZ5adC3Yi3E" frameborder="0" allowfullscreen></iframe>
<br>

<i style="color:red;">Great Note</i>, Every time you change any file in `config/initializers`, You must restart `server`.
