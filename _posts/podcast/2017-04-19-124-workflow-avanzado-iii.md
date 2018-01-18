---
id: 469
title: '#124 &#8211; WorkFlow Avanzado (III)'
date: 2017-04-19T17:02:16+00:00
author: bateria2x100
layout: post
guid: https://www.bateria2x100.com/?p=469
permalink: /124-workflow-avanzado-iii/
enclosure:
  - https://www.bateria2x100.com/podcast/Bat2x100_124.mp3
image: /wordpress/wp-content/uploads/2017/04/IMG_5766-2-400x372.jpeg
categories:
  - IOS
tags:
  - Ios
  - WORKFLOW
---
<div class="powerpress_player" id="powerpress_player_5973">
  <audio class="wp-audio-shortcode" id="audio-469-126" preload="none" style="width: 100%;" controls="controls"><source type="audio/mpeg" src="https://www.bateria2x100.com/podcast/Bat2x100_124.mp3?_=126" /><a href="https://www.bateria2x100.com/podcast/Bat2x100_124.mp3">https://www.bateria2x100.com/podcast/Bat2x100_124.mp3</a></audio>
</div>

<p class="powerpress_links powerpress_links_mp3">
  Podcast: <a href="https://www.bateria2x100.com/podcast/Bat2x100_124.mp3" class="powerpress_link_pinw" target="_blank" title="Play in new window" onclick="return powerpress_pinw('https://www.bateria2x100.com/?powerpress_pinw=469-podcast');" rel="nofollow">Play in new window</a> | <a href="https://www.bateria2x100.com/podcast/Bat2x100_124.mp3" class="powerpress_link_d" title="Download" rel="nofollow" download="Bat2x100_124.mp3">Download</a>
</p>

<p class="powerpress_links powerpress_subscribe_links">
  Subscribe: <a href="https://subscribeonandroid.com/www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_android" title="Subscribe on Android" rel="nofollow">Android</a> | <a href="https://www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_rss" title="Subscribe via RSS" rel="nofollow">RSS</a>
</p>

WorkFlow Avanzado (III)
  
HyperBackUp : Están fallando las copias en Amazon Drive (<https://forum.synology.com/enu/viewtopic.php?f=268&t=130651>)

*Formato JSON
  
<https://www.copterlabs.com/json-what-it-is-how-it-works-how-to-use-it/>

*El robo/pérdida del iPhone 6 de mi mujer :
  
(<https://support.apple.com/es-us/HT201472>)

Y la app a la que hago referencia : (Life360)[<https://itunes.apple.com/us/app/find-my-family-friends-iphone-life360-locator/id384830320?mt=8>], una app que en conjunto con Piper nos permite saber si hay o no gente en casa para poder activar el modo “ausente” en el Piper. Además ha sido mucho más precis que &#8220;buscar mi iPhone&#8221; en cuanto a posicionamiento.

Os dejo un link al respecto del “miedo” a comerse la batería por el supo del GPS.
  
<http://venturebeat.com/2013/06/11/life360-battery/>

### Combinar PDFs

Este (WF)[<https://workflow.is/workflows/2633672cbbef42329928435039f5fd7e>] es más simple pero potente, nos permite descargar PDFs de DropBox y unirlos en un sólo PDF. Veréis que es simple pero potente.

Hoy seguiremos con el ejemplo anterior, y vamos a aprovechar que sabemos a que hora se pone el sol para crear 2 WF más :

1- Salir de Casa : Apagará las luces Wemo y Hue según la hora que sea, y activará el modo alarma de Piper
  
(<https://workflow.is/workflows/ab4f64526e5a42c2ad7ef2b2d831cfdd>)

2- Llegada a casa : Desactivará el modo Ausente de Piper
  
(<https://workflow.is/workflows/7d63f5b469f64d399688b545579324e3>)

Estos dos WorkFlows nos llevan antes a hablar de IFTTT.

IFTTT con Workflow nos abre un mundo nuevo, y permite ejecutar secuencias de acciones ya no de forma automática, sino cuando nosotros deseemos.

_SALIR DE CASA :_

  * Trigger IFTTT Applet (receta) : Aquí lo que permite es ejecutar un applet que préviamente tengamos definido en IFTTT. En este ejemplo, tenemos varios applets:

  * En el caso que falten menos de 30 minutos para la puesta de sol :

  * Dejar Encendida una luz que hay en un Interruptor Wemo

  * En el caso que falten más de 30 minutos para la puesta de sol (es de día aún) :
  * Apagar la luz Wemo
  * Apagar las luces HUE que haya encendidas.

_NOTA IMPORTANTE_: Recordar que hay que tener también un hábito creado en las luces Hue o una regla en Wemo para que cuando se ponga el sol se enciendan (si lo creéis conveniente claro)

Para el sorteo del próximo día 28/4 de 3 licencias del libro de @patuflinx :
  
**Recordad : Sorteo 3 licencias del libro (&#8220;Aprende y domina WorkFlow para IOS&#8221;)[https://itunes.apple.com/es/book/aprende-y-domina-workflow-para-ios/id1116817635?mt=11]**
  
&#8220;#&#8221;libroWorkFlow

Como siempre :

Sed buenos !!

[@bateria2x100](https://Twitter.com/bateria2x100)
  
<https://www.bateria2x100.com>
  
[&#98;&#x61;&#116;&#x65;&#114;i&#x61;&#50;&#x78;&#49;&#x30;&#48;&#x40;&#103;&#x6d;&#97;&#x69;&#108;.&#x63;&#111;&#x6d;](&#109;a&#x69;&#108;&#x74;&#111;&#x3a;&#98;&#x61;&#116;&#x65;&#114;i&#x61;&#50;&#x78;&#49;&#x30;&#48;&#x40;&#103;&#x6d;&#97;&#x69;&#108;.&#x63;&#111;&#x6d;)