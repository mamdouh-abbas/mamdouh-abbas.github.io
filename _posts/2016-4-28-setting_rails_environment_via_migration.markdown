---
layout: post
title:  "Setting Environment For Rails Migration"
tags: ruby rails migration database environment
keywords: ruby rails migrate database environment
description: Setting Environment For Rails Migration.
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

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

