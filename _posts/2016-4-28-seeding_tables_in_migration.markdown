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

Related:
<ul>
<li><a href="/2016/04/28/adding_fields_to_table_via_migration.html">Adding fields to table via migration.</a></li>
<li><a href="/2016/04/28/creating_migrating_file_using_generate_migration.html">Creating migration file using generate migration</a></li>
<li><a href="/2016/04/28/creating_migrating_file_using_generating-_model.html">Creation migration file using generate model.</a></li>
<li><a href="/2016/04/28/creating_migrating_file_using_scaffold.html">Creating migration file using scaffold.</a></li>
<li><a href="/2016/04/28/drop_tables_using_migration.html">Drop tables using migration.</a></li>
<li><a href="/2016/04/28/editing_migration_manually.html">Editing migration file manually.<a></li>
<li><a href="/2016/04/28/joining_two_tables_via_migration.html">Joining two tables via migration.</a></li>
<li><a href="/2016/04/28/migrating_specific_version_or_step.html">Migration specific VERSION or STEP.</a></li>
<li><a href="/2016/04/28/removing_fields_from_tables_via_migration.html">Removing fields from tables via migration.</a></li>
<li><a href="/2016/04/28/setting_rails_environment_via_migration.html">Setting rails environment via migration command.</a></li>
<li><a href="/2016/04/28/setup_reset_and_drop_database.html">Setup, reset and drop database</a></li>
</ul>


<br>
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
