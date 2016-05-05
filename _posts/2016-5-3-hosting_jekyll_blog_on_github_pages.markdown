---
layout: post
title:  "Hosting Jekyll Blog On Github Pages"
tags: Hosting Jekyll Blog Github Pages
keywords: Hosting Jekyll Blog Github Pages
description: How To Host Jekyll Blog On Github Pages
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

   {% for category in page.categories %} {{ category }} {% endfor %}

<h4>How To Host Jekyll Blog On Github Pages.</h4>

First, You must create a new `repository` on you `github` account and provide its name as you `username` followed by `.github.io` i.e as `user_name.github.io`.

Second, Change directory to your blog and push you blog.

{% highlight ruby %}
git init
git remote add origin https://github.com/user_name/user_name.github.io.git
git add --all
git commit -m "first github pages"
git push -u origin master
{% endhighlight %}

Last, Browse to your `blog` url: `user_name.github.io`

Now, Take a look to this tutorial video.

<iframe width="100%" height="315" src="https://www.youtube-nocookie.com/embed/YdcZH4arUIc" frameborder="0" allowfullscreen></iframe>