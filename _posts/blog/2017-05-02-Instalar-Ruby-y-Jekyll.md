---
layout: post
title: "Instalar Ruby y Jekyll"
date: 2017-05-02
tags: [jekyll, blog, ruby, antergos, ubuntu]
categories: jekyll
comments: true
---

Voy a explicar como instalar un blog de Jekyll para poder ejecutarlo en local y posteriormente, si lo desamos, subirlo a GitHub. Es muy importante trabajar en local y no hacerlo desde la interfaz web de GitHub, ya que el proceso de publicación, modificaciones..., es mucho mas lento y conduce a errores que nos van a crear muchos quebraderos de cabeza.  

Decir que me remito a Antergos y Ubuntu, pero en realidad es como decir derivadas de Arch Linux o Debian.  

Cada comando, irá separado por "/", que separa a la izquierda el comando de **Antergos** y a la derecha el de **Ubuntu**.  

**Antergos / Ubuntu**  

---  

Instalamos ruby  

```
sudo pacman -S ruby /  sudo apt install ruby
```

Ahora vamos a instalar un par de librerías de ruby  

```
gem install jekyll bundler / sudo gem install jekyll bundler
```

> **Solo en Antergos**  
Ahora te tienes que ir al fichero ~/.bashrc y pegar esta línea al final del fichero:

 ```
 PATH="$(ruby -e 'print Gem.user_dir')/bin:$PATH"
```  

Guarda y reinicia la terminal.

## Ejecutar el Blog en local

Ir al directorio raiz del proyecto ejecuta:  

```
jekyll serve
```

Si da error, ejecuta para instalar esa dependencia:

```
gem install jekyll-sitemap / sudo gem install jekyll-sitemap
```

vuelve a ejecutar:  

```
jekyll serve
```

Para acceder desde otro dispositivo dentro de nuestra red local, poniendo por ejemplo que el localhost o ip local de nuestro dispotivo es 192.168.1.100, ejecutar:  

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
