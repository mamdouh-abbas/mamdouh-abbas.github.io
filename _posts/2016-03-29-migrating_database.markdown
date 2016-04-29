---
layout: post
title:  "Migrating Database"
tags: ruby rails migration database 
keywords: ruby rails migrate database
description: Migrating database in rails application.
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

<h3>1- Creating Migrating File Using Scaffold.</h3>

`Migrating Database`: After any changes on database in rails application using ruby code, you must assure that changes have been applied to the database it self, this is called `Migration`.

Or converting ruby code to build database tables, columns, properties, changes, and so on.

This can be done using `rake` or "ruby make" command.

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

This `migration` will do changes to database according to a file with a name of date-time stamps in `/db/migrate` folder as:

{% highlight ruby %}
20150522235057_create_books.rb
{% endhighlight %}

This means that this file has been generated in 22/5/2015 (year month day)  at 11:50:57pm (hour minute seconds).

Ex: If you create rails application via scaffold, you must make migration to create the database tables as :

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

As shown in this tutorial video : 

<iframe width="100%" height="315" src="https://www.youtube.com/embed/daFA4WPhaT4" frameborder="0" allowfullscreen></iframe>
