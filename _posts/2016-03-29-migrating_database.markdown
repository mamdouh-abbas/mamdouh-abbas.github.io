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

`Migrating Database`: After any changes on database in rails application using ruby code, you must assure that changes have been applied to the database it self, this is called `Migration`.

Or converting ruby code to build database tables, columns, properties, changes, and so on.

This can be done using `rake` or "ruby make" command.

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

This `migration` will do changes to database according to a file with a name of date-time stamp in `/db/migrate` folder as:

{% highlight ruby %}
20150522235057_create_cars.rb
{% endhighlight %}

This means that this file has been generated in 22/5/2015 (year month day)  at 11:50:57pm (hour minute seconds).

Ex: If you create rails application via scaffold, you must make migration to create the database tables as :

{% highlight ruby %}
rails generate scaffold cars brand:string year:integer
or
rails g scaffold cars brand year:integer 
{% endhighlight %}

This will generate a new file in db/migrate/(date-time stamp)_create_cars.rb.

Then after making migration as:

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

Note that you can undo this migration using 

{% highlight ruby %}
rake db:rollback
{% endhighlight %}
