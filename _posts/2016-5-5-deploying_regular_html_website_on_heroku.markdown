---
layout: post
title:  "Deploying Regular HTML Website On Heroku"
tags: Hosting Heroku Deploy
keywords: Hosting Heroku Deploy
description: How to deploy or host an HTML on heroku
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

   {% for category in page.categories %} {{ category }} {% endfor %}

<h4>How To Deploy A Regular HTML Website On Heroku.</h4>

The `Heroku` is one of the most pupular `PAAS` program as a service, and used for `server side application` so it suppose that you have a server side programming language such as `php`, `ruby`, `java` and so on.

So, For non server side application, we have a problem to deploy on `heroku`, but you can overcome it.

First, Change your `index.html` to be `home.html`.

Second, Create a new file `index.php` and type:

{% highlight php %}
<?php include_once("home.html"); ?>
{% endhighlight %}

And then, Deploy you site simply.

Now, Take a look to this tutorial video.

<iframe width="100%" height="315" src="https://www.youtube-nocookie.com/embed/jni52Hp7Cug" frameborder="0" allowfullscreen></iframe>