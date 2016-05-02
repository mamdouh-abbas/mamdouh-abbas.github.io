---
layout: post
title: "Rails Exception Handler, Dealing With Missing Layout" 
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
   <li><a href="/2016/04/22/Rails_Exception_Handler_complete_example_part1.html">Rails Exception Handler Gem</a></li>
   <li><a href="/2016/04/22/Rails_Exception_Handler_complete_example_part3.html">Creating Exception Page</a></li>
   <li><a href="/2016/04/22/Rails_Exception_Handler_complete_example_part4.html">Storing User Information</a></li>
 </ul>

<h4>Dealing with Missing Layout.</h4>

We know that the default error pages in the `public` folder has no layout, But in `rails exception handler` it uses layout, so What we can do if layout is missed.

For this reason, rails exception handler provide

 {% highlight ruby %}
#config.fallback_layout = 'home'
{% endhighlight %}

 in `/config/initializers/rails_exception_handler.rb`/

 Uncomment it and change `home` layout to be another one as `error` in our tutorial.

As shown in this tutorial video :

<iframe width="100%" height="350" src="https://www.youtube.com/embed/fHPkjvPq_sY" frameborder="0" allowfullscreen></iframe>

<br>
<a target="_blank" href="https://github.com/mamdouh-abbas-farh/exception_handler" title="source on github">Source on github.com</a>

<i style="color:red;">Great Note</i>, Every time you change any file in `config/initializers`, You must restart `server`.
