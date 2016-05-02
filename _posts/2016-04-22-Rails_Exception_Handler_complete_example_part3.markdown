---
layout: post
title: "Rails Exception Handler, Creating Exceptions Page"
keywords: ruby rails exception error handler
tags: ruby rails exception handler
description: How to handle exceptions in your rails application using rails exception handler gem, step by step tutorial guide.
published: true
---

TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

   {% for category in page.categories %} {{ category }} {% endfor %}

 Series:

 <ul>
   <li><a href="/2016/04/22/Rails_Exception_Handler_complete_example_part1.html">Rails Exception Handler Gem</a></li>
   <li><a href="/2016/04/22/Rails_Exception_Handler_complete_example_part2.html">Dealing With Missing Layout</a></li>
   <li><a href="/2016/04/22/Rails_Exception_Handler_complete_example_part4.html">Storing User Information</a></li>
 </ul>

<h4>Creating View For Exceptions.</h4>

First, Assign all exceptions from the `ErrorMessage` model to an instance variable `@errors` in the posts controller to be accessed in `errors` page in views as:

{% highlight ruby %}
def errors
    @errors=ErrorMessage.all
end
{% endhighlight %}

Then, Make a route before `posts` to avoid `id` exception as:

{% highlight ruby %}
get "posts/errors"
root to: "posts#index"
resources :posts
{% endhighlight %}

Then, Create `views/errors.html.erb` and paste the next code and save.

{% highlight ruby %}
<h1>Errors</h1>
<table border="2">
  <tr>
  <% @errors.attribute_names.each do |key,value| %>
    <th>
      <%= key %>
    </th>
  <% end %>
  </tr>
  <% @errors.each do |error| %>
  <tr>
  <% error.attributes.each do |key,value| %>
    <td>

      <%= value  %>

    </td>
      <% end %>
  </tr>
    <% end %>
</table>
{% endhighlight %}

You can use any `paging` gem to handle large exceptions.

Now, Take a look to this tutorial video :

<iframe width="100%" height="350" src="https://www.youtube.com/embed/JCVsqGa0WZk" frameborder="0" allowfullscreen></iframe>

<br>
<a target="_blank" href="https://github.com/mamdouh-abbas-farh/exception_handler" title="source on github">Source on github.com</a>

<i style="color:red;">Great Note</i>, Every time you change any file in `config/initializers`, You must restart `server`.
