---
id: 612
title: '#156 &#8211; Atentado en Barcelona y algo de tecnología.'
date: 2017-08-18T21:32:47+00:00
author: bateria2x100
layout: post
guid: https://www.bateria2x100.com/?p=612
permalink: /156-atentado-en-barcelona-y-algo-de-tecnologia/
enclosure:
  - https://www.bateria2x100.com/podcast/Bat2x100_156.m4a
image: /wordpress/wp-content/uploads/2017/08/IMG_6280.jpeg
categories:
  - NAS
tags:
  - Wordpress
---
<div class="powerpress_player" id="powerpress_player_6005">
  <audio class="wp-audio-shortcode" id="audio-612-158" preload="none" style="width: 100%;" controls="controls"><source type="audio/mpeg" src="https://www.bateria2x100.com/podcast/Bat2x100_156.m4a?_=158" /><a href="https://www.bateria2x100.com/podcast/Bat2x100_156.m4a">https://www.bateria2x100.com/podcast/Bat2x100_156.m4a</a></audio>
</div>

<p class="powerpress_links powerpress_links_m4a">
  Podcast: <a href="https://www.bateria2x100.com/podcast/Bat2x100_156.m4a" class="powerpress_link_pinw" target="_blank" title="Play in new window" onclick="return powerpress_pinw('https://www.bateria2x100.com/?powerpress_pinw=612-podcast');" rel="nofollow">Play in new window</a> | <a href="https://www.bateria2x100.com/podcast/Bat2x100_156.m4a" class="powerpress_link_d" title="Download" rel="nofollow" download="Bat2x100_156.m4a">Download</a>
</p>

<p class="powerpress_links powerpress_subscribe_links">
  Subscribe: <a href="https://subscribeonandroid.com/www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_android" title="Subscribe on Android" rel="nofollow">Android</a> | <a href="https://www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_rss" title="Subscribe via RSS" rel="nofollow">RSS</a>
</p>

# Atentado en Barcelona y algo de tecnología.

Crear carpeta “carpeta_ejemplo” en Web y asegurar que el usuario tiene permiso de ESCRITURA ! !

  * Descargar WordPress de WordPress.org y descomprimir en una carpeta de web en vuestro NAS (se presuponen los pasos iniciales que podéis ver en el tutirial que enlazo más abajo de jmRamirez)

  1. Editar elwp-config-sample.php

define(&#8216;DB_NAME&#8217;, &#8216;nassau&#8217;);

/*\* MySQL database username \*/
  
define(&#8216;DB\_USER&#8217;, ‘user\_name’);

/*\* MySQL database password \*/
  
define(&#8216;DB_PASSWORD&#8217;, ‘pasword’);

/*\* MySQL hostname \*/
  
define(&#8216;DB_HOST&#8217;, &#8216;localhost:/run/mysqld/mysqld10.sock&#8217;);

/*\* Database Charset to use in creating database tables. \*/
  
define(&#8216;DB_CHARSET&#8217;, &#8216;utf8&#8217;);

/*\* The Database Collate type. Don&#8217;t change this if in doubt. \*/
  
define(&#8216;DB_COLLATE&#8217;, &#8221;);

  1. Eliminar el “-sample”
  2. Eliminar las linias : 
  
    y añadir las que se generen con esta página :
  
    <https://api.wordpress.org/secret-key/1.1/salt/>

  3. Navegador : https://ip\_nas/carpeta\_ejemplo/wp-admin/install.php

  4. Añadir en wp-config : (para poder instalar tema, plugins) 
      * define(&#8216;FS_METHOD&#8217;, &#8216;direct&#8217;); 

* * *

<table>
  <tr />
  
  <tr />
</table>

  * Tuto de JM Ramirez para virtualización ligera de WordPress :
    
    [Virtualización ligera con Docker en un NAS de Synology](https://www.jmramirez.pro/tutorial/virtualizacion-ligera-con-docker/)

  * Tuto para crear una web con WordPress desde 0 muy útil (JM Ramírez)
    
      * [Como crear tu web en un NAS de Synology con WordPress](https://www.jmramirez.pro/tutorial/web-en-un-synology-con-wordpress/)
      * [Como crear tu web en un NAS de Synology con WordPress &#8211; YouTube](https://www.youtube.com/watch?time_continue=798&v=RheTjPXYWSI)

* * *

  * Enlace a la camiseta del podcast, es una forma de ayudar a este humilde podcaster a seguir !

<http://bit.ly/CamisetaBateria2x100>

* * *

Gracias a todos/as los que me dejáis una reseña en iTunes ! Y los que no TAMBIÉN !!!!!!!!

Sed buenos !!

[@bateria2x100](https://Twitter.com/bateria2x100)
  
<https://www.bateria2x100.com>
  
<bateria2x100@gmail.com>

#podcast/plantilla