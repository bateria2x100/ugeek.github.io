---
layout: page
title: "Crear un usb con una ISO de una distro"
date: 2017-05-23 21:36:00
tags: [blog, usb, pendrive, terminal]
categories: aplicaciones
comments: true
---
#### Publicado por Angel

![usb](/img/post/usb.png)

---
Averiguamos cual es el nombre de nuestro usb o pendrive con:  


```
lsblk
```


La primera parte es la iso ("nombre_de_la_iso.iso") y la segunda, la unidad de pendrive (/dev/sdb):   

```
sudo dd if=nombre_de_la_iso.iso of=/dev/sdb bs=4M
```

Esperamos y ya tendremos nuestro usb con la distro grabada y lista para ser instalada.
<!-- -------------------------------------Aquí abajo los comentarios -------------------------------------------  -->


{% endhighlight %}



Tags: {% assign sorted_tags = page.tags | sort %} {% for tag in sorted_tags %} , <span class="tag"><a href="https://ugeek.github.io/search#{{ tag }}">{{ tag }}</a></span> {% endfor %},



{% if page.comments %}
<div id="disqus_thread"></div>
<script>

/**
*  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
*  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/
/*
var disqus_config = function () {
this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = 'https://https-angelbcn-github-io-ugeek.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>


{% endif %}
