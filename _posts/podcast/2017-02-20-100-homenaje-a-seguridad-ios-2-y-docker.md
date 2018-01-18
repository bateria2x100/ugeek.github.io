---
id: 360
title: '#100 &#8211; Homenaje a&#8230;Seguridad IOS (2) Y Docker'
date: 2017-02-20T15:50:26+00:00
author: bateria2x100
layout: post
guid: https://www.bateria2x100.com/?p=360
permalink: /100-homenaje-a-seguridad-ios-2-y-docker/
enclosure:
  - https://www.bateria2x100.com/podcast/Bat2x100_100.mp3
categories:
  - Mac OSX
tags:
  - Podcast
---
<div class="powerpress_player" id="powerpress_player_5949">
  <audio class="wp-audio-shortcode" id="audio-360-102" preload="none" style="width: 100%;" controls="controls"><source type="audio/mpeg" src="https://www.bateria2x100.com/podcast/Bat2x100_100.mp3?_=102" /><a href="https://www.bateria2x100.com/podcast/Bat2x100_100.mp3">https://www.bateria2x100.com/podcast/Bat2x100_100.mp3</a></audio>
</div>

<p class="powerpress_links powerpress_links_mp3">
  Podcast: <a href="https://www.bateria2x100.com/podcast/Bat2x100_100.mp3" class="powerpress_link_pinw" target="_blank" title="Play in new window" onclick="return powerpress_pinw('https://www.bateria2x100.com/?powerpress_pinw=360-podcast');" rel="nofollow">Play in new window</a> | <a href="https://www.bateria2x100.com/podcast/Bat2x100_100.mp3" class="powerpress_link_d" title="Download" rel="nofollow" download="Bat2x100_100.mp3">Download</a>
</p>

<p class="powerpress_links powerpress_subscribe_links">
  Subscribe: <a href="https://subscribeonandroid.com/www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_android" title="Subscribe on Android" rel="nofollow">Android</a> | <a href="https://www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_rss" title="Subscribe via RSS" rel="nofollow">RSS</a>
</p>

Hoy hablaremos de :

Especial Seguridad (II)

AJUSTES -> PRIVACIDAD 
  
Podemos también limitar los cambios a la privacidad, es decir, podemos restringir para que si desactivamos aquellas apps que tienen acceso al carrete de fotos, no se puedan hacer más cambios, es decir, que no se pueda modificar ninguna app para que pueda tener acceso a las fotos. Si sabemos que apps pueden acceder a las fotos, y el niño instala una app que requiere el acceso a ellas, directamnete no le va a preguntar y le va a decri que NO, que no tiene acceso a las fotos. 
  
Otro aspecto importante sería el que encontramos en AJUSTES -> GENERAL -> RESTRICCIONES
  
Podemos hacer que no se puedan tocar las configuraciones de las cuentas, por ejemplo, para que no nosborren la config del correo, cuenta de linkedin, facebook, etc&#8230;
  
Limitar el volumen : También podemos limitar el volumen, para que el niño no se pueda dañar los oidos por ejemplo.
  
Otra opción : Game Center: Podemos activar o desactivar la opción de añadir amigos, juegos multijugaodr, grabar partidas&#8230;. de todo !

IOS está a tope de opciones para configurar la seguridad.

Si queréis algo más poderoso, ya que nos permitirá controlar algunas de estas opciones vía otro dispositivo :

<https://kidslox.com/en/> (es de suscripción, pero muy poderoso). Esta app la comentó Marc_intosh, al cual espero tener algún día en algún episodio.

Otra opción para niños :

## Dar acceso a una app, pero que el usuario no pueda salir de esta app. &#8211;> AJUSTES &#8211;>GENERAL &#8211;> ACCESIBILIDAD, a bajo de todo : APRENDIZAJE-> ACCESO GUIADO.

Qué es Docker ?

Los contenedores Docker envuelven un software en un sistema de archivos completo que contiene todo lo necesario para ejecutar: código, tiempo de ejecución, herramientas del sistema, bibliotecas del sistema, todo lo que se puede instalar en un servidor. Esto garantiza que el software siempre ejecutará el mismo, independientemente de su entorno.

Principales características :
  
LIGHTWEIGHT (pesan poco)
  
Containers running on a single machine share the same operating system kernel; they start instantly and use less RAM. Images are constructed from layered filesystems and share common files, making disk usage and image downloads much more efficient.
  
OPEN (abiertas)
  
Docker containers are based on open standards, enabling containers to run on all major Linux distributions and on Microsoft Windows &#8212; and on top of any infrastructure.
  
SECURE BY DEFAULT (seguras, ejecutan apps de forma totalmente aislada)
  
Containers isolate applications from one another and the underlying infrastructure, while providing an added layer of protection for the application.
  
Respecto a máq. virtuales : parecidas, pero pesan mucho menos, son por lo tanto más portables y eficientes, no consumen demasiada ram.

En Synology por ejemplo, por defecto vienen 2 repositorios de lo que llama Registro :

DockerHub
  
GitHub
  
Aquí podemos buscar por ejemplo : Nextcloud, wallabag, ubuntu,windows&#8230; lo que queramos.

Una vez descargada la imagen, la podemos iniciar, y es aquí donde se crea lo que llama contenedor, es decir, un &#8220;paquete&#8221; que será autoejecutable por si solo.

Siguiendo el ejemplo, nos podríamos descargar NExtcloud e iniciar la imagen, creando por ejemplo 2 contenedores, Next1 y Next2.

Cuando arrancamos estos contenedores, ahora qué ? 

Pues bien, eso ya depende. Lo usual es que estos &#8220;paquetes&#8221; lleven asociado un puerto, y epara verlas es tan fácil como abrir un navegador y atacar a la ip del NAS en el puerto que hayamos definido, o sea definido por la app.

Por ejemplo, en Synology para wallabag puedes definir el puerto en el 8000, entocnes, desde el navegador web, ip_NAS:8000 y podremos acceder a Wallabag.

A partir de aquí, con una config de Proxy inverso podríamos acceder a esta app de Wallabag a través de nuestro teléfono con protocolo https, u otra forma, utilizando VPN a través del puerto 8000. Una tercera vía sería abrir puertos en el router y acceder mediante el nombre de dominio de nuestro NAS, con el puerto 8000.

Como siempre :

Sed buenos !!

@bateria2x100
  
<https://www.bateria2x100.com>
  
<bateria2x100@gmail.com>