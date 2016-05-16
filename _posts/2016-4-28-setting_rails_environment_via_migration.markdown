---
layout: post
title:  "Setting Environment For Rails Migration"
tags: ruby rails migration database environment
keywords: ruby rails migrate database environment
description: Tutorial video will guide you to Set environment for Rails Migration.
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
<li><a href="/2016/04/28/seeding_tables_in_migration.html">Seeding data into tables via migration.</a></li>
<li><a href="/2016/04/28/joining_two_tables_via_migration.html">Joining two tables via migration.</a></li>
<li><a href="/2016/04/28/migrating_specific_version_or_step.html">Migration specific VERSION or STEP.</a></li>
<li><a href="/2016/04/28/removing_fields_from_tables_via_migration.html">Removing fields from tables via migration.</a></li>
<li><a href="/2016/04/28/setting_rails_environment_via_migration.html">Setting rails environment via migration command.</a></li>
<li><a href="/2016/04/28/setup_reset_and_drop_database.html">Setup, reset and drop database</a></li>
</ul>

<br>
<h3>Setting Environment For Rails Migration.</h3>

You can set the `environment` for rails migration `RAILS_ENV` using one of two ways:

First, Using `rake` command line as:

{% highlight ruby %}
rake db:migrate RAILS_ENV=test
#or
rake db:migrate RAILS_ENV=development
#or
rake db:migrate RAILS_ENV=production
{% endhighlight %}

Second, Using system variables in command line

{% highlight ruby %}
export RAILS_ENV=test
#or
export RAILS_ENV=development
#or
export RAILS_ENV=production
{% endhighlight %}

Or editing `~/.bashrc` file to add `RAILS_ENV` as:

{% highlight ruby %}
echo 'RAILS_ENV=test' >> ~/.bashrc
#or
echo 'RAILS_ENV=test' >> ~/.bashrc
#or
echo 'RAILS_ENV=test' >> ~/.bashrc
{% endhighlight %}

And then, refresh your system variables using:

{% highlight ruby %}
source ~/.bashrc
{% endhighlight %}

You can assure that you have system variable `RAILS_ENV` and its value using :

{% highlight ruby %}
echo $RAILS_ENV
{% endhighlight %}

<i style="color:red;">Note, The database for that environment must be created before its migration.</i>

Now, Take a look to this tutorial video:

<iframe width="100%" height="315" src="https://www.youtube.com/embed/PcGxPKmmbE8" frameborder="0" allowfullscreen></iframe>

