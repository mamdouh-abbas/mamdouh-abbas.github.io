---
layout: post
title:  "Creating Migration File Via Generating Rails Migration"
tags: ruby rails migration database 
keywords: ruby rails migrate database
description: Creating Migration File Via Generating Migration In Rails Application.
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

<h3>1- Creating Migration File Via Generating Rails Migration.</h3>

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

<iframe width="100%" height="315" src="https://www.youtube.com/embed/RHJXsNd5vFo" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/2cSW_dLK6Rs" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/VUWfJfCUWYM" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/DDQrRj_WQCc" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/fq0fDJ_Tuko" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/jCC8nyBoC5E" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/A4DvaZ_lR0U" frameborder="0" allowfullscreen></iframe>

