---
layout: post
title:  "Creating Migration File Via Rails Scaffold"
tags: ruby rails migration database 
keywords: ruby rails migrate scaffold database
description: Creating Migration File Via Rails Scaffold.
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

<h3>Creating Migration File Via Rails Scaffold.</h3>

Generating `scaffold` will create a migration file that create its table as:

{% highlight ruby %}
rails generate scaffold book title brief:text
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

Take a look to this tutorial video:

<iframe width="100%" height="315" src="https://www.youtube.com/embed/daFA4WPhaT4" frameborder="0" allowfullscreen></iframe>
