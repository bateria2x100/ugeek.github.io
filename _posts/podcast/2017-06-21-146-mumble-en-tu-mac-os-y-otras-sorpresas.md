---
id: 557
title: '#146 &#8211; Mumble en tu Mac OS&#8230;Y otras sorpresas&#8230;'
date: 2017-06-21T16:27:29+00:00
author: bateria2x100
layout: post
guid: https://www.bateria2x100.com/?p=557
permalink: /146-mumble-en-tu-mac-os-y-otras-sorpresas/
enclosure:
  - https://www.bateria2x100.com/podcast/Bat2x100_146.m4a
image: /wordpress/wp-content/uploads/2017/06/IMG_6034-400x372.jpeg
categories:
  - Mac OSX
---
<div class="powerpress_player" id="powerpress_player_5995">
  <audio class="wp-audio-shortcode" id="audio-557-148" preload="none" style="width: 100%;" controls="controls"><source type="audio/mpeg" src="https://www.bateria2x100.com/podcast/Bat2x100_146.m4a?_=148" /><a href="https://www.bateria2x100.com/podcast/Bat2x100_146.m4a">https://www.bateria2x100.com/podcast/Bat2x100_146.m4a</a></audio>
</div>

<p class="powerpress_links powerpress_links_m4a">
  Podcast: <a href="https://www.bateria2x100.com/podcast/Bat2x100_146.m4a" class="powerpress_link_pinw" target="_blank" title="Play in new window" onclick="return powerpress_pinw('https://www.bateria2x100.com/?powerpress_pinw=557-podcast');" rel="nofollow">Play in new window</a> | <a href="https://www.bateria2x100.com/podcast/Bat2x100_146.m4a" class="powerpress_link_d" title="Download" rel="nofollow" download="Bat2x100_146.m4a">Download</a>
</p>

<p class="powerpress_links powerpress_subscribe_links">
  Subscribe: <a href="https://subscribeonandroid.com/www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_android" title="Subscribe on Android" rel="nofollow">Android</a> | <a href="https://www.bateria2x100.com/feed/podcast/" class="powerpress_link_subscribe powerpress_link_subscribe_rss" title="Subscribe via RSS" rel="nofollow">RSS</a>
</p>

Mumble en tu Mac OS

## Concurso DaisyDisk : Ganadores :

    * @jar77jar
    * @Pferrer
    

  * ClippyCam(IOS) free con compras in app 
      * <https://itunes.apple.com/es/app/clippycam/id1236287944?mt=8>

## _Comentario Fundas iPhone_

    * Vooway : [Oro Ultra-delgado Funda Case Cover y Protector de Pantalla Para Apple iPhone 7 Plus 5.5 pulgadas Vooway® MS70198: Amazon.es: Electrónica](https://www.amazon.es/gp/product/B01LS03HG4/ref=oh_aui_search_detailpage?ie=UTF8&psc=1)
    * Doupi :  [doupi UltraSlim Funda para iPhone 7 Plus ( 5.5” ) finamente aburrido Ligero estuche projoector Protective Cover Case escudo shell Hardcase, rojo: Amazon.es: Electrónica](https://www.amazon.es/gp/product/B01LSBSN94/ref=oh_aui_detailpage_o02_s00?ie=UTF8&psc=1)
    * Spigen: [Funda iPhone 7 Plus, Spigen® Air Skin Ultra-Thin Soft Clear Premium Semi-transparent Lightweight / Exact Fit / NO Bulkiness Hard Funda Carcasa para iPhone 7 Plus (2016): Amazon.es: Electrónica](https://www.amazon.es/gp/product/B01GIWFLCA/ref=oh_aui_search_detailpage?ie=UTF8&psc=1)
    

  * Aparición Angel en promo podcast -> Mumble

## Concurso licencias [Resilio](https://www.resilio.com) !!! “#loveResilio”

## _DOCKER MUMBLE en nuestro MAC !_

Hay que distinguir las imágenes de los containers :

  * Imagen : La que descargamos de la store [Docker Store](https://store.docker.com) 
      * Container : Lo que creamos a partir de una imagen. Se pueden crear varios containers d una imagen (con nombres distintos del container claro)

  1. Instalar Docker para MAC
  2. Abrir el Puerto 64738 en el router. 
  3. Entrar en terminal : 

    docker pull mattikus/murmur
    docker run -d -p 64738:64738 -p 64738:64738/udp mattikus/murmur
    

  1. Parar/arrancar un container :

    docker stop Nombre
    docker start Nombre
    

_Para listar los containers corriendo:_
  
docker ps

_Para listar las imágenes :_ 
  
docker images

Hasta aquí ya tendríamos mumble corriendo, pero si queremos modificar el fichero ini, para pode cambiar el puerto y el password de acceso a nuestras SALAS de mumble :

  * _Para modificar el murmur.ini :_
  
    (copiamos el murmur.ini del docker a nuestro disco)
  
    docker cp your-container-name:/etc/murmur.ini /path/to/murmur.ini
    
    Yo lo que he cambiado es :
    
    # Password to join server.
    
            # Welcome message sent to clients when they connect.
        

  * _Per ejecutar el container con la ini modificada :_
  
    docker run -d -p 64738:64738 -p 64738:64738/udp \
  
    -v /path/to/murmur.ini:/etc/murmur.ini mattikus/murmur
    
    /NOTA : El Path to murmur.ini se puede sacar fácil arrastrando el fichero desde Finder a una ventana de Terminal/

Importante que renombres tu mumble a un nombre más sencillo que los que aparecen, para cambiar nombre :

    * *Renombrar un container :*
    

docker rename Nombre_antiguo NombreNuevo

_Queremos desinstalarlo completamente una imagen :_

  1. Mirar que no esté en ningún contaminer : 
      1. docker ps (para ver los containers corriendo)
      2. La columna NAMES indica el nombre de cada container
  2. Si está corriendo : 
      1. docker stop “nombre del container”
  3. Eliminamos el container : 
      1. docker rm nombre_Container
  4. Listamos las imágenes 
      1. docker images
      2. copiamos el image ID
  5. Eliminamos la imagen 
      1. docker rmi Image_ID

YA está ! 

Para el Cliente :

    Se instala fácil :
    [Mumble.com | Mumble Server Hosting](https://www.mumble.com/)
    
    [Skins - Mumble Wiki](https://wiki.mumble.info/wiki/Skins)
    Y para cambiar el aspecto feo de la app :
        En Mumble, User Interface, y allí veréis donde seleccionar la ruta donde habéis descargo el PIB (es una carpeta con multitud de ficheros)
    

Por favor, reseñas y retuits ! Gracias equipoooo

Sed buenos !!

[@bateria2x100](https://Twitter.com/bateria2x100)
  
<https://www.bateria2x100.com>
  
<bateria2x100@gmail.com>

<table>
  <tr />
  
  <tr />
</table>

#podcast/plantilla

<table>
  <tr />
  
  <tr />
</table>