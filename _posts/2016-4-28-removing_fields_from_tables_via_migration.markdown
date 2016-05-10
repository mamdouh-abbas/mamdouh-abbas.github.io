---
layout: post
title:  "Removing Fields From Table via migration"
tags: ruby rails migration database add
keywords: ruby rails migrate database
description: How to remove fields from table via rails migration .
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
<li><a href="/2016/04/28/setting_rails_environment_via_migration.html">Setting rails environment via migration command.</a></li>
<li><a href="/2016/04/28/setup_reset_and_drop_database.html">Setup, reset and drop database</a></li>
</ul>


<br>
<h3>Removing Fields From Table Via Rails Migration.</h3>

First, We suppose that you have a `books` table as:

{% highlight ruby %}
rails g scaffold book name brief:text price:float
rake db:migrate
{% endhighlight %}

Now, You can remove the column `price` using:

{% highlight ruby %}
rails g migration RemovePriceFromBooks price:float
{% endhighlight %}

This mean, Remove price field from the books table, and will create a migration file as:

{% highlight ruby %}
class RemovePriceFromBooks<ActiveRecord::Migration
	def change
		remove_column :books, :price, :float
	end 
end
{% endhighlight %}

Then run 

{% highlight ruby %}
rake db:migrate
{% endhighlight %}

This will remove the `price` column form `books` table.

<i style="color:red">Take care,</i> The data stored in this field will be destoyed and can't be restored, So, What will happened if you run:

{% highlight ruby %}
rake db:rollback
{% endhighlight %}

<i style="color:red">Sure</i>, It will restore `price` field but not restore its `data`.

<iframe width="100%" height="315" src="https://www.youtube.com/embed/2cSW_dLK6Rs" frameborder="0" allowfullscreen></iframe>
<br>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/VUWfJfCUWYM" frameborder="0" allowfullscreen></iframe>
