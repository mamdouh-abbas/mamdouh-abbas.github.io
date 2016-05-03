---
layout: post
title:  "Adding A Column Type Array To Postgres Database Table Via Migration Only"
tags: Postgres Column Array Rails
keywords: Postgres Column Array Rails
description: How To Add A Column Type Array To Postgres Database Table Via Migration Only
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

   {% for category in page.categories %} {{ category }} {% endfor %}

<h4>How To Add A Column Type Array To Postgres Database Table Via Migration Only</h4>

In our example, We suppose that you watched our tutorial about <a href="/2016/03/31/Rails_With_postgres_database_complete_example.html">rails application with postgres database</a>.

<h4>Creating Migration</h4>

First, We need to create a migration file to do our mission, Creating a column named reader type text as:

{% highlight ruby %}
rails g migration AddReaderToPosts reader:text
{% endhighlight %}

This will create a migration file like:

{% highlight ruby %}
class AddReaderToPosts < ActiveRecord::Migration
  def change
    add_column :posts, :reader, :text
  end
end
{% endhighlight %}

Edit it to be like:

{% highlight ruby %}
class AddReaderToPosts < ActiveRecord::Migration
  def change
    add_column :posts, :reader, :text,array: true, default:[]
  end
end
{% endhighlight %}

 Then make migrate as:

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

Now, You have a `reader` column which is an array, it can take many values as any array[`up to tons of tons ...].

And you can access the arry values in rails console as follow:

{% highlight ruby %}
a=Post.first
# push "Mamdouh"
a.reader << "Mamdouh"
# push "Ali"
a.reader << "Ali"
# push "Soso"
a.reader << "Soso"
# puts reader array values
a.reader
# traverse the reader array
a.reader.each do |x|
puts x
end
# get count
a.reader.count
# clear all values
a.reader.clear
{% endhighlight %}

Now, Take a look to this tutorial video.

<iframe width="100%" height="315" src="https://www.youtube.com/embed/qetZv-ZxFL8" frameborder="0" allowfullscreen></iframe>