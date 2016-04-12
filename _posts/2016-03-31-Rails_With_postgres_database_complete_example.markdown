---
layout: post
title: "Rails With Postgresql database, complete example"
keywords: ruby rails postgres database
tags: ruby rails postgres database
description: How to install, create postgres database and create rails application using it, step by step tutorial guide.
published: true
---

TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

   {% for category in page.categories %} {{ category }} {% endfor %}

 <h3>1- Creating Postgresql Database.</h3>

First, log into postgres-server

{% highlight ruby %}
sudo su postgres -c psql
{% endhighlight %}

Type password and be ready to use postgresql DSL.
First, you may need to determine that you will create more than one database, one for development environment, and one for test, and the third for production environment.

Here, We will create one for development only, and you can create the others.

{% highlight ruby %}
create database rails_dev;
{% endhighlight %}

Type password and be ready to use postgres DSL.
First, Create you may need to determine that you will create more than one database, one for development environment, and one for test, and the third for production environment.

Here, We will create one for development only, and you can create the others.

{% highlight ruby %}
create database rails_dev;
{% endhighlight %}

Also, You need to create user:

{% highlight ruby %}
create user osama with password '123456789';
{% endhighlight %}

Then, Grant all privileges to this user

{% highlight ruby %}
grant all privileges on database rails_dev to osama;
{% endhighlight %}

At this point, you have `database` name, `username` and `password`.

<hr>
<br>

<h3>2- Creating Rails Application With Postgresql database.</h3>

{% highlight ruby %}
rails new auto --database=postgresql
cd auto
subl .
{% endhighlight %}

The default database for rails is sqlite3, but we use `--database=postgresql` to use postgres instead, so you will find ` gem 'pg'.

Note, If you change from sqlite3 to postgres, you need to make 

{% highlight ruby %}
bundle install
{% endhighlight %}

 to update `gemfile.lock` and install `pg` gem if not installed.

Open `config/database.yml` and fill 

{% highlight ruby %}
  default: &default
  adapter: postgresql
  encoding: unicode
  port: 5432
  username: osama
  password: 123456789
  pool: 5

development:
  <<: *default
  database: rails_dev
{% endhighlight %}

Now, Create you posts using `scaffold` :

{% highlight ruby %}
rails g scaffold post name comment:text
{% endhighlight %}

And then, Make `migration` to create the posts table in the database it self.

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

Last, Fire up you rails server:

{% highlight ruby %}
rails s
{% endhighlight %}

Now, ready to browse to `localhost:3000/posts` and process all `CRUD` operations.

All these steps in this tutorial video :

<iframe width="100%" height="350" src="https://www.youtube.com/embed/-ajUunAwezo" frameborder="0" allowfullscreen></iframe>











