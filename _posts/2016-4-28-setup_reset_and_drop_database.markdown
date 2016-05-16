---
layout: post
title:  "Setup, Reset And Drop Database"
tags: ruby rails migration database setup reset drop 
keywords: ruby rails migrate database setup reset drop
description: Tutorial video will guide you to Setup, Reset And Drop database in Rails application.
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
<li><a href="/2016/04/28/joining_two_tables_via_migration.html">Joining two tables via migration.</a></li>
<li><a href="/2016/04/28/migrating_specific_version_or_step.html">Migration specific VERSION or STEP.</a></li>
<li><a href="/2016/04/28/removing_fields_from_tables_via_migration.html">Removing fields from tables via migration.</a></li>
<li><a href="/2016/04/28/setting_rails_environment_via_migration.html">Setting rails environment via migration command.</a></li>
</ul>

<br>
<h3>Setup, Reset and Drop Database Via Rails Console.</h3>

Setting up the database using `rake db:setup` will create the database and migrate the migration files.

{% highlight ruby %}
rake db:setup
{% endhighlight %}

Also, Resetting the database using

{% highlight ruby %}
rake db:reset
{% endhighlight %}

will re-migrate the migration files.

But, Drop the database using 

{% highlight ruby %}
rake db:drop
{% endhighlight %}

This will delete the the database itself.
<br>
<i style="color:red">Note,</i> `rake db:reset` equals `rake db:drop db:setup`.

<br>

Now, Take a look to this tutorial video:

<iframe width="100%" height="315" src="https://www.youtube.com/embed/eQirPQNBy9Q" frameborder="0" allowfullscreen></iframe>
