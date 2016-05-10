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

{% include migration_related.html %}

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
