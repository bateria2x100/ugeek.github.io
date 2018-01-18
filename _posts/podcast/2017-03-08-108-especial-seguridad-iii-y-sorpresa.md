---
id: 386
title: '#108 &#8211; Especial Seguridad III Y Sorpresa'
date: 2017-03-08T15:20:03+00:00
author: bateria2x100
layout: post
guid: https://www.bateria2x100.com/?p=386
permalink: /108-especial-seguridad-iii-y-sorpresa/
enclosure:
  - https://www.bateria2x100.com/podcast/Bat2x100_108.mp3
categories:
  - Mac OSX
tags:
  - Podcast
---
<div class="powerpress_player" id="powerpress_player_5957">
  <audio class="wp-audio-shortcode" id="audio-386-110" preload="none" style="width: 100%;" controls="controls"><source type="audio/mpeg" src="https://www.bateria2x100.com/podcast/Bat2x100_108.mp3?_=110" /><a href="https://www.bateria2x100.com/podcast/Bat2x100_108.mp3">https://www.bateria2x100.com/podcast/Bat2x100_108.mp3</a></audio>
</div>

<p class="powerpress_links powerpress_links_mp3">
  Podcast: <a href="https://www.bateria2x100.com/podcast/Bat2x100_108.mp3" class="powerpress_link_pinw" target="_blank" title="Play in new window" onclick="return powerpress_pinw('https://www.bateria2x100.com/?powerpress_pinw=386-podcast');" rel="nofollow">Play in new window</a> | <a href="https://www.bateria2x100.com/podcast/Bat2x100_108.mp3" class="powerpress_link_d" title="Download" rel="nofollow" download="Bat2x100_108.mp3">Download</a>
</p>

<p class="powerpress_links powerpress_subscribe_links">
  Subscribe: <a href="https://subscribeonandroid.com/www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_android" title="Subscribe on Android" rel="nofollow">Android</a> | <a href="https://www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_rss" title="Subscribe via RSS" rel="nofollow">RSS</a>
</p>

Especial Seguridad (iii)

ASPECTOS DES SEGURIDAD BÁSICOS :

LO QUE SOY, LO QUE TENGO Y LO QUE SÉ :

Lo que soy : medidas biométricas (huella dactilar, escáner de iris, reconocimiento facial, mano&#8230;)
  
Lo que sé : Un password.
  
Lo que tengo : Algo que tengo físicamente, por ejemplo : targeta con microchip, targeta de coordenadas de un banco, Autenticación en dos pasos -> ahora explicaremos que es.

Teniendo 2 de estas tres cosas, SISTEMA MUY SEGURO. Aunque me roben el móbil, no saben mi password, o no tienen mi huella dactilar.

Apple ha desactivado la página donde se podía comprobar si el número de serie del terminal era robado o no ya que lo estaban usando para encontrar números válidos. Todo esto lo explican mejor en PuroMac original #428. 

Usar la autenticación en dos pasos :Lo que sé y lo que tengo. Esto para dispositivos con IOS 9 o anteriores sigue vigente, pero para nuevos dispositivos : 

Esto funciona a partir de una clave generadora que se guarda en el servidor y en nuestro terminal y que cada 30 segundos arroja un &#8220;token&#8221; de 6 cifras que lógicamente es el mismo en los dos sitios.
  
Hay varias apps para gestionar estos tokens :
  
Authy, Google Authenticator, microsoft también tiene una&#8230;. Importante, la hora de nuestro terminal debe estar correcta !!! Sinó puede ser quen o funcione !! 

Apple (pay pal, twitter) no usa este tipo de apps, y ofrece 2 opciones :

  * sms : primero te envía un sms para validar que tienes ese terminal. 
  * Notificación : al dispositivo de apple que queramos.

Es una buena opción, hoy por hoy 100 % recomendable.

Apple ya ha cambiado esta opción y ahora ofrece la llamada autenticación de doble factor, implementada posteriormente por Apple en todas sus plataformas.
  
La diferencia principal con la verificación en dos pasos es que tan solo podrás activar un dispositivo nuevo desde otro dispositivo de confianza. En definitiva, es la única opción (y por lo tanto la mejor de todas) para mejorar la seguridad y privacidad de tus datos en un producto de Apple

Cómo funciona ? A partir de ahora siempre que tengas que iniciar sesión en iCloud.com en un nuevo navegador, en un iPhone, iPad o Mac necesitarás un código de autenticación de doble factor. 

VPN : Conectarse a Wifi públicas sobre VPN, SIEMPRE ! !

Hacer un mitmf, con kali linux, es realmente fácil, muy fácil. Primero se rastrea la wifi con herramientas como ettercap, se detectan las ips, y después añadimos 2 targets, el router y una víctima, o incluso podemos ojear todos los equipos conectados a esa wifi. Esos paquetes, sinó están encriptados (dentro de un aVPN), son perfectamente legibles, incluso si queremos entrar en gmail, estas https pasan a htt, y sino nos damos cuenta, caemos y ya nos han secuestrado el correo.

Soluciones : 

Tunnel Bear, &#8230; Si tenéis un NAS o un router de gamaalta, es fácil crear una VPN y poder conectarse a ella.
  
Ojo, una VPN en nuestra casa no nos hace anónimos.

Hay varios protocolos de VPN : 

PPTP : Se ha demostrado que puede ser crackeado
  
L2TP-IPSEC : Según Snowden, la NSA lo habría crackeado.
  
OPENVPN: Protocolo abierto, basado en OPENSSL. &#8211;> El más recomendado. Crea claves de forma temporal.
  
OPENVPN :
  
En el MAC : TunnelBlick
  
OpenVPN : En IOS

Sakris KronGruf : Ha hecho un pdf donde explcia como corregir algunos warnings que aparecen en TunnelBlick

OPEN VPN

Otras cosas que he escuchado : 

No instalar ORACLE JAVa, y no instalar FLASH. 
  
Si instalamos JAVA, desactivar la opción que corra JAVA.
  
Los MAC son más seguros qeue los MAC ? A día de hoy no. La política de actualizaciones de Windows es semanal, la de MAC es mucho distante. Por contra, el número de usuarios es menor, y mac y linux requiern que cualquier proceso precise del ok del usuario. Como dicen, el mayor aguejro de seguridad está entre el teclado y la silla.

Los antivirus de mac/NAS (synology) buscan sobre todo, vulnerabilidades de Windows. Si un MAC va a trabajar con unidades de red compartidas en Windows, quizás tendría sentido instalar un antivirus en ese mac.

Lo peligroso son los troyanos, esos programas que isntalamos pensando que hacen una cosa cuando hacen otra. 

Cosas a hacer MAC:

Cifrar el disco FileVault : No realintza el disco, y nos va a facilitar la posibilidad de que nadie tenga acceso a nuestro disco en caso de robo.
  
Gatekeeper (sólo permitir instalar apps firmadas por empresas autorizadas por Apple)
  
Cifrar las copias de seguridad del iphone !
  
Usar gestores de contraseñas, por ejemplo LAst PAss, 1PAssword, Gestor propio de contraseñas del mac.
  
Desactivar las cuentas de invitado :

Fallos 0-day(muy bien pagados, vulnerable no publicadas)
  
Por eso es importante tener las apps actualizadas : 
  
Hay robots que escanean IPS y que buscan determinadas vulnerabilidades.

Ver como @wikileaks publicó en su timeline ayer numerosos informes al respecto de que la 

Ojo en casa si sendesconecta la wifi y te pide la password:ataque de denegacion de servicio y se ponen a la escucha paramque cuando la entres, te la pillen.

Subred en casa : video macjosan

<https://www.youtube.com/watch?v=M3JYWystlOQ>

Información extraida de la red, y de podcasts como :

Applecoding
  
NASeros

<table>
  <tr />
  
  <tr />
  
  <tr />
  
  <tr />
</table>

SORTEO de dos licencias :

Commander One de Eltima Software : 

  * Doble pamel Explorador
  * Integración con Drive y DropBox, 7Z&#8230;)
  * Compresor incluido (en varios formatos, zip
  * Sistema de búsqueda bastante potente ( por expresiones regulares, Spotlight, dentro de ficheros&#8230;)

<http://mac.eltima.com/ftp-manager.html>

Para poder ganar :

1 &#8211; Seguirme en twitter : @bateria2x100
  
2 &#8211; Tweet con algo como : &#8220;quiero ese programa ! #escuchabateria2x100 @bateria2x100&#8221;
  
&#8220;Que me toque a mi ! #escuchabateria2x100 @bateria2x100&#8221;

Sorteo : Fecha límite: Jueves 16/3 a las 23:00
  
Sorteo : Viernes 

Saludos, sed buenos !! 

Como siempre :

@bateria2x100
  
<https://www.bateria2x100.com>
  
<bateria2x100@gmail.com>