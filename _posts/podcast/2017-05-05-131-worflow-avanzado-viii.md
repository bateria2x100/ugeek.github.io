---
id: 500
title: '#131 &#8211; Worflow Avanzado (VIII)'
date: 2017-05-05T16:46:52+00:00
author: bateria2x100
layout: post
guid: https://www.bateria2x100.com/?p=500
permalink: /131-worflow-avanzado-viii/
enclosure:
  - https://www.bateria2x100.com/podcast/Bat2x100_131.mp3
image: /wordpress/wp-content/uploads/2017/05/IMG_5766-2-400x372.jpeg
categories:
  - IOS
tags:
  - Ios
  - WORKFLOW
---
<div class="powerpress_player" id="powerpress_player_5980">
  <audio class="wp-audio-shortcode" id="audio-500-133" preload="none" style="width: 100%;" controls="controls"><source type="audio/mpeg" src="https://www.bateria2x100.com/podcast/Bat2x100_131.mp3?_=133" /><a href="https://www.bateria2x100.com/podcast/Bat2x100_131.mp3">https://www.bateria2x100.com/podcast/Bat2x100_131.mp3</a></audio>
</div>

<p class="powerpress_links powerpress_links_mp3">
  Podcast: <a href="https://www.bateria2x100.com/podcast/Bat2x100_131.mp3" class="powerpress_link_pinw" target="_blank" title="Play in new window" onclick="return powerpress_pinw('https://www.bateria2x100.com/?powerpress_pinw=500-podcast');" rel="nofollow">Play in new window</a> | <a href="https://www.bateria2x100.com/podcast/Bat2x100_131.mp3" class="powerpress_link_d" title="Download" rel="nofollow" download="Bat2x100_131.mp3">Download</a>
</p>

<p class="powerpress_links powerpress_subscribe_links">
  Subscribe: <a href="https://subscribeonandroid.com/www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_android" title="Subscribe on Android" rel="nofollow">Android</a> | <a href="https://www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_rss" title="Subscribe via RSS" rel="nofollow">RSS</a>
</p>

Worflow Avanzado (VIII)

  * [RCLONE](https://rclone.org/#) : Sin duda “la herramienta&#8221; para sincronizar NAS/NUBEs &#8230;

  * [BEAR](http://www.bear-writer.com/) : Una gran app de notas&#8230; con un teclado en IOS que añade unas teclas de función rápidas para poder escribir en markdown de una forma ágil. Un diseño espectacular, capacidad para exportar TODAS las notas, sincronización&#8230;etc&#8230;
  
    Soporte para imágenes, alta integración con WorkFlow ya que tiene definido el protocolo x-callback-URL, lo cual permite que workflow pueda &#8220;entenderse&#8221; muy bien con la app.

  * Posibilidad desde IOS en cualquier Web, a través de la extensión, de Exportar una página entera como nota en markdown. (**Espectacular**)

  * Desde las extensiones para Safari,Chrome o firefox permite también lo comentado en el punto anterior. 
  * Importar desde muchos formatos/apps(day one, vesper,evernote,etc)
  * Soporte para touch bar (nuevos macbook)
  * Capacidad de adjuntar ficheros a las notas
  * Etiquetas anidadas.
  * Búsqueda avanzada, con tags, operadores excluyentes&#8230;
  * Exportar las notas a varios formatos ! 
  * Configuración de fuentes, temas, espaciados&#8230;al más puro estilo Apple
  * Compatible con teclados externos bluetooth y con un amplio número de Atajos de teclado.
  * Se pueden lincar notas entre ellas.

Hablado con el desarrollador, me comenta que está trabajando en una versión Web&#8230; lo cual para mi sería casi definitivo para darle una oportunidad.

* * *

**Mercury Parser**

Resumen : 
  
2 WFs, el primero se ejecuta mejor desde Safari como extensión, recibe una URL y la parsea con la API de Mercury Parser. El segundo recibirá la info y la tratará, mostrando varias opciones para el usuario.

[WorkFlow1](https://workflow.is/workflows/2e612cfd04ff4f208bd34cd37318520a)
  
[WorkFlow2](https://workflow.is/workflows/9cb503cef39a4032ab83b8f2d672bcef)

Hoy usaremos otra API :
  
[Mercury Parser](https://mercury.postlight.com/web-parser/)

Una vez registrados y obtenido la API KEY, os podéis mirar como funciona su API y podremos hacer cosas como esta :

1- La idea es &#8220;parsear&#8221; una página de manera que la deje en lo mínimo para poder leerla. A modo ejmplo, lo que haremos será parsear la web, y además aprovechar que la API devuelve el título, un resumen y el documento parseado en si para pasarlo a un segundo WorkFlow y tratarlo según nos interese :

  * **Enviar por mail** : Donde veremos como enviar un mail con texto en el body y un adjunto a la vez. (Aprovechando el &#8220;Add to Variable&#8221;
  * **Guardar PDF en DropBox** : Esto es fácil, pero le cambiaremos el nombre para darle algún uso a la opción.
  * **Compartir PDF parseado por AirDrop** 
  * **Copiar PDF al portapapeles**.
  *  **Copiar texto parseado como texto al portapapeles**

<table>
  <tr />
  
  <tr />
</table>

Scanbot:
  
[WF](https://workflow.is/workflows/c4d28025462d4b42b0359ced22c3c5f5)
  
[Scanbot](https://support.scanbot.io/hc/en-us/articles/202383707-URL-Scheme-Support)

_Spark Mail_ 
  
[WF](https://workflow.is/workflows/be6f07234b4a4282bc889820ea7cbeed)

  * Abrir Spark
  * Abrir Spark en componer
  * Abrir Spark con destinatario y tema

_READDLE_
  
[WF](https://workflow.is/workflows/5121614a39854db3aa9a5624650644cf)

  * Documents
  * PDFEXPERT

_WHERE TO_
  
[WF](https://workflow.is/workflows/bf6eb953cb064eb9b686040f0b3137cf)

  * Buscar Restaurentes,metro, tren, Supermercados, Bancos,..

Varios URL Callbacks
  
[WF](https://workflow.is/workflows/bf6eb953cb064eb9b686040f0b3137cf)

_Simplenote_

  * Crear una nota con un tag

_Spotify_

  * Buscar algún artista

_TextExpander_

  * Crear una abreviatura

_1PASSWORD_

  * Buscar algún password.

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