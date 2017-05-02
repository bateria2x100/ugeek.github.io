---
layout: post
title: "Instalar Ruby y Jekyll"
date: 2017-05-02
tags: [jekyll, blog, ruby, antergos, ubuntu]
categories: jekyll
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

Tags: {% assign sorted_tags = page.tags | sort %} {% for tag in sorted_tags %} , <span class="tag"><a href="/search#{{ tag }}">{{ tag }}</a></span> {% endfor %},
