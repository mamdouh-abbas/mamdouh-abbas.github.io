---
layout: post
title:  "Setup, Reset and Drop Database Via Rails Console"
tags: ruby rails migration database setup reset drop 
keywords: ruby rails migrate database setup reset drop
description: Setup, Reset and Drop Database Via  Console in Rails Application.
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

<h3>1- Setup, Reset and Drop Database Via Rails Console.</h3>

{% highlight ruby %}
rails generate model book title brief:text
{% endhighlight %}

This will generate a new file in db/migrate/(date-time stamp)_create_books.rb.

Then, Apply changes to database using:

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

Note that you can undo this migration using:

{% highlight ruby %}
rake db:rollback
{% endhighlight %}

<iframe width="100%" height="315" src="https://www.youtube.com/embed/A4DvaZ_lR0U" frameborder="0" allowfullscreen></iframe>
