---
layout: page
title: "Crear un Blog Jekyll desde la Terminal"
date: 2017-05-03
tags: [github, blog, terminal]
categories: github
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
