---
id: 592
title: '#151 &#8211; Homebridge + Día de winners !!! Y &#8230;.'
date: 2017-07-13T10:16:03+00:00
author: bateria2x100
layout: post
guid: http://www.bateria2x100.com/?p=592
permalink: /151-homebridge-dia-winners/
enclosure:
  - |
    https://www.bateria2x100.com/podcast/Bat2x100_151.m4a
    7250704
    audio/x-m4a
categories:
  - IOS
---
<div class="powerpress_player" id="powerpress_player_6000">
  <audio class="wp-audio-shortcode" id="audio-592-153" preload="none" style="width: 100%;" controls="controls"><source type="audio/mpeg" src="https://www.bateria2x100.com/podcast/Bat2x100_151.m4a?_=153" /><a href="https://www.bateria2x100.com/podcast/Bat2x100_151.m4a">https://www.bateria2x100.com/podcast/Bat2x100_151.m4a</a></audio>
</div>

<p class="powerpress_links powerpress_links_m4a">
  Podcast: <a href="https://www.bateria2x100.com/podcast/Bat2x100_151.m4a" class="powerpress_link_pinw" target="_blank" title="Play in new window" onclick="return powerpress_pinw('https://www.bateria2x100.com/?powerpress_pinw=592-podcast');" rel="nofollow">Play in new window</a> | <a href="https://www.bateria2x100.com/podcast/Bat2x100_151.m4a" class="powerpress_link_d" title="Download" rel="nofollow" download="Bat2x100_151.m4a">Download</a>
</p>

<p class="powerpress_links powerpress_subscribe_links">
  Subscribe: <a href="https://subscribeonandroid.com/www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_android" title="Subscribe on Android" rel="nofollow">Android</a> | <a href="https://www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_rss" title="Subscribe via RSS" rel="nofollow">RSS</a>
</p>

Sorteos 

Ganadores licencias Resilio 

  *   * @raulbuenomolina 
      * @ivanpc 

Ganadores licencias Downie 

  *   * @\_vyck\_ 
      * @CacharreroGeek 

Y&#8230;.sorteo 2 licencias de la app para Mac **Waltr2** 

#loveWaltr2 

[WALTR 2. The all-new product](https://softorino.com/w2/)[.](https://softorino.com/w2/) 

**Sorteo hasta el viernes 28/7 a las 23:00 !!** 

Camisetas del podcast : 

<http://bit.ly/CamisetaBateria2x100> 

**INSTALAR HOMEBRIDGE EN NUESTRO SYNOLOGY** 

Después de instalar homebridge en el mac mini (ved la maravillosa entrada de @marc_instosh en <http://marcalonso.com/anadir-compatibilidad-homekit-accesorios-incompatibles-tipo-wemo/>) , y que habláramos con Osymar de instalarlo en el NAs, os trasncribo la info de una página que cito para poder correr himebridge desde nuestro Synology. 

La idea es instalar Homebridge a través de un Docker, y después añadir 2 ficheros de config. 

[Homebridge in a Docker Container on the Synology Diskstation Guide &#8211; Jens Boum](http://jensbouma.nl/blog/homebridge-in-a-docker-container-on-the-synology-diskstation-guide/)[a](http://jensbouma.nl/blog/homebridge-in-a-docker-container-on-the-synology-diskstation-guide/) 

<https://hub.docker.com/r/marcoraddatz/homebridge/> 

Crear ficheros 2 siguiendo el ejemplo y guardarlos en la ruta del NAS que hayamos destinado como Volumen en el Docker ( en mi ejemplo, Docker/Homebridge): 

<https://github.com/jensbouma/Homebridge-Synology-Diskstation/blob/master/sample.json> 

PASOS 

  1. Instalar Docker desde el Packet Manager de nuestro Synology 
  2. Descargar la imagen de “marcoraddatz-synology-homebridge” desde la app de Docker 
  3. Crear una carpeta &#8220;homebridge&#8221; en la carpeta compartida Docker de nuestro Nas. 
  4. Añadir los ficheros de configuración install.sh y config.json con los módulos que deseamos.Ved los ejemplos de ambos ficheros más abajo. 
  5. Arrancar la imagen y configurarla (capturas de <http://jensbouma.nl/blog/homebridge-in-a-docker-container-on-the-synology-diskstation-guide/:> 


<img src="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-4.png" class="wp-image-593" srcset="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-4.png 1334w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-4-300x258.png 300w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-4-768x660.png 768w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-4-1024x880.png 1024w" sizes="(max-width: 1334px) 100vw, 1334px" /> 


<img src="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-5.png" class="wp-image-594" srcset="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-5.png 1326w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-5-300x254.png 300w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-5-768x651.png 768w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-5-1024x868.png 1024w" sizes="(max-width: 1326px) 100vw, 1326px" /> 

En volumen añadir : 

_root_.homebridge y en Ruta de Montaje la carpeta compartida de vuestro NAS Docker/homebridge (por ejemplo) 


<img src="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-4.jpeg" class="wp-image-595" srcset="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-4.jpeg 1470w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-4-300x225.jpeg 300w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-4-768x576.jpeg 768w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-4-1024x768.jpeg 1024w" sizes="(max-width: 1470px) 100vw, 1470px" /> 

En Red marcar el check : 

Utilice la misma red que Docker Host 


<img src="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-5.jpeg" class="wp-image-596" srcset="https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-5.jpeg 1470w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-5-300x225.jpeg 300w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-5-768x576.jpeg 768w, https://www.bateria2x100.com/wordpress/wp-content/uploads/2017/07/word-image-5-1024x768.jpeg 1024w" sizes="(max-width: 1470px) 100vw, 1470px" /> 

Ahora se debería poder iniciar la imagen y en vuestro iphone, en la app &#8220;casa&#8221;, añadir accesorio (símbolo + arriba a la derecha) debería aparecer Homebridge !!!! 

**NOTA** : 

El install.sh una vez hagáis levantado el servico lo podéis renombrar para que si reiniciáis el servicio NO se vuelvan a descargar los paquetes. De todos modos, siempre va bien ya que si hay alguna update se os actualizará. 

package.json 

{ 

&#8220;bridge&#8221;: { 

&#8220;name&#8221;: &#8220;Homebridge is Working&#8221;, 

&#8220;username&#8221;: &#8220;CC:22:33:11:EE:77&#8221;, 

&#8220;port&#8221;: 51825, 

&#8220;pin&#8221;: &#8220;012-34-567&#8221; 

}, </p> 

&#8220;description&#8221;: &#8220;This is an example configuration file with all supported devices. You can use this as a template for creating your own configuration file containing devices you actually own.&#8221;, 

&#8220;platforms&#8221;: [ 

], 

&#8220;accessories&#8221;: [ 

] 

} 

install.sh (lo que está con “#” siginfica que está comentado, NO se ejectuta) 

#!/bin/sh 

npm install -g homebridge-platform-wemo 

#npm install -g homebridge-particle 

#npm install -g homebridge-http 

#npm install -g homebridge-evohome 

#npm install -g homebridge-ifttt 

#npm install -g homebridge-synology 

#npm install -g homebridge-better-http-rgb 

#npm install -g homebridge-http-securitysystem 

#npm install -g homebridge-server 

#npm install -g homebridge-ssh 

#npm install -g homebridge-suncalc 

Gracias a todos/as los que me dejáis una reseña en iTunes ! Y los que no TAMBIÉN !!!!!!!! 

Sed buenos !! 

[@bateria2x10](https://Twitter.com/bateria2x100)[](https://Twitter.com/bateria2x100) 

[https://www.bateria2x100.co](https://www.bateria2x100.com)[m](https://www.bateria2x100.com) 

[bateria2x100@gmail.co](mailto:bateria2x100@gmail.com)[m](mailto:bateria2x100@gmail.com) 

#podcast/plantilla