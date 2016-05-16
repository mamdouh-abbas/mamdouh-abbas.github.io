---
layout: post
title: "Rails With Mysql database, complete example"
keywords: ruby rails mysql database
tags: ruby rails mysql database
description: Tutorial video will guide you to install, create mysql database and create rails application using it, step by step tutorial guide.
published: true
---

TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

   {% for category in page.categories %} {{ category }} {% endfor %}

 <h3>1- Installing Mysql-server and Creating Database.</h3>

{% highlight ruby %}
sudo apt-get install mysql-server
{% endhighlight %}

Then log into mysql-server with root account:

{% highlight ruby %}
mysql -u root -p
{% endhighlight %}

Type root password and be ready to use mysql DSL.
First, you may need to determine that you will create more than one database, one for development environment, and one for test, and the third for production environment.

Here, We will create one for development only, and you can create the others.

{% highlight ruby %}
create database rails_dev;
{% endhighlight %}

You can see all mysql databases on system using:

{% highlight ruby %}
show databases;
{% endhighlight %}

Also, You need to create user rather than root:

{% highlight ruby %}
create user 'osama'@'localhost' identified by '123456789';
{% endhighlight %}

Then, Grant all privileges to this user

{% highlight ruby %}
grant all privileges on * . * to 'osama'@'localhost';
{% endhighlight %}

At this point, you have `database` name, `username` and `password`.

<hr>
<br>

<h3>2- Creating Rails Application With Mysql database.</h3>

{% highlight ruby %}
rails new auto --database=mysql
cd auto
subl .
{% endhighlight %}

The default database for rails is sqlite3, but we use `--database=mysql` to use mysql instead, so you will find ` gem 'mysql2'.

Note, If you change from sqlite3 to mysql, you need to make 

{% highlight ruby %}
bundle install
{% endhighlight %}

 to update `gemfile.lock` and install `mysql` gem if not installed.

Open `config/database.yml` and fill 

{% highlight ruby %}
  default: &default
  adapter: mysql2
  encoding: utf8
  pool: 5
  username: osama       #of mysql database created.
  password: 123456789   #of mysql database created.
  socket: /var/run/mysqld/mysqld.sock

development:
  <<: *default
  database: rails_dev   #of mysql database created.
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

<iframe width="100%" height="350" src="https://www.youtube.com/embed/YUfxiIscIyc" frameborder="0" allowfullscreen></iframe>











