---
layout: post
title:  "Creating Migration File Via Generating Rails Model"
tags: ruby rails migration database 
keywords: ruby rails migrate database
description: reating Migration File Via Generating Rails Model.
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

<h3>1- reating Migration File Via Generating Rails Model.</h3>

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

<iframe width="100%" height="315" src="https://www.youtube.com/embed/ck3LhvLtLZI" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/UpsRsGvMRYA" frameborder="0" allowfullscreen></iframe>
