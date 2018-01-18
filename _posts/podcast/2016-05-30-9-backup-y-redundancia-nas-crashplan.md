---
id: 130
title: '#9 Backup y Redundancia (NAS) Crashplan'
date: 2016-05-30T07:58:02+00:00
author: bateria2x100
layout: post
guid: http://www.bateria2x100.com/?p=130
permalink: /9-backup-y-redundancia-nas-crashplan/
enclosure:
  - |
    http://www.bateria2x100.com/podcast/Bat2x100_09.mp3
    8582372
    audio/mpeg
    a:1:{s:8:"duration";s:8:"00:08:56";}
categories:
  - Uncategorized
---
<div class="powerpress_player" id="powerpress_player_5858">
  <audio class="wp-audio-shortcode" id="audio-130-11" preload="none" style="width: 100%;" controls="controls"><source type="audio/mpeg" src="http://www.bateria2x100.com/podcast/Bat2x100_09.mp3?_=11" /><a href="http://www.bateria2x100.com/podcast/Bat2x100_09.mp3">http://www.bateria2x100.com/podcast/Bat2x100_09.mp3</a></audio>
</div>

<p class="powerpress_links powerpress_links_mp3">
  Podcast: <a href="http://www.bateria2x100.com/podcast/Bat2x100_09.mp3" class="powerpress_link_pinw" target="_blank" title="Play in new window" onclick="return powerpress_pinw('https://www.bateria2x100.com/?powerpress_pinw=130-podcast');" rel="nofollow">Play in new window</a> | <a href="http://www.bateria2x100.com/podcast/Bat2x100_09.mp3" class="powerpress_link_d" title="Download" rel="nofollow" download="Bat2x100_09.mp3">Download</a>
</p>

<p class="powerpress_links powerpress_subscribe_links">
  Subscribe: <a href="https://subscribeonandroid.com/www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_android" title="Subscribe on Android" rel="nofollow">Android</a> | <a href="https://www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_rss" title="Subscribe via RSS" rel="nofollow">RSS</a>
</p>

Lunes!
  
Diferencia entre copia de seguridad y redundancia de datos. 

RAID no protege un archivo se elimine

RAID no protege de un archivo sea sobreescrito.

RAID no te protege de que su sistema se vea comprometido y todos sus datos se sobrescriban, sean borrados o dañados.

Los gurus dicen (Regla del 3-2-1) :

3 copias distintas
  
2 formatos fisicos distintos(en teoria disco a disco no cuenta!)
  
1 con un lugar físico distinto

CrashPlan en el NAS de Sinology ! :

1 &#8211; Instalar el paquete de CrashPlan no oficial del repositorio :

http://packages.pcloadletter.co.uk

2 &#8211; Configuración :

Abrir Terminal :
  
sudo nano /Applications/CrashPlan.app/Contents/Resources/Java/conf/ui.properties

Ahora estaos editando el fichero, eliminar # de la línea SERVICEHOST y cambiar 127.0.0.1 por la IP de nuestro NAS Synology. ^ X para salir y GRABAR pulsando Y

Ahora, entrar mediante SSH al NAS y ejecutar :

echo \`cat /var/lib/crashplan/.ui_info\` (OJO ! NO son comillas !!!, mejor copiar y pegar ! )

Aquí se nos mostrará una línea de texto,:

4243, y un Token, acabando con una IP.

Copiar el TOKEN al portapapeles.

Salir de SSH y modificar otro fichero haciendo : 

sudo nano &#8220;/Library/Application Support/CrashPlan/.ui_info&#8221;

Ahora sustituimos el TOKEN por el que hemos copiado antes, y salimos.

Debería estar hecho.

Comprobación :

Deberías poder abrir CrashPlan en el cliente MAC y en Settings, el nombre del NAS que será backupeado en CrashPlan !! 

Si ya tenías una máquina, debes ADOPTAR, así la máquina principal será ahora el NAS de Synology.

Saludos !