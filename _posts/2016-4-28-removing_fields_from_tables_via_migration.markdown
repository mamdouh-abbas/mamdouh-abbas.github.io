---
layout: post
title:  "Removing Fields From Table via migration"
tags: ruby rails migration database add
keywords: ruby rails migrate database
description: Removing Fields From Table Via Rails Migration .
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

<h3>1- Removing Fields From Table Via Rails Migration.</h3>

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

<iframe width="100%" height="315" src="https://www.youtube.com/embed/2cSW_dLK6Rs" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/VUWfJfCUWYM" frameborder="0" allowfullscreen></iframe>
