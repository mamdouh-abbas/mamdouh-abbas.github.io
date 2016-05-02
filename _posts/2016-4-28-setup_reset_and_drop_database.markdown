---
layout: post
title:  "Setup, Reset And Drop Database"
tags: ruby rails migration database setup reset drop 
keywords: ruby rails migrate database setup reset drop
description: Setup, Reset And Drop Database In Rails Application.
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

<h3>Setup, Reset and Drop Database Via Rails Console.</h3>

Setting up the database using `rake db:setup` will create the database and migrate the migration files.

{% highlight ruby %}
rake db:setup
{% endhighlight %}

Also, Resetting the database using

{% highlight ruby %}
rake db:reset
{% endhighlight %}

will re-migrate the migration files.

But, Drop the database using 

{% highlight ruby %}
rake db:drop
{% endhighlight %}

will delete the the database itself.

Note, `rake db:reset` equals `rake db:drop db:setup`.
<iframe width="100%" height="315" src="https://www.youtube.com/embed/eQirPQNBy9Q" frameborder="0" allowfullscreen></iframe>
