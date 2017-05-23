---
layout: page
title: "Crear el Feed para el podcast en tu Blog con Jekyll"
date: 2017-04-24
tags: [jekyll, blog, feed, podcast]
categories: jekyll
comments: true
---
#### Publicado por Angel

Tags: {% assign sorted_tags = page.tags | sort %} {% for tag in sorted_tags %} , <span class="tag"><a href="/tag#{{ tag }}">{{ tag }}</a></span> {% endfor %},

Voy a explicar en este post, como generar el Feed del podcast de forma automática.

* Creamos un archivo `podcast.xml` en la raiz, con el siguiente contenido:

[Descargar archivo podcast.xml](https://ia601501.us.archive.org/32/items/podcast_20170424/podcast.xml)



* Añadimos en el archivo `_config.yml`, el siguiente contenido:

{% highlight ruby %}

# Podcast Feed Settings
podcast_url: https://ugeek.github.io
podcast_album_art: https://ugeek.github.io/img/ugeek.png
podcast_title: uGeek
podcast_owner: Angel
podcast_email: ugeekpodcast@gmail.com
podcast_category: Technology
podcast_subcategory_one: Linux
podcast_subcategory_two: Gadgets
podcast_explicit: "no"
podcast_author: Angel
podcast_description: Podcast de Tecnología en el que hablo de GNU/Linux, Raspberry Pi, servidores y tecnología en general.
podcast_summary: Podcast de Tecnología en el que hablo de GNU/Linux, Raspberry Pi, servidores y tecnología en general.
podcast_subtitle: Podcast de Tecnología en el que hablo de GNU/Linux, Raspberry Pi, servidores y tecnología en general.

{% endhighlight %}


* Por último, añadiremos en cada post, que es un podcast, el link del mp3, imagen, tags, etc...

{% highlight ruby %}

---
layout: post
title: "046. Sincronización de carpetas entre dispositivos. Syncthing, Resilio y Dukto"
date: 2017-04-21
categories: podcast
image: img/ugeek.png
podcast_link: https://ia601509.us.archive.org/6/items/046SyncthingResilioYDukto/%23046%20Syncthing%2c%20Resilio%20y%20Dukto%20.mp3
tags: [syncthing, resilio, dukto, sincronización carpetas, podcast]
comments: true
---

{% endhighlight %}

<!-- TAGS Y COMENTARIOS -->

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
