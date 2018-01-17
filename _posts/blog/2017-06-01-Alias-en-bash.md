---
layout: page
title: "Alias en Bash. (.bashrc)"
date: 2017-06-01 21:30
tags: [blog, alias, bash, terminal]
categories: terminal
comments: true
---
#### Publicado por Angel

Alias .bashrc
-------------

Para crear un alias, una palabra que introduciremos en la terminal y
bash lo interpretará como una línea de comando, editaremos el archivo
/home/usuario/.bashrc.  
`sudo nano /home/usuario/.bashrc`

Al final del contenido de este archivo, iremos introduciendo los alias así:  
`alias palabra='comando'`

ejemplo:  
si añadimos esta línea en ubuntu, cada vez que escribamos en la
terminal, **actualizar**, se ejecutará los comandos para actualizar.  
`alias actualizar='sudo apt update && sudo apt upgrade && clear && echo
"Sistema Operativo Actualizado"'`

<!-- -------------------------------------Aquí abajo los comentarios -------------------------------------------  -->
Tags: {% assign sorted_tags = page.tags | sort %} {% for tag in sorted_tags %} , <span class="tag"><a href="/tag#{{ tag }}">{{ tag }}</a></span> {% endfor %},


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

<script id="dsq-count-scr" src="//https-angelbcn-github-io-ugeek.disqus.com/count.js" async></script>
