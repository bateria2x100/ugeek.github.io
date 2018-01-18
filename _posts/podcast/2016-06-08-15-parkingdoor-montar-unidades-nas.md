---
id: 142
title: '#15 ParkingDoor &#038; Montar Unidades NAS'
date: 2016-06-08T12:56:02+00:00
author: bateria2x100
layout: post
guid: http://www.bateria2x100.com/?p=142
permalink: /15-parkingdoor-montar-unidades-nas/
enclosure:
  - |
    http://www.bateria2x100.com/podcast/Bat2x100_15.mp3
    12421328
    audio/mpeg
    a:1:{s:8:"duration";s:8:"00:12:56";}
categories:
  - Uncategorized
---
<div class="powerpress_player" id="powerpress_player_5864">
  <audio class="wp-audio-shortcode" id="audio-142-17" preload="none" style="width: 100%;" controls="controls"><source type="audio/mpeg" src="http://www.bateria2x100.com/podcast/Bat2x100_15.mp3?_=17" /><a href="http://www.bateria2x100.com/podcast/Bat2x100_15.mp3">http://www.bateria2x100.com/podcast/Bat2x100_15.mp3</a></audio>
</div>

<p class="powerpress_links powerpress_links_mp3">
  Podcast: <a href="http://www.bateria2x100.com/podcast/Bat2x100_15.mp3" class="powerpress_link_pinw" target="_blank" title="Play in new window" onclick="return powerpress_pinw('https://www.bateria2x100.com/?powerpress_pinw=142-podcast');" rel="nofollow">Play in new window</a> | <a href="http://www.bateria2x100.com/podcast/Bat2x100_15.mp3" class="powerpress_link_d" title="Download" rel="nofollow" download="Bat2x100_15.mp3">Download</a>
</p>

<p class="powerpress_links powerpress_subscribe_links">
  Subscribe: <a href="https://subscribeonandroid.com/www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_android" title="Subscribe on Android" rel="nofollow">Android</a> | <a href="https://www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_rss" title="Subscribe via RSS" rel="nofollow">RSS</a>
</p>

Miércoles ! Vamos !
  
https://parkingdoor.com/

Montar unidades del NAS :

do shell script &#8220;if [ -d &#8216;/Volumes/NombreCarpetaCompartida&#8217; ]; then
  
diskutil unmount &#8216;/Volumes/NombreCarpetaCompartida&#8217;;
  
else
  
mkdir &#8216;/Volumes/home&#8217;;
  
mount -t afp &#8216;afp://usuario:password@IP_NAS/NombreCarpetaCompartida&#8217; &#8216;/Volumes/NombreCarpetaCompartida&#8217;;
  
fi&#8221;