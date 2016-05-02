---
layout: post
title:  "Migrating Specific VERSION Or STEP In Rails Migration"
tags: ruby rails migration database version step 
keywords: ruby rails migrate database version step
description: Migrating Specific VERSION Or STEP In Rails Migration Migration In Rails Application.
published: false
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

<h3>Migrating Specific VERSION Or STEP In Rails Migration.</h3>

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

<iframe width="100%" height="315" src="https://www.youtube.com/embed/jCC8nyBoC5E" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/A4DvaZ_lR0U" frameborder="0" allowfullscreen></iframe>

