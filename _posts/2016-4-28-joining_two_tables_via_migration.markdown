---
layout: post
title:  "Joining Two Tables Via Rails Migration"
tags: ruby rails migration database join 
keywords: ruby rails migrate database join
description: Joining Two Tables Via Rails Migration.
published: true
---
   
   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

<h3>Joining Two Tables Via Rails Migration.</h3>

First, We suppose that you have two tables at least.

In our example, we have `books` and `authors` tables, so we can join them using migration by adding `references` column which is author's `id` of the `book`.

Or in other word, each record in `books` has its author's `id` as:

{% highlight ruby %}
rails g migration AddAuthorRefToBooks author:references
{% endhighlight %}

This will generate a migration file to add this column as:

{% highlight ruby %}
class AddAuthorRefToBooks < ActiveRecord::Migration
  def change
    add_reference :books, :author, index: true, foreign_key: true
  end
end
{% endhighlight %}

Then, Apply changes to database using:

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

Note that you can undo this migration using:

{% highlight ruby %}
rake db:rollback
{% endhighlight %}

Now, You need to manually join these table via `model` by :

> 
>Adding `has_many :books` in the `author` model
>
>Adding `belongs_to :author` in the `book` model
>

In `models/author.rb`

{% highlight ruby %}
has_many :books
{% endhighlight %}

In `models/book.rb`

{% highlight ruby %}
belongs_to :author
{% endhighlight %}

Now, Take a look to this tutorial video:

<iframe width="100%" height="315" src="https://www.youtube.com/embed/DDQrRj_WQCc" frameborder="0" allowfullscreen></iframe>
