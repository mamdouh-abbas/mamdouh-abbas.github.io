---
layout: post
title:  "Adding Disqus Comments To Jekyll Blog"
tags:  Jekyll Blog Comment Disqus
keywords: jekyll blog comment disqus
description: How To Add Disqus Comments To Jekyll Blog
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

   {% for category in page.categories %} {{ category }} {% endfor %}

<h4>How To Add Disqus Comments To Jekyll Blog</h4>

>
> Click the `setting ring` in the top right corner.
>
> Click `Add Disqus To Site`.
>
> Then, Click `Start Using Engage`.
>
> Enter the `site name`.
>
> Enter your disqus `unique url`.
>
> Choose the `category`.
>
> Click `Next`.
>
> Click `My site is just a personal site`.
>
> You can `Skip` next two step.
>
> Then, Choose `Universal Code`.
>
> Then `copy` the next code.
>

{% highlight html %}
<div id="disqus_thread"></div>
<script>
    var disqus_config = function () {
      this.page.url = {% raw %}"{{site.url}}{{page.url}}"{% endraw %};
      this.page.identifier = {% raw %}"{{ page.id }}"{% endraw %};
    };

    (function() {  // Replace your_unique_disqus_id with your true one.
        var d = document, s = d.createElement('script');
        
        s.src = '//your_unique_disqus_id.disqus.com/embed.js';
        
        s.setAttribute('data-timestamp', +new Date());
        (d.head || d.body).appendChild(s);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript" rel="nofollow">comments powered by Disqus.</a></noscript>
{% endhighlight %}

>
> And `paste` it in the `bottom` of the `_layouts/post.html`.
>
> Don't forget replacing `your_unique_disqus_id` with you actual one.
>
> Then `copy` the next code.
>

{% highlight html %}
<script id="dsq-count-scr" src="//your_unique_disqus_id.disqus.com/count.js" async></script> 
{% endhighlight %}

> And `paste` it in the `bottom` of the `_layouts/default.html` before `</body>`.
>
> Also don't forget replacing `your_unique_disqus_id` with you actual one.
>

Now, Take a look to this tutorial video.

<iframe width="100%" height="315" src="https://www.youtube.com/embed/uXiJmo2-XDg" frameborder="0" allowfullscreen></iframe>