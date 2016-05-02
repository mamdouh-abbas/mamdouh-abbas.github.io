---
layout: post
title:  "Removing Fields From Table via migration"
tags: ruby rails migration database add
keywords: ruby rails migrate database
description: Removing Fields From Table Via Rails Migration .
published: false
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

<h3>Removing Fields From Table Via Rails Migration.</h3>

<a href="/2016/4/28/adding_fields_to_table_via_migration.html">link</a>
<a href="/2016/04/28/creating_migrating_file_using_generate_migration.html">link</a>
<a href="/2016/04/28/creating_migrating_file_using_generating _model.html">link</a>
<a href="/2016/04/28/creating_migrating_file_using_scaffold.html">link</a>
<a href="/2016/04/28/drop_tables_using_migration.html">link</a>
<a href="/2016/04/28/editing_migration_manually.html">link</a>
<a href="/2016/04/28/seeding_tables_in_migration.html">link</a>
<a href="/2016/04/28/joining_two_tables_via_migration.html">link</a>
<a href="/2016/04/28/migrating_specific_version_or_step.html">link</a>
<a href="/2016/04/28/removing_fields_from_tables_via_migration.html">link</a>
<a href="/2016/04/28/setting_rails_environment_via_migration.html">link</a>
<a href="/2016/04/28/setup_reset_and_drop_database.html">link</a>

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

<iframe width="100%" height="315" src="https://www.youtube.com/embed/2cSW_dLK6Rs" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/VUWfJfCUWYM" frameborder="0" allowfullscreen></iframe>
