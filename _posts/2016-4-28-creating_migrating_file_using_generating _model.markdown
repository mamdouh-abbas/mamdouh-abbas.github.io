---
layout: post
title:  "Creating Migration File Via Generating Rails Model"
tags: ruby rails migration database 
keywords: ruby rails migrate database
description: Tutorial video will guide you to create Migration file via generating Rails Model.
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

Related:
<ul>
<li><a href="/2016/04/28/adding_fields_to_table_via_migration.html">Adding fields to table via migration.</a></li>
<li><a href="/2016/04/28/creating_migrating_file_using_generate_migration.html">Creating migration file using generate migration</a></li>
<li><a href="/2016/04/28/creating_migrating_file_using_scaffold.html">Creating migration file using scaffold.</a></li>
<li><a href="/2016/04/28/drop_tables_using_migration.html">Drop tables using migration.</a></li>
<li><a href="/2016/04/28/editing_migration_manually.html">Editing migration file manually.<a></li>
<li><a href="/2016/04/28/seeding_tables_in_migration.html">Seeding data into tables via migration.</a></li>
<li><a href="/2016/04/28/joining_two_tables_via_migration.html">Joining two tables via migration.</a></li>
<li><a href="/2016/04/28/migrating_specific_version_or_step.html">Migration specific VERSION or STEP.</a></li>
<li><a href="/2016/04/28/removing_fields_from_tables_via_migration.html">Removing fields from tables via migration.</a></li>
<li><a href="/2016/04/28/setting_rails_environment_via_migration.html">Setting rails environment via migration command.</a></li>
<li><a href="/2016/04/28/setup_reset_and_drop_database.html">Setup, reset and drop database</a></li>
</ul>

<br>
<h3>Creating Migration File Via Generating Rails Model.</h3>

Generating model will create a migration file to create its table as

{% highlight ruby %}
rails generate model book title brief:text
{% endhighlight %}

This will generate a new file in db/migrate/(date-time stamp)_create_books.rb.

Then, Apply changes to database using:

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

Note that you can undo this migration using:

{% highlight ruby %}
rake db:rollback
{% endhighlight %}

Take a look to this tutorial video:

<iframe width="100%" height="315" src="https://www.youtube.com/embed/ck3LhvLtLZI" frameborder="0" allowfullscreen></iframe>
<br>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/UpsRsGvMRYA" frameborder="0" allowfullscreen></iframe>
