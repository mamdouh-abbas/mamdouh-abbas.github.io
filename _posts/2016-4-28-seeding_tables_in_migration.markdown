---
layout: post
title:  "Seeding Tables Using Migration In Rails"
tags: ruby rails migration database 
keywords: ruby rails migrate database seed rollback
description: Seeding Tables Using Migration In Rails.
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

<h3>Seeding Tables Using Migration In Rails.</h3>

Before starting, We assumes that you have a table `authors` and its `model`, if not, you can do

{% highlight ruby %}
rails g scaffold author name
{% endhighlight %}

Seeding tables can be done by many ways:

Open `db/seeds.rb` and paste 

{% highlight ruby %}
5.times do |i|
Author.create(name: "John#{i}"
end
{% endhighlight %}

First, Using `rake db:setup` if the database not set, where `rake db:setup` creates the database and make migrations and seed data from `db/seeds.rb`.

Then, You can check the `authors` table using `console`.

Second, Using

{% highlight ruby %}
rake db:seed
{% endhighlight %}

Which insert `seeds` from `db/seeds.rb`.

Last, Using migration as

{% highlight ruby %}
rails g migration AddSeeds
{% endhighlight %}

This will create an empty migration file.
Then paste this seeding code:

{% highlight ruby %}
5.times do |i|
Author.create(name: "John#{i}"
end
{% endhighlight %}

Then, 

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

Also, You can check the `authors` data using `rails c` or `browser`

Note, You can delete these seeds using 

{% highlight ruby %}
rake db:rollback
{% endhighlight %}

Now, Take a look to this tutorial video:

<iframe width="100%" height="315" src="https://www.youtube.com/embed/0tE4oLlYv-k" frameborder="0" allowfullscreen></iframe>

<iframe width="100%" height="315" src="https://www.youtube.com/embed/QwU8XHriWCU" frameborder="0" allowfullscreen></iframe>
