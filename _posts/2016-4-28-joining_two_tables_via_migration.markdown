---
layout: post
title:  "Joining Two Tables Via Rails Migration"
tags: ruby rails migration database join 
keywords: ruby rails migrate database join
description: Tutorial video will guide you to Join two tables via Rails Migration.
published: true
---
   
   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

Related:
<ul>
<li><a href="/2016/04/28/adding_fields_to_table_via_migration.html">Adding fields to table via migration.</a></li>
<li><a href="/2016/04/28/creating_migrating_file_using_generate_migration.html">Creating migration file using generate migration</a></li>
<li><a href="/2016/04/28/creating_migrating_file_using_generating-_model.html">Creation migration file using generate model.</a></li>
<li><a href="/2016/04/28/creating_migrating_file_using_scaffold.html">Creating migration file using scaffold.</a></li>
<li><a href="/2016/04/28/drop_tables_using_migration.html">Drop tables using migration.</a></li>
<li><a href="/2016/04/28/editing_migration_manually.html">Editing migration file manually.<a></li>
<li><a href="/2016/04/28/seeding_tables_in_migration.html">Seeding data into tables via migration.</a></li>

<li><a href="/2016/04/28/migrating_specific_version_or_step.html">Migration specific VERSION or STEP.</a></li>
<li><a href="/2016/04/28/removing_fields_from_tables_via_migration.html">Removing fields from tables via migration.</a></li>
<li><a href="/2016/04/28/setting_rails_environment_via_migration.html">Setting rails environment via migration command.</a></li>
<li><a href="/2016/04/28/setup_reset_and_drop_database.html">Setup, reset and drop database</a></li>
</ul>

<br>
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
