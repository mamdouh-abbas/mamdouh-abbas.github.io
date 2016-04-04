---
layout: post
title: "Creating a new Rails application"
tags: ruby on rails rails software 
keywords: ruby rails 
description: Starting a new Rails application and screencast.
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

First, We assume that you installed `Ruby`, you can know that using :

{% highlight ruby %}
ruby --v
{% endhighlight %}

Then, you need to install `Rails`:

{% highlight ruby %}
gem install rails
{% endhighlight %}

You can use  --no-ri --no-rdoc , for no gems documenation

{% highlight ruby %}
gem install rails --no-ri --no-rdoc
{% endhighlight %}

Also, you can know its version using :

{% highlight ruby %}
rails --v
{% endhighlight %}

Now, you are ready to `Rails`

> 1. Open a terminal
>
> 2. Go to the parent folder you want to build you application there.
>
> 3. Type the following line and press `Enter`.

{% highlight ruby %}
rails new webalone
{% endhighlight %}

<!--

<iframe width="100%" height="350" src="http://www.youtube.com/embed/WO82PoAczTc" frameborder="0"> </iframe> 

-->
