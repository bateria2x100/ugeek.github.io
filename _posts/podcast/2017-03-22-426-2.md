---
id: 426
title: '#115 &#8211; MisceláNASnea de miércoles !'
date: 2017-03-22T17:21:29+00:00
author: bateria2x100
layout: post
guid: http://www.bateria2x100.com/?p=426
permalink: /426-2/
enclosure:
  - |
    https://www.bateria2x100.com/podcast/Bat2x100_115.mp3
    21544968
    audio/mpeg
    a:1:{s:8:"duration";s:8:"00:26:26";}
categories:
  - IOS
---
<div class="powerpress_player" id="powerpress_player_5964">
  <audio class="wp-audio-shortcode" id="audio-426-117" preload="none" style="width: 100%;" controls="controls"><source type="audio/mpeg" src="https://www.bateria2x100.com/podcast/Bat2x100_115.mp3?_=117" /><a href="https://www.bateria2x100.com/podcast/Bat2x100_115.mp3">https://www.bateria2x100.com/podcast/Bat2x100_115.mp3</a></audio>
</div>

<p class="powerpress_links powerpress_links_mp3">
  Podcast: <a href="https://www.bateria2x100.com/podcast/Bat2x100_115.mp3" class="powerpress_link_pinw" target="_blank" title="Play in new window" onclick="return powerpress_pinw('https://www.bateria2x100.com/?powerpress_pinw=426-podcast');" rel="nofollow">Play in new window</a> | <a href="https://www.bateria2x100.com/podcast/Bat2x100_115.mp3" class="powerpress_link_d" title="Download" rel="nofollow" download="Bat2x100_115.mp3">Download</a>
</p>

<p class="powerpress_links powerpress_subscribe_links">
  Subscribe: <a href="https://subscribeonandroid.com/www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_android" title="Subscribe on Android" rel="nofollow">Android</a> | <a href="https://www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_rss" title="Subscribe via RSS" rel="nofollow">RSS</a>
</p>

Buenas ! Hoy día muy muy cargado :

Truco para Pocket y sus tags ( al guardar, aparece unos segundos en pantalla de IOS, si pulsas, puedes definir las etiquetas

**Idea** **Fustrada** : Pocket -> etiqueta salvar &#8211;> IFTTT regla que me lo pase a pdf (a poder ser limpio) y me lo ponga en una carpetad e Drive/amazon, de momento no sale, pero si alguien averigua cómo conseguirlo, que lo diga por favor !!

**NAS de SYNOLOGY**

Notificaciones de nuestro NAS a nuestro teléfono/dispositivos :

  1. Darse de alta en PushBullet <https://www.pushbullet.com> 
  2. Crear un token : 

<img src="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/03/word-image.png" class="wp-image-427" srcset="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/03/word-image.png 1504w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/03/word-image-300x156.png 300w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/03/word-image-768x400.png 768w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/03/word-image-1024x534.png 1024w" sizes="(max-width: 1504px) 100vw, 1504px" />

  1. Añadir el repositorio <https://www.cphub.net> en nuestro centro de paquetes 
  2. Instalar Notification Forwardeer y Notification Essentials (son dependientes, hay que instalar los 2 !) 
  3. Abrir Notification Forwarder y configurar : 

<img src="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/03/word-image-1.png" class="wp-image-428" srcset="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/03/word-image-1.png 1117w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/03/word-image-1-300x78.png 300w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/03/word-image-1-768x199.png 768w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/03/word-image-1-1024x266.png 1024w" sizes="(max-width: 1117px) 100vw, 1117px" />

Hay un botón de test para que podáis comprobar que funciona !

**MUMBLE &#8211; Servicio de VoIP privado :**

Para instalar UMurmur (servidor de Mumble) en nuestro Synology :

1 &#8211; Instalar :

<http://www.mertymade.com/syno/>

**Config File Editor**: Para editar tener que ir entrando por Telnet para configurar el fichero de config. Muy útil para varias cosas de nuestro NAS !

2 &#8211; Agregar el repositorio de Synnocomunity en el centro de paquetes-> Configuración -> Origenes del pquete

<http://packages.synocommunity.com>

3 &#8211; Instalar uMurmur

4 &#8211; Antes de arrancar el servicio :

Entrar en Config File Editor, Abajo de todo, seleccionar &#8220;config File Editor&#8221; y añadir :

/usr/local/umurmur/var/umurmur.conf, Umurmur

Entonces, reiniciar la aplicación y seleccionar uMurmur

Editar : linea 5 : Meter un password

Editar Linea 6: Meter otro password

Editar :# bindaddr = &#8220;IPLOCAL DEL_NAS&#8221;;

5 &#8211; Arrancar el uMurmur (no tiene interfaz de usuario)

6 &#8211; Recordad que hay que abrir el puerto en el Router ! !

Descargar la app de cliente ( mumble o mumblefy en IOS) , configurar y conectar !!!

Os dejo un link de youtube que lo explica también :

<https://www.youtube.com/watch?v=sS1PJHe3KYU>

Como siempre :

Sed buenos !!

@bateria2x100

https://www.bateria2x100.com

bateria2x100@gmail.com