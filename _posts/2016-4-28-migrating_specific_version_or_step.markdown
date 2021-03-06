---
layout: post
title:  "Migrating Specific VERSION Or STEP In Rails Migration"
tags: ruby rails migration database version step 
keywords: ruby rails migrate database version step
description: Tutorial video will guide you to migrate specific VERSION or STEP in Rails Migration.
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

<li><a href="/2016/04/28/removing_fields_from_tables_via_migration.html">Removing fields from tables via migration.</a></li>
<li><a href="/2016/04/28/setting_rails_environment_via_migration.html">Setting rails environment via migration command.</a></li>
<li><a href="/2016/04/28/setup_reset_and_drop_database.html">Setup, reset and drop database</a></li>
</ul>

<br>
<h3>How To Migrate Specific VERSION Or STEP In Rails Migration.</h3>

First, We suppose that we have three models as:

{% highlight ruby %}
rails g model author name
rails g model book title brief:text
rails g model admin name
{% endhighlight %}

This means that we have three migration files for:

>
> author migration file.
>
> book migration file.
>
> admin migration file.
>

Each one of these files has its date-time stamps which is its `VERSION`.

The `author` migration is `STEP=1`.
The `book` migration is `STEP=2`..
The `admin` migration is `STEP=3`

If you run `rake db:migrate`, you will migrate all three file in the same sequence, But if you run `rake db:rollback`, you will `rollback` `one by one` in the `opposite` sequence.

But if you want to `migrate` or `rollback` specific `STEP` or `VERSION` you can use the following form: 

{% highlight ruby %}
rake db:migrate VERSION=xxxxxxxxxxxxxx
rake db:migrate STEP=x
or
rake db:rollback VERSION=xxxxxxxxxxxxxx
rake db:rollback STEP=x
{% endhighlight %}

Where `xxxxxxxxxxxxxx` is the `VERSION` of the desired migration file and `x` is the `index` of the desired migration file.

<i style="color:red;">Great Note:</i> You must be care with the `dependencies` between migration file also you may lost you data.

Now, Take a look to this tutorial videos:

<iframe width="100%" height="315" src="https://www.youtube.com/embed/jCC8nyBoC5E" frameborder="0" allowfullscreen></iframe>
<br>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/A4DvaZ_lR0U" frameborder="0" allowfullscreen></iframe>

