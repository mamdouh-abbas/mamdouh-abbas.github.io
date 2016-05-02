---
layout: post
title: "Rails Exception Handler, Saving User Informations"
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
   <li><a href="/2016/04/22/Rails_Exception_Handler_complete_example_part2.html">Dealing With Missing Layout</a></li>
   <li><a href="/2016/04/22/Rails_Exception_Handler_complete_example_part3.html">Creating Exception Page</a></li>
   
 </ul>

<h4>How to save User Informations In `error_messages` table.</h4>

First, You must have one of the authentication methods such as devise.

Then, Uncomment the following line in `/config/initializers/rails_exception_handler.rb` and edit it to be:

{% highlight ruby %}
  config.store_user_info = {:method => :current_user, :field => :email} # Helper method for easier access to current_user
{% endhighlight %}

Where you will store the user `email` as user information into `ErrorMessage` table and we suppose that you use `current_user` as used in `devise`.

As shown in this tutorial video :

<iframe width="100%" height="350" src="https://www.youtube.com/embed/VZ5adC3Yi3E" frameborder="0" allowfullscreen></iframe>

<br>
<a target="_blank" href="https://github.com/mamdouh-abbas-farh/exception_handler" title="source on github">Source on github.com</a>

<i style="color:red;">Great Note</i>, Every time you change any file in `config/initializers`, You must restart `server`.
