---
layout: post
title:  "Escaping Double Curly Braces In Markdown"
tags: Escape Markdown Jekyll
keywords: Escape Markdown Jekyll
description: How To Escape Double Curly Braces In Markdown
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

   {% for category in page.categories %} {{ category }} {% endfor %}

<h4>How To Escape Double Curly Braces In Markdown In Jekyll</h4>

If you need to add the next two lines of code using `markdown`

{% highlight html %}
{% raw %}this.page.url = "{{site.url}}{{page.url}}";{% endraw %}
{% raw %}this.page.identifier = "{{ page.id }}";{% endraw %}
{% endhighlight %}

The output will be:

{% highlight html %}
this.page.url = "{{site.url}}{{page.url}}";
this.page.identifier = "{{ page.id }}";
{% endhighlight %}

But how to `escape` the action of `double curly braces`, This can be done by putting your desired code between `{``%``raw``%``}` and `{``%``endraw``%``}`.

So, Putting `{``%``raw``%``}`"{% raw%}{{site.url}}{{page.url}}"{% endraw%}`{``%``endraw``%``}`

The output will be:

{% highlight html %}
<div id="disqus_thread"></div>
<script>
    var disqus_config = function () {
      this.page.url = {% raw %}"{{site.url}}{{page.url}}"{% endraw %};
      this.page.identifier = {% raw %}"{{ page.id }}"{% endraw %};
    };
</script>
{% endhighlight %}

Now, Take a look to this tutorial video.

<iframe width="100%" height="315" src="https://www.youtube.com/embed/TJzVxOKF_Xo" frameborder="0" allowfullscreen></iframe>