---
layout: post
title:  "Accessing And Traversing Array Fields In Vews In Rails"
tags: Postgres Mysql Column Array Rails
keywords: Postgres Mysql Column Array Rails
description: How To Access And Traverse Array Fields In Vews In Rails
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

   {% for category in page.categories %} {{ category }} {% endfor %}

<h4>How To Access And Traverse Array Fields In Vews In Rails</h4>

In our example, We suppose that you watched our tutorials about <a href="/2016/03/31/Rails_With_postgres_database_complete_example.html">rails application with postgres database</a> or <a href="/2016/03/30/Rails_With_Mysql_database_complete_example.html">rails application with Mysql database</a> and <a href="/2016/04/30/adding_column_type_array_to_postgres_table_via_migration_only.html">adding column type array to postgres table via migration only</a> and <a href="/2016/04/30/adding_column_type_array_to_postgres_table_via_model_and_migration.html">adding column type array to postgres table via model and migration</a> and <a href="/2016/05/01/adding_column_type_array_to_mysql_table.html">adding column type array to mysql table</a>.

Then, You must add the `fields or columns` into `permited params` in our example `reader` and `editor` in the bottom of its `controller`, in our example `PostsController` as:

{% highlight ruby %}
def post_params
      params.require(:post).permit(:name, :comment,:reader,:editor)
    end
{% endhighlight %}

Then, Edit the `show` page to be like:

{% highlight ruby %}
<p id="notice"><%= notice %></p>

<p>
  <strong>Name:</strong>
  <%= @post.name %>
</p>

<p>
  <strong>Comment:</strong>
  <%= @post.comment %>
</p>
<p>
  <strong>Readers:</strong>
  
  <ol>
  	<% @post.reader.each do |reader| %>
  		<li><%= reader %></li>
  	<% end %>
  </ol>
</p>
<p>
  <strong>Editors:</strong>
  <ol>
  	<% @post.editor.each do |editor| %>
  		<li><%= editor %></li>
  	<% end %>
  </ol>
</p>

<%= link_to 'Edit', edit_post_path(@post) %> |
<%= link_to 'Back', posts_path %>
{% endhighlight %}

 Note, You can use full `array functions` in `ruby` with the `reader` and `editor` fields.

Now, Take a look to this tutorial video.

<iframe width="100%" height="315" src="https://www.youtube-nocookie.com/embed/vuJNhZB1DiU" frameborder="0" allowfullscreen></iframe>