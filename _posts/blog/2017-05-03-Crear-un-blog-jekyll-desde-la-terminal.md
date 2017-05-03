---
layout: page
title: "Crear un Blog Jekyll desde la Terminal"
date: 2017-05-03
tags: [jekyll, blog, terminal]
categories: jekyll
comments: true
---
Vamos a crear un Blog Jekyll desde la terminal, teniendo en cuenta que previamente hemos instalado tanto [Ruby como Jekyll.](/Instalar-Ruby-y-Jekyll/)  

Primero creamos la carpeta donde depositaremos el Blog  

```
sudo mkdir blog
```
Ahora crearemos el blog por defecto en Jekyll  

```
jekyll new blog
```
Si tuvieramos un blog guardado en zip, ahora lo descomprimiriamos y copiariamos:
* indice.html, CNAME y la carpeta _posts

Ahora entramos dentro de la carpeta blog y ejecutariamos:
```
jekyll serve
```
Si funciona correctamente, ya podemos subirlo a GiHub.

---

Recordar que si queremos cambiar el puerto por defecto a otro (ejem: 4003), deberiamos ejecutad:
```
jekyll serve --ports 4003
```
Para poder acceder desde otro dispositivo dentro de nuestra red local, debemos especificar la ip del dispositivo (ejem:192.168.1.100):  
```
jekyll serve --host 192.168.1.100
```
<!-- TAGS Y COMENTARIOS -->

Tags: {% assign sorted_tags = page.tags | sort %} {% for tag in sorted_tags %} , <span class="tag"><a href="/search#{{ tag }}">{{ tag }}</a></span> {% endfor %},



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
