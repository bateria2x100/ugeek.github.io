---
id: 495
title: '#130 &#8211; Worflow Avanzado (VII)'
date: 2017-05-03T23:01:47+00:00
author: bateria2x100
layout: post
guid: https://www.bateria2x100.com/?p=495
permalink: /130-worflow-avanzado-vii/
enclosure:
  - https://www.bateria2x100.com/podcast/Bat2x100_130.mp3
image: /wordpress/wp-content/uploads/2017/05/IMG_5766-1-400x372.jpeg
categories:
  - IOS
tags:
  - WORKFLOW
---
<div class="powerpress_player" id="powerpress_player_5979">
  <audio class="wp-audio-shortcode" id="audio-495-132" preload="none" style="width: 100%;" controls="controls"><source type="audio/mpeg" src="https://www.bateria2x100.com/podcast/Bat2x100_130.mp3?_=132" /><a href="https://www.bateria2x100.com/podcast/Bat2x100_130.mp3">https://www.bateria2x100.com/podcast/Bat2x100_130.mp3</a></audio>
</div>

<p class="powerpress_links powerpress_links_mp3">
  Podcast: <a href="https://www.bateria2x100.com/podcast/Bat2x100_130.mp3" class="powerpress_link_pinw" target="_blank" title="Play in new window" onclick="return powerpress_pinw('https://www.bateria2x100.com/?powerpress_pinw=495-podcast');" rel="nofollow">Play in new window</a> | <a href="https://www.bateria2x100.com/podcast/Bat2x100_130.mp3" class="powerpress_link_d" title="Download" rel="nofollow" download="Bat2x100_130.mp3">Download</a>
</p>

<p class="powerpress_links powerpress_subscribe_links">
  Subscribe: <a href="https://subscribeonandroid.com/www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_android" title="Subscribe on Android" rel="nofollow">Android</a> | <a href="https://www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_rss" title="Subscribe via RSS" rel="nofollow">RSS</a>
</p>

Worflow Avanzado (VII)

Como devolver una app :

<https://apple5x1.com/devolver-app-store/>

APP : [Annotable] 
  
(<https://www.macstories.net/reviews/annotable-20-adds-deep-customization-features/>)

[Skitch](https://itunes.apple.com/us/app/skitch-snap-mark-up-send/id490505997?mt=8)
  
[Annotate](https://itunes.apple.com/us/app/annotate-text-emoji-stickers-shapes-on-photos-screenshots/id994933038?mt=8)
  
[iMark](https://itunes.apple.com/us/app/imark-image-annotation-tool/id1174741369?mt=8)

Explicar un poco las magic variables :Nos facilitan un poco la vida ya que permiten &#8220;acortar&#8221; los WorkFlows, evitando tener que definir variables a las salidas de un bloque para poder recuperar ese valor. 

Aclarar :

  * Ficheros JSON como ficheros de configuración guardados en iCloud
  * API vs Esquemas URL

Consejos : 

Antes de bajar el WF, registraros en las APIS y obtened la clave, así cuando importéis el WF y os pregunte la API KEY, ya la tendréis.

Fijaos en la parte superior del WorfFlow, allí veréis que &#8220;This WorkFlow accepts&#8221; Images, por ejemplo, eso significa que lo ideal es ejecutar el WF desde, por jemplo, el camera Roll, de manera que pulsamos compartir y buscamos el &#8220;Run WorkFlow&#8221; que deberíais tener. (sino está, ya lo sabéis, a la derecha de todo, &#8220;more&#8221;, y lo activáis. Consejo, PONEDLO el PRIMERO !!!!

_Poder utilizar Google Maps en nuestro WorkFlow !_

Como primer plato, Google Maps !!! 
  
Si, aunque nuestros amigos de Apple se empeñan en que no lo usemos, podemos, a través de la API, tener acceso desde WorkFlow a las maravillas ocultas de Google :

Para obtener una API Key de Google maps :

[API](https://console.developers.google.com/flows/enableapi?apiid=maps_backend,geocoding_backend,directions_backend,distance_matrix_backend,elevation_backend,places_backend&reusekey=true)

Pero en este primer ejemplo No usaremos la API [Ruta Hacia con Google maps](https://workflow.is/workflows/256b929daf6349cb97359ee56815aa5f), sino que usaremos el la característica de x-callback-url para abrir Google Maps en IOS pasándole los parámetros de origen-destino. Vamos a aprovechar también el uso de iCloud como repositorio para tener un &#8220;fichero de configuración de la aplicación&#8221;. 

Aquí os dejo la documentación de Google al respecto : (<https://developers.google.com/maps/documentation/ios-sdk/urlscheme>)

El objetivo es que WF nos abra Google maps para ir a un destino habitual (u otro si queremos), y nos presentará las opciones que definamos en nuestro fichero de Config que guardaremos en iCloud y que nos puede evitar cambiar tropecientos Workflows que tengamos con nuestras localizaciones habituales.

El fichero es del tipo JSON :

{
  
&#8220;casa&#8221;:&#8221;mi+direccion+sin+espacios+usando+como+separador&#8221;,
  
&#8220;trabajo&#8221;:&#8221;segunda+direccion&#8221;,
  
&#8220;amante&#8221;:&#8221;no+es+buena+idea&#8221;
  
}
  
Este fichero, lo guardáis en iCloud como destinos.txt por ejemplo (**importante que sea .txt**)

**NOTA IMPORTANTE** Este mismo fichero **NO** sería válido para MAPAS de IOS ya que entonces no haría falta añadir &#8220;+&#8221; como separador. Si se añade, mapas de Apple no es capaz de entender la dirección.(os dejo el workflow equivalente : (<https://workflow.is/workflows/f41a2b0d2c8446d6a682ece793e412ba>)

El fichero debería ser así :
  
{
  
&#8220;casa&#8221;:&#8221;mi direccion&#8221;,
  
&#8220;trabajo&#8221;:&#8221;segunda direccion&#8221;,
  
&#8220;amante&#8221;:&#8221;Sigue siendo una mala idea&#8221;
  
}

1- El WorkFlow llama a [Sub_Destinos](https://workflow.is/workflows/b879c7b1d74c451597120d104882d958) y nos devolverá el JSON anterior.

2- A partir de aquí, te pregunta como irás (andando, coche, transporte público) y empieza la magia.

* * *

_Estación de Tren,Bus,Metro más cercana y como llegar_

[WF](https://workflow.is/workflows/8c21c876fc634d6f8a224ee40bd03d88)

Este segundo ejemplo es un poco más complejo, requiere de la API de Google Maps, y como su propio nombre describe, permite recibir las indicaciones a la estación de metro/bus, etc..más cercana. Disfrutadla ! !

La API de hoy :

  * [Google Maps](https://developers.google.com/maps/?hl=es-419)

_Tiempo hasta casa y mensaje por Telegram_

Seguimos.. Vamos a calcular el tiempo de llegada a casa, y además vamos a enviar a nuestra amada esposa un Telegram indicándolo. A día de hoy esta tarea se ha complicado mucho ya que WorkFlow no soporta Telegram, pero con un poco de maña&#8230;.

[Telegram](https://workflow.is/workflows/1475d3330d3e4d09b1bc3fc5a2962496)

Este WorkFlow es genérico, pero si cambiáis la selección de un contacto por el número deseado lo podéis personalizar más, o por ejemplo, con un fichero JSON de configuración como el que hemos visto se podría desplegar un menu con los 3 o 4 contactos más habituales para enviar este tipo de mensaje.

* * *

_Tiempo de llegada usando API de GMaps_

[Tiempo de llegada con GMaps](https://workflow.is/workflows/c0523fd7559e4c2b8df0a8b4b7a6cb41)

Ilustrativo para poder calcular la distancia en términos de tiempo hasta un lugar. Se puede hacer con mapas de Apple, pero también podemos seguir usando Google Maps ! 

Ejercicio&#8230; Fusionar ambos para poder calcular el tiempo de llegada a un destino habitual y enviar por Telegram o WhatsApp al destinatario Escogido.

Hoy además tocaremos imágenes ! 

2 WorkFlows :

  * Fácil : Redimensionar una imagen con las herramientas de la APP
  * Medio : Para los valientes, Optimizar una imagen mediante la API de (TinyPNG)[<https://tinypng.com/developers>] y que nos permite comprimir las imágenes con unos resultados más que buenos.

[WF1](https://workflow.is/workflows/1e119703ce234379b5e9e0e3128f4bc7)
  
[WF2](https://workflow.is/workflows/61428e6c9f1a4aed9095f01a3084325b)

Disfrutadlos.

Sed buenos !!

[@bateria2x100](https://Twitter.com/bateria2x100)
  
<https://www.bateria2x100.com>
  
<bateria2x100@gmail.com>

<table>
  <tr />
  
  <tr />
</table>

#podcast