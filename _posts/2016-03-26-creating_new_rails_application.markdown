---
layout: post
title: "Creating a new Rails application"
tags: ruby on rails rails software 
keywords: ruby rails 
description: Starting a new Rails application and screencast.
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

First, We assume that you installed `Ruby`, you can know that using :

{% highlight ruby %}
ruby -v
{% endhighlight %}

Then, you need to install `Rails`:

{% highlight ruby %}
gem install rails
{% endhighlight %}

You can use  --no-ri --no-rdoc , for no gems documenation

{% highlight ruby %}
gem install rails --no-ri --no-rdoc
{% endhighlight %}

Also, you can know its version using :

{% highlight ruby %}
rails -v
{% endhighlight %}

Now, you are ready to `Rails`

> - Open a terminal
>
> - Go to the parent folder you want to build you application there.
>
> - Type the following line and press `Enter`.

{% highlight ruby %}
rails new autos
{% endhighlight %}

>
> - This will generate a directory called `autos` which contains the <a href="/2016/03/24/Directory_structure_in_rails">rails application directory structure</a>.
>
> - Change directory to `autos`.

{% highlight ruby %}
cd autos
{% endhighlight %}

>
> - Fire up the `rails server`.


{% highlight ruby %}
rails server 
or 
rails s
{% endhighlight %}

>
> - Then,browse to `localhost:3000`.
> - You will see this page:

<img src="/images/rails_welcome.png" alt="rails welcome page" title="rails welcome page">

Note that you can stop rails server using 

{% highlight ruby %}
ctrl + c
{% endhighlight %}

Also, Note that you don't need to restart rails server every time you make changes to you application as long as you are in development environment.

<iframe width="100%" height="350" src="https://www.youtube.com/embed/MMUMMAUTq_Y" frameborder="0" allowfullscreen></iframe>

<br>
<br>

Now, let's start our `autos` application:

First, we will use scaffolding to create cars controller, model, views, routes, test and database migration file in one line.

 {% highlight ruby %}
rails generate scaffold car brand:string year:integer
or
rails g scaffold car brand year:integer
{% endhighlight %}

This single line will create:

>
> `car` model
>
> `cars` controller
>
> `cars` views
>
> `cars` routes
>
> `cars` tests
>
> `cars` migration file
>

Then we need to create `cars` database table using :

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

This line will create the `cars` table and its database schema in `db/` folder, this table has two columns, one is brand with data type string and the other is year with data type integer.

Now, you are ready to browse you application and make `CRUD` operations;

`CRUD` means :

>
> `C` for `Create`
>
> `R` for `Read`
>
> `U` for `Update`
>
> `D` for `Delete`
>

Now, browse to `localhost:3000`, you will see the welcome page for rails application, so browse to `localhost:3000/cars` .

All these steps in the next tutorial video `You First Rails Application`

<iframe width="100%" height="350" src="https://www.youtube.com/embed/x3vgeGcrty8" frameborder="0" allowfullscreen></iframe>