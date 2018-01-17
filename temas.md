---
layout: page
title: Temas
desc: "Lista de post ordenados por etiquetas"
permalink: /Temas/

sitemap:
  priority: .5

---

---
<!-- Begin SpeakPipe code -->
<script type="text/javascript">
(function(d){
var app = d.createElement('script'); app.type = 'text/javascript'; app.async = true;
var pt = ('https:' == document.location.protocol ? 'https://' : 'http://');
app.src = pt + 'www.speakpipe.com/loader/u33wn17v7gblat29taobg3x8q901jwfj.js';
var s = d.getElementsByTagName('script')[0]; s.parentNode.insertBefore(app, s);
})(document);
</script>
<!-- End SpeakPipe code -->




**Terminal**  
1. [Antergos. Comandos para terminal y derivadas de Arch Linux](/Antergos-comando-para-terminal-y-derivadas-arch/)  
2. [Crear un USB con una ISO de una distro](https://ugeek.github.io/Crear-un-usb-con-iso/)  
3. [Alias en Bash. (.bashrc)](https://ugeek.github.io/Alias-en-bash/)  



---  


**Servicios**  
1. [Docker en Ubuntu, Antergos y derivadas en menos de 10 minutos](https://ugeek.github.io/Docker-en-Ubuntu-Antergos-en-menos-de-10-minutos/)  

---  

**GitHub**  
1. [Configurar GitHub en tu Pc mediante la terminal](/GitHub.-Configurarlo-en-tu-Pc-mediante-la-terminal/)  
2. [Comandos GitHub en la Terminal.](/GitHub-en-la-Terminal.-Comandos/)  
3. [Crear un Blog Jekyll desde la Terminal](/Crear-un-blog-jekyll-desde-la-terminal/)  

---

**Jekyll**  
1. [Instalar Ruby y Jekyll](/Instalar-Ruby-y-Jekyll/)  
2. [Crear el Feed para el podcast](/generar-feed-para-podcast-en-jekyll/)  


---  

**Aplicaciones**  
1. [Synapse](/Synapse/)  

---

*Podcast*   


Abre con VLC
<a href="https://ugeek.github.io/ugeek.m3u"><img style="float: left;" src="https://ugeek.github.io/img/icon/vlc.png" alt="" width="30" height="30" /></a>



<html lang="en">
<head>
    <meta content="text/html; charset=utf-8" http-equiv="Content-Type">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
    <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

    <script type="text/javascript" >
    var audio;
    var playlist;
    var tracks;
    var current;
    var previous;
    var current_track;
    var previous_track;
    var ntracks;
    function initaudio(){
        audio=$("audio");
        playlist=$("#playlist");
        ntracks=$("[id^=item-]").length
        audio[0].volume=1;
        current=0;
        previous=ntracks-1;
        current_track=playlist.find("#item-0");
        previous_track=playlist.find("#item-"+previous);
        runaudio(current_track, audio[0],false);
        $("#panelplayer").height("50px");
        $("[id^=item-]").click(function(e){
            e.preventDefault();
            previous=current;
            previous_track=current_track;
            remove_play(previous_track);
            current_track=$(this);
            current=current_track.parent().index();
            runaudio(current_track, audio[0]);
        });
        audio[0].addEventListener("ended",function(e){
            playnext();
        });
        audio[0].addEventListener("pause",function(e){
            $("#playing").hide();
            $("#panelplayer").height("50px");
        });
        audio[0].addEventListener("play",function(e){
            $("#playing").show();
            $("#panelplayer").height("auto");
        });
    };
    function playnext(){
        previous=current;
        previous_track=current_track;
        remove_play(previous_track);
        current++;
        current_track=playlist.find("#item-"+current);
        if(current_track.length==0){
            current=0;
            current_track=playlist.find("#item-0");
        }
        runaudio($(current_track),audio[0]);
    }
    function playprevious(){
        previous=current;
        previous_track=current_track;
        remove_play(previous_track);
        current--;
        current_track=playlist.find("#item-"+current);
        if(current<0){
            current=ntracks-1;
        }
        current_track=playlist.find("#item-"+current);
        runaudio($(current_track),audio[0]);
    }
    function remove_play(item){
        isp=$(item.find(".isplaying"));
        isp.html("");
    }
    function runaudio(item, player,play=true){
        isp=$(item.find(".isplaying"))
        isp.html("<i class='fa fa-play' aria-hidden='true'></i>");
        podcast=$(item.find(".podcast"));
        $("#podcast").text(podcast.text());
        track=$(item.find(".track"));
        $("#track").text(track.text());
        link=$(item.find('a'));
        player.src=link.attr("href");
        par=link.parent();
        par.addClass("active").siblings().removeClass("active");
        audio[0].load();
        if(play==true){
            console.log(play);
            audio[0].play();
        }
    }
    $(document).ready(function(){ 
        console.log($("[id^=item-]").length);
        $("#right").bind("click", function(e) {
            playnext();
        });
        $("#left").bind("click", function(e) {
            playprevious();
        });
        $("#playing").hide();
        initaudio();
    });
    </script>
    <link href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css?family=Roboto" rel="stylesheet">
    <style>
        #left{
            margin-top: 7px;
            float: left;
            width: 16px;
            height: 32px;
            cursor:hand;
        }
        #right{
            margin-top: 7px;
            float:left;
            width: 16px;
            height: 32px;
            cursor:hand;
        }
        .ugeektecnologíaandroidlinuxservidoresymuchomás{
	background: url('data:image/png;base64,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');

	background-size: 48px 48px;
}


        body{
            background-color: rgb(247, 247, 247);
            font-family: "Roboto", sans-serif;
        }
        .panel{
            webkit-box-shadow: 0 0 1px rgba(0, 0, 0, 0.15);
            -moz-box-shadow: 0 0 1px rgba(0, 0, 0, 0.15);
            box-shadow: 0 0 1px rgba(0, 0, 0, 0.15);
            box-sizing: border-box;
            display: block;
            background-color: #fff;
            padding: 10px;
            margin: 0 auto;
            margin-bottom: 20px;
        }
        audio {
            width:250px; /* Ancho del reproductor */
            display: block;
            float:left;
        }
        ul {
          list-style-type: none;
          padding-left: 0px;
        }
        li {
            list-style-type: none;
            height:60px;
        }
        span[id^="item-"]{
            height:48px;
            line-height: 20px;
            display: block;
        }
        .isplaying{
            float:left;
            margin-top:12px;
            width:24px;
            height:24px;
            margin-right: 5px;
        }
        .logo{
            float:left;
            width:48px;
            height:48px;
            margin-right: 5px;
            background-size: 48px 48px;
            background-repeat: no-repeat;
        }
        .podcast, #podcast{
            display: block;
            font-size: 16px;
            font-weight: 400;
            color:rgba(0,0,0,.87);
        }
        .track, #track{
            display: block;
            font-size: 14px;
            font-weight: normal;
            color:rgba(0,0,0,.54);
            width: 200px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        #player{
            float:left;
        }
        .playingnow{
            font-size: 12px;
            color: #9E9E9E;
        }
        a{
            text-decoration:none;
            color:rgba(0,0,0,.54);
        }
        a:visited{
            text-decoration: none;
            color:rgba(0,0,0,.54);
        }
        @media only screen and (min-width: 700px) {
            .panel{
                width:600px;
            }
        }
        @media only screen and (max-width: 319px) {
            #player{
                float:none;
            }
            audio{
                width:120px;
            }
            .track,#track{
                width:150px;
            }
            .panel, #player{
                height: auto;
                min-height:50px;
            }
            #playing{
                display:inline-block;
            }
        }
        @media only screen and (min-width: 320px) and (max-width: 499px) {
            .track{
                width:70%;
            }
            #track{
                width:280px;
            }
            #playing{
                display:inline-block;
            }
        }
        @media only screen and (min-width: 500px) {
            .track{
                width:80%;
            }
            #track{
                width:35%;
            }
            #playing{
                display:block;
            }
        }
        @media only screen and (min-width: 600px) {
            #track{
                width:50%;
            }
        }
    </style>
</head>
<body>
    <div class="panel" id="panelplayer">
        <div id="player">
            <a href="#" id="left" onclick="return false" title="Anterior">
                <i class="fa fa-chevron-left" aria-hidden="true"></i>
            </a>
            <audio id="audio" preload="auto" tabindex="0" controls="">
                <source src="">
            </audio>
            <a href="#" id="right" onclick="return false" title="Siguiente">
                <i class="fa fa-chevron-right" aria-hidden="true"></i>
            </a>
        </div>
        <div id="playing">
            <span class="playingnow">Reproduciendo ahora...</span>
            <span id="podcast"></span>
            <span id="track"></span>
        </div>
    </div>
    <div class="panel">
        <ul id="playlist">
        <li class="active">
	<span id="item-0">
		<a href="https://ia801507.us.archive.org/12/items/2AplicacionesYReproductorDePodcast/2%20aplicaciones%20y%20reproductor%20de%20podcast.mp3" title="084. Rerproductor de Podcast y 2 App de Oferta">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">084. Rerproductor de Podcast y 2 App de Oferta</span>
		</a>
	</span>
</li>
<li>
	<span id="item-1">
		<a href="https://ia601500.us.archive.org/0/items/NasVsServidorLinux/Nas%20vs%20Servidor%20Linux.mp3" title="083. Nas vs Servidor Linux">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">083. Nas vs Servidor Linux</span>
		</a>
	</span>
</li>
<li>
	<span id="item-2">
		<a href="https://ia601504.us.archive.org/25/items/SlimbookOneEl3En1/SlimbookOne_El_3_en_1.mp3" title="082. Slimbook One. El 3 en 1">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">082. Slimbook One. El 3 en 1</span>
		</a>
	</span>
</li>
<li>
	<span id="item-3">
		<a href="https://anchor.fm/s/106db04/podcast/download/68109/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fanchor-data%2Fstationexports%2Fpodcasts%2FRecomendaciones-Y-Pr-ximo-Ep---4dadac040f951.m4a" title="081. Recomendaciones y Próximos Podcast">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">081. Recomendaciones y Próximos Podcast</span>
		</a>
	</span>
</li>
<li>
	<span id="item-4">
		<a href="https://ia601506.us.archive.org/0/items/80.HRecorderPro_201711/80.H-Recorder-pro.m4a" title="080. Grabadora de Audio en Oferta">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">080. Grabadora de Audio en Oferta</span>
		</a>
	</span>
</li>
<li>
	<span id="item-5">
		<a href="https://anchor.fm/s/106db04/podcast/download/47948/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fanchor-data%2Fstationexports%2Fpodcasts%2FComo-enlazo-audios-a-Anchor-b378f648f54ec.m4a" title="079. Novedades Anchor y como enlazo mis Audios">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">079. Novedades Anchor y como enlazo mis Audios</span>
		</a>
	</span>
</li>
<li>
	<span id="item-6">
		<a href="https://anchor.fm/s/106db04/podcast/download/47146/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fanchor-data%2Fstationexports%2Fpodcasts%2FAplicaci-n-De-Podcast-Gratis--23f7b134c5844.m4a" title="078. Aplicación Gratis de Podcast y Música Streaming">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">078. Aplicación Gratis de Podcast y Música Streaming</span>
		</a>
	</span>
</li>
<li>
	<span id="item-7">
		<a href="https://anchor.fm/s/106db04/podcast/download/46801/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fanchor-data%2Fstationexports%2Fpodcasts%2FEsExplorer-Y-Otros-Exploradore-1a73fb172fa59.m4a" title="077.Android: Es Explorer y varios exploradores de Carpetas">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">077.Android: Es Explorer y varios exploradores de Carpetas</span>
		</a>
	</span>
</li>
<li>
	<span id="item-8">
		<a href="https://ia601500.us.archive.org/19/items/076.UnServidorEnMiCasaMaratnLinuxero/076.%20Un%20Servidor%20en%20mi%20Casa%20-%20Marat%C3%B3n%20Linuxero.mp3" title="076. Un Servidor en mi Casa - Podcast del Maratón Linuxero 2017">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">076. Un Servidor en mi Casa - Podcast del Maratón Linuxero 2017</span>
		</a>
	</span>
</li>
<li>
	<span id="item-9">
		<a href="https://ia601508.us.archive.org/22/items/075.RespuestaDePreguntasYMaraton/075.%20Respuesta%20de%20Preguntas%20y%20Maraton.mp3" title="075. Respuestas a Preguntas de los Oyentes y Maratón Linuxero">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">075. Respuestas a Preguntas de los Oyentes y Maratón Linuxero</span>
		</a>
	</span>
</li>
<li>
	<span id="item-10">
		<a href="https://ia601507.us.archive.org/20/items/074.NotasYFeed/074.%20Notas%20y%20Feed.mp3" title="074. Me explicáis como tomáis vuestras Notas. Y Que es uGeekRadio">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">074. Me explicáis como tomáis vuestras Notas. Y Que es uGeekRadio</span>
		</a>
	</span>
</li>
<li>
	<span id="item-11">
		<a href="https://ia601501.us.archive.org/17/items/073.PorqueSeDescargaTanRapido/073.%20Porque_se_descarga_tan_rapido.mp3" title="073. ¿Porque se descarga tan rápido la batería de mi Android?">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">073. ¿Porque se descarga tan rápido la batería de mi Android?</span>
		</a>
	</span>
</li>
<li>
	<span id="item-12">
		<a href="https://ia601505.us.archive.org/24/items/072.Anchor/072.%20Anchor.mp3" title="072. Anchor">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">072. Anchor</span>
		</a>
	</span>
</li>
<li>
	<span id="item-13">
		<a href="https://ia601502.us.archive.org/29/items/071.CopiaRemotaDeVuestraSDMasSnaps/071.%20Copia%20remota%20de%20vuestra%20SD,%20Mas%20snap's.mp3" title="071. Copia Remota De Vuestra SD, Mas Snap's">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">071. Copia Remota De Vuestra SD, Mas Snap's</span>
		</a>
	</span>
</li>
<li>
	<span id="item-14">
		<a href="https://ia801500.us.archive.org/2/items/070.EficienciaEnRaspberryYNotas/070.%20Eficiencia%20en%20Raspberry%20y%20Notas.mp3" title="070. Eficiencia de servicios y aplicaciones. Notas entre Keep, OneNote, Paper, Emacs...">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">070. Eficiencia de servicios y aplicaciones. Notas entre Keep, OneNote, Paper, Emacs...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-15">
		<a href="https://ia601505.us.archive.org/23/items/069.RaspberryPi.SiONo/069.%20Raspberry%20Pi.%20Si%20o%20no.mp3" title="069. Raspberry Pi. ¿Esta hecha para mi?">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">069. Raspberry Pi. ¿Esta hecha para mi?</span>
		</a>
	</span>
</li>
<li>
	<span id="item-16">
		<a href="https://ia601505.us.archive.org/11/items/68ComoTenerMasEspacioEnTuMovil/68-Como%20tener%20mas%20espacio%20en%20tu%20movil.mp3" title="068. Android: Limpia tu telefono por dentro">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">068. Android: Limpia tu telefono por dentro</span>
		</a>
	</span>
</li>
<li>
	<span id="item-17">
		<a href="https://ia601507.us.archive.org/16/items/67Miscelanea/67-Miscelanea.mp3" title="067. Miscelánea. Nextcloud 12, Resilio, Rsync...">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">067. Miscelánea. Nextcloud 12, Resilio, Rsync...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-18">
		<a href="https://ia601507.us.archive.org/15/items/NextcloudResilioSyncthingQueNubeElijoo/Nextcloud%2c%20Resilio%2c%20Syncthing%20%c2%bfQue%20Nube%20elijo%3f.mp3" title="066. Nextcloud, Resilio, Syncthing... ¿Que Nube elijo?">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">066. Nextcloud, Resilio, Syncthing... ¿Que Nube elijo?</span>
		</a>
	</span>
</li>
<li>
	<span id="item-19">
		<a href="https://ia601502.us.archive.org/7/items/065.Tiddlywiki/065.%20tiddlywiki.mp3" title="065. TiddlyWiki. Una Wiki en un único archivo y multiplataforma.">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">065. TiddlyWiki. Una Wiki en un único archivo y multiplataforma.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-20">
		<a href="https://ia801501.us.archive.org/34/items/064.ResilioLaNubeDondeElControlLoTienesTu/064.%20Resilio,%20La%20nube%20donde%20el%20control%20lo%20tienes%20tu.mp3" title="064. Resilio. Una Nube Ilimitada, donde el control de tus datos los tienes tu.">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">064. Resilio. Una Nube Ilimitada, donde el control de tus datos los tienes tu.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-21">
		<a href="https://ia801502.us.archive.org/3/items/ConLinuxEsPosible/Con%20Linux%20es%20posible.mp3" title="063. Con Linux es posible">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">063. Con Linux es posible</span>
		</a>
	</span>
</li>
<li>
	<span id="item-22">
		<a href="https://ia801505.us.archive.org/28/items/062.DomoticaConMiRasperry./062.%20Domotica%20con%20mi%20Rasperry..mp3" title="062. Domótica con mi Raspberry Pi. Usemos el GPIO">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">062. Domótica con mi Raspberry Pi. Usemos el GPIO</span>
		</a>
	</span>
</li>
<li>
	<span id="item-23">
		<a href="https://ia601502.us.archive.org/23/items/DockerEnMenosDe10Min/Docker%20en%20menos%20de%2010%20min.mp3" title="061. Docker en 10 minutos">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">061. Docker en 10 minutos</span>
		</a>
	</span>
</li>
<li>
	<span id="item-24">
		<a href="https://ia601504.us.archive.org/9/items/TerminalAlias/Terminal%20alias.mp3" title="060. La Terminal mas fácil con alias">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">060. La Terminal mas fácil con alias</span>
		</a>
	</span>
</li>
<li>
	<span id="item-25">
		<a href="https://ia801505.us.archive.org/21/items/059.2AplicacinesParaTomarNotas/059.%202%20Aplicaci%C3%B3nes%20para%20tomar%20Notas.mp3" title="059. 2 Aplicaciones de Notas alternativas que utilizo">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">059. 2 Aplicaciones de Notas alternativas que utilizo</span>
		</a>
	</span>
</li>
<li>
	<span id="item-26">
		<a href="https://ia601502.us.archive.org/10/items/058.Android.AppCloneMultipleAccounts/058.%20Android.%20App%20clone%20-%20Multiple%20Accounts.m4a" title="058. Android: Multicuentas. Gestion de Servicios Raspberry Pi">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">058. Android: Multicuentas. Gestion de Servicios Raspberry Pi</span>
		</a>
	</span>
</li>
<li>
	<span id="item-27">
		<a href="https://ia801500.us.archive.org/13/items/057.MulticuentaTelegramWire/057.%20Multicuenta%20telegram,%20wire.mp3" title="057. Multicuenta de Telegram en tu PC de escritorio y Wire">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">057. Multicuenta de Telegram en tu PC de escritorio y Wire</span>
		</a>
	</span>
</li>
<li>
	<span id="item-28">
		<a href="https://ia801503.us.archive.org/12/items/056.VideoderYLlamadasTelegram/056.%20Videoder%20y%20llamadas%20Telegram.mp3" title="056. Android: Videoder y llamadas de Telegram">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">056. Android: Videoder y llamadas de Telegram</span>
		</a>
	</span>
</li>
<li>
	<span id="item-29">
		<a href="https://ia801506.us.archive.org/9/items/055.M4aAplicacionesDePodcastYNuevoMicro/055.%20M4a,%20aplicaciones%20de%20Podcast%20y%20nuevo%20micro.mp3" title="055. Nuevos Cambios...">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">055. Nuevos Cambios...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-30">
		<a href="https://ia601507.us.archive.org/31/items/054.TelefnicaEstaSiendoAtacada/054.%20Telef%C3%B3nica%20esta%20siendo%20atacada!%20.mp3" title="054. Telefónica esta siendo Atacada!!!">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">054. Telefónica esta siendo Atacada!!!</span>
		</a>
	</span>
</li>
<li>
	<span id="item-31">
		<a href="https://ia601502.us.archive.org/7/items/053.Synapse/053.%20Synapse%20.mp3" title="053. Synapse">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">053. Synapse</span>
		</a>
	</span>
</li>
<li>
	<span id="item-32">
		<a href="https://ia601506.us.archive.org/33/items/JekyllOWordpress/Jekyll%20o%20Wordpress.mp3" title="052. ¿Jekyll o WordPress?">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">052. ¿Jekyll o WordPress?</span>
		</a>
	</span>
</li>
<li>
	<span id="item-33">
		<a href="https://ia801502.us.archive.org/5/items/051.AdisBloggerHolaGithub/051.%20Adi%C3%B3s%20Blogger,%20Hola%20Github%20.mp3" title="051. Adiós Blogger, Hola GitHub!">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">051. Adiós Blogger, Hola GitHub!</span>
		</a>
	</span>
</li>
<li>
	<span id="item-34">
		<a href="https://ia801505.us.archive.org/9/items/050.QueAndoHaciendo/050.%20Que%20ando%20haciendo.mp3" title="050. Que ando haciendo, nuevas publicaciones y más...">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">050. Que ando haciendo, nuevas publicaciones y más...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-35">
		<a href="https://ia601503.us.archive.org/0/items/049.Syncthing/049.%20Syncthing.mp3" title="049. Instalando Syncthing en Ubuntu, Antergos y Raspberry Pi">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">049. Instalando Syncthing en Ubuntu, Antergos y Raspberry Pi</span>
		</a>
	</span>
</li>
<li>
	<span id="item-36">
		<a href="https://ia601503.us.archive.org/28/items/EncuentroDeAmiguetes/Encuentro%20de%20amiguetes.mp3" title="048. Encuentro de amiguetes">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">048. Encuentro de amiguetes</span>
		</a>
	</span>
</li>
<li>
	<span id="item-37">
		<a href="https://ia801500.us.archive.org/21/items/SeEstropeaLaSDDeMiRasberry/Se%20estropea%20la%20SD%20de%20mi%20rasberry.mp3" title="047. Se quemó la SD. Comparación de consumos entre PC, NAS-Microserver, Raspberry Pi">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">047. Se quemó la SD. Comparación de consumos entre PC, NAS-Microserver, Raspberry Pi</span>
		</a>
	</span>
</li>
<li>
	<span id="item-38">
		<a href="https://ia601509.us.archive.org/6/items/046SyncthingResilioYDukto/%23046%20Syncthing%2c%20Resilio%20y%20Dukto%20.mp3" title="046. Sincronización de carpetas entre dispositivos. Syncthing, Resilio y Dukto">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">046. Sincronización de carpetas entre dispositivos. Syncthing, Resilio y Dukto</span>
		</a>
	</span>
</li>
<li>
	<span id="item-39">
		<a href="https://ia801505.us.archive.org/27/items/045CrossoverConSalmorejoGeek/%23045%20Crossover%20con%20Salmorejo%20Geek.mp3" title="045. Crossover con Salmorejo Geek, donde hablamos de Mastodon, Ubuntu, Telegram y mucho mas...">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">045. Crossover con Salmorejo Geek, donde hablamos de Mastodon, Ubuntu, Telegram y mucho mas...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-40">
		<a href="https://ia801504.us.archive.org/22/items/044WebDeJekyllEnGithub/%23044%20Web%20de%20Jekyll%20en%20Github.mp3" title="044. La web de Jekyll en GitHub, va tomando forma">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">044. La web de Jekyll en GitHub, va tomando forma</span>
		</a>
	</span>
</li>
<li>
	<span id="item-41">
		<a href="https://ia601509.us.archive.org/23/items/043BotDeTelegramDeIFTTT/%23043%20Bot%20de%20Telegram%20de%20IFTTT.mp3" title="043. Bot de Telegram IFTTT">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">043. Bot de Telegram IFTTT</span>
		</a>
	</span>
</li>
<li>
	<span id="item-42">
		<a href="https://ia601502.us.archive.org/25/items/042ElAtareaoVisitaElCrossoverDeLaSemana/%23042%20El%20Atareao%20visita%20el%20Crossover%20de%20la%20Semana.mp3" title="042. El Atareao visita el Crossover de la Semana">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">042. El Atareao visita el Crossover de la Semana</span>
		</a>
	</span>
</li>
<li>
	<span id="item-43">
		<a href="https://ia801502.us.archive.org/1/items/041UbuntuYElAdiosAUnity/%23041%20Ubuntu%20y%20el%20adi%c3%b3s%20a%20Unity.mp3" title="041. Ubuntu y el adios de Unity">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">041. Ubuntu y el adios de Unity</span>
		</a>
	</span>
</li>
<li>
	<span id="item-44">
		<a href="https://ia801504.us.archive.org/29/items/40AntergosOCNewsDeNextcloudYJekyll/%2340%20Antergos%2c%20OCNews%20de%20Nextcloud%20y%20Jekyll%20.mp3" title="040. Antergos, Ocnews De Nextcloud Y Jekyll">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">040. Antergos, Ocnews De Nextcloud Y Jekyll</span>
		</a>
	</span>
</li>
<li>
	<span id="item-45">
		<a href="https://ia601508.us.archive.org/2/items/039TelegramNotes/%23039%20Telegram%2c%20Notes.mp3" title="039. Aplicación Notes de Nextcloud y crea tus bots de Telegram">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">039. Aplicación Notes de Nextcloud y crea tus bots de Telegram</span>
		</a>
	</span>
</li>
<li>
	<span id="item-46">
		<a href="https://ia601506.us.archive.org/26/items/38CrossoverConMosqueteroWeb/%23%2038%20Crossover%20con%20MosqueteroWeb.mp3" title="038. Crossover con MosqueteroWeb. Masterclass de FreeNas, Docker y virtualización mediante Proxmox y Esxi.">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">038. Crossover con MosqueteroWeb. Masterclass de FreeNas, Docker y virtualización mediante Proxmox y Esxi.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-47">
		<a href="https://ia801503.us.archive.org/18/items/037LlamadasDeTelegram/%23037%20Llamadas%20de%20Telegram.mp3" title="037. Llamadas de Telegram ya estan aquí. Y 3 bots que os encantaran">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">037. Llamadas de Telegram ya estan aquí. Y 3 bots que os encantaran</span>
		</a>
	</span>
</li>
<li>
	<span id="item-48">
		<a href="https://ia601509.us.archive.org/25/items/036PodcastConFrank/%23036%20podcast%20con%20Frank.mp3" title="036. Podcast con Frank de Batería2x100, Servidores Linux y NAS, lo mismo pero  diferente">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">036. Podcast con Frank de Batería2x100, Servidores Linux y NAS, lo mismo pero  diferente</span>
		</a>
	</span>
</li>
<li>
	<span id="item-49">
		<a href="https://ia601501.us.archive.org/10/items/035MiG8/%23035%20Mi%20G8.mp3" title="035. Mi HP ProLiant MicroServer Gen8">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">035. Mi HP ProLiant MicroServer Gen8</span>
		</a>
	</span>
</li>
<li>
	<span id="item-50">
		<a href="https://ia801500.us.archive.org/9/items/034BotDeTelegramSustitutoAShazam/%23034%20Bot%20de%20Telegram%20sustituto%20a%20Shazam.mp3" title="034. Bots de Telegram Sustitutos a Shazam y busqueda de articulos dentro del bot de Pocket">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">034. Bots de Telegram Sustitutos a Shazam y busqueda de articulos dentro del bot de Pocket</span>
		</a>
	</span>
</li>
<li>
	<span id="item-51">
		<a href="https://ia601500.us.archive.org/4/items/033BotDePocketParaTelegram/%23033%20Bot%20de%20Pocket%20para%20Telegram.mp3" title="033. Bots en Telegram. Bot de Pocket">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">033. Bots en Telegram. Bot de Pocket</span>
		</a>
	</span>
</li>
<li>
	<span id="item-52">
		<a href="https://ia601606.us.archive.org/30/items/032MiscelaneaDeViernes/%23032%20Miscel%C3%A1nea%20de%20Viernes.mp3" title="032. Miscelánea de Viernes">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">032. Miscelánea de Viernes</span>
		</a>
	</span>
</li>
<li>
	<span id="item-53">
		<a href="https://ia601606.us.archive.org/14/items/031Keepass.ComoGestionoMisContrasenas/%23031%20Keepass.%20Como%20gestiono%20mis%20contrase%C3%B1as.mp3" title="031. Keepass, como gestiono mis contraseñas">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">031. Keepass, como gestiono mis contraseñas</span>
		</a>
	</span>
</li>
<li>
	<span id="item-54">
		<a href="https://ia601609.us.archive.org/0/items/030Mumble/%23030%20Mumble.mp3" title="030. Mumble, VoIP de Software Libre. Nextcloud, Wallabag y kdenlive">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">030. Mumble, VoIP de Software Libre. Nextcloud, Wallabag y kdenlive</span>
		</a>
	</span>
</li>
<li>
	<span id="item-55">
		<a href="https://ia601608.us.archive.org/28/items/029MiscelneaDeViernes/%23029%20Miscel%C3%A1nea%20de%20viernes.mp3" title="029. Miscelánea de Viernes.">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">029. Miscelánea de Viernes.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-56">
		<a href="https://ia601607.us.archive.org/17/items/ugeekpodcast_gmail_XMPP/XMPP.mp3" title="028. Instala un servidor de mensajeria tipo Whatsapp o Telegram y de Software Libre con XMPP/Jabber">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">028. Instala un servidor de mensajeria tipo Whatsapp o Telegram y de Software Libre con XMPP/Jabber</span>
		</a>
	</span>
</li>
<li>
	<span id="item-57">
		<a href="https://ia601606.us.archive.org/3/items/027InstalaTuVpnEnUbuntuORaspberryPi/%23027%20instala%20tu%20vpn%20en%20Ubuntu%20o%20Raspberry%20Pi.mp3" title="027. Instala una VPN (OpenVpn) en Ubuntu o Raspberry Pi con PiVpn">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">027. Instala una VPN (OpenVpn) en Ubuntu o Raspberry Pi con PiVpn</span>
		</a>
	</span>
</li>
<li>
	<span id="item-58">
		<a href="https://ia601606.us.archive.org/25/items/026PodcastConFrankDeBatera2x100/%23026%20Podcast%20con%20Frank%20de%20Bater%C3%ADa2x100.mp3" title="026. Podcast con Frank de Batería2x100, Hablamos de como gestionamos nuestras Fotos, actualidad y sorteo del libro del año">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">026. Podcast con Frank de Batería2x100, Hablamos de como gestionamos nuestras Fotos, actualidad y sorteo del libro del año</span>
		</a>
	</span>
</li>
<li>
	<span id="item-59">
		<a href="https://ia601600.us.archive.org/16/items/025MtodoMMsCompletoQueParaRecopilarNotasOrgMode/%23025%20M%C3%A9todo%20m%C3%A1s%20completo%20que%20para%20recopilar%20notas%2C%20org%20mode.mp3" title="025. Metodo mas completo para recopilar notas, org Mode">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">025. Metodo mas completo para recopilar notas, org Mode</span>
		</a>
	</span>
</li>
<li>
	<span id="item-60">
		<a href="https://ia601605.us.archive.org/10/items/024ConectateRemotamenteATuRaspberryPiCondataplicity/%23024%20Conectate%20remotamente%20a%20tu%20Raspberry%20Pi%20con%20%22dataplicity%22%20.mp3" title="024. Conectate remotamente a tu Raspberry Pi con "dataplicity"">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">024. Conectate remotamente a tu Raspberry Pi con "dataplicity"</span>
		</a>
	</span>
</li>
<li>
	<span id="item-61">
		<a href="https://ia801609.us.archive.org/20/items/EntrevistaADosDesarrolladoresDeSoftwareLibreDeIgalia/Entrevista%20a%20dos%20desarrolladores%20de%20Software%20Libre%20de%20Igalia.mp3" title="023. Entrevista a Chema y Juan, dos desarrolladores de Software Libre de Igalia.com en el #mwc17">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">023. Entrevista a Chema y Juan, dos desarrolladores de Software Libre de Igalia.com en el #mwc17</span>
		</a>
	</span>
</li>
<li>
	<span id="item-62">
		<a href="https://ia601600.us.archive.org/33/items/EntrevistaConArturoSuarezDirectivoDelCloudDeCanonicalUbuntu/Entrevista%20con%20Arturo%20Suarez,%20Directivo%20del%20Cloud%20de%20Canonical%20Ubuntu.mp3" title="022. Entrevista con Arturo Suarez, DIrectivo del Cloud de Canonical Ubuntu">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">022. Entrevista con Arturo Suarez, DIrectivo del Cloud de Canonical Ubuntu</span>
		</a>
	</span>
</li>
<li>
	<span id="item-63">
		<a href="https://ia801606.us.archive.org/21/items/021UbuntuEnMobileWorldCongress/%23021%20ubuntu%20en%20Mobile%20World%20Congress%20.mp3" title="021. Ubuntu en el Mobile World Congress">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">021. Ubuntu en el Mobile World Congress</span>
		</a>
	</span>
</li>
<li>
	<span id="item-64">
		<a href="https://ia601601.us.archive.org/7/items/20PodcastConFrankDeBatera2x100HablamosDeComoGestionamosNuestraNotas/%2320%20Podcast%20con%20Frank%20de%20Bater%c3%ada2x100%2c%20Hablamos%20de%20como%20gestionamos%20nuestra%20notas%20.mp3" title="020. Podcast con Frank de Batería2x100, Hablamos de como gestionamos nuestra notas y mucho mas...">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">020. Podcast con Frank de Batería2x100, Hablamos de como gestionamos nuestra notas y mucho mas...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-65">
		<a href="https://ia601603.us.archive.org/6/items/019DokuwikiNuevaFormaDeTomarMisNotas/%23019%20Dokuwiki%2c%20nueva%20forma%20de%20tomar%20mis%20notas%20.mp3" title="019. Dokuwiki, nueva forma de tomar mis notas. Monta tu wiki con DokuWiki o MediaWiki.">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">019. Dokuwiki, nueva forma de tomar mis notas. Monta tu wiki con DokuWiki o MediaWiki.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-66">
		<a href="https://ia601604.us.archive.org/24/items/018WallabagElPocketOInstapaper/%23018_Wallabag%2c_el_Pocket_o_Instapaper.mp3" title="018. Como montar Wallabag, el Pocket o Instapaper de software libre y lo mejor de todo, en tu servidor">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">018. Como montar Wallabag, el Pocket o Instapaper de software libre y lo mejor de todo, en tu servidor</span>
		</a>
	</span>
</li>
<li>
	<span id="item-67">
		<a href="https://ia801300.us.archive.org/34/items/017PodcastConFrankDeBateria2x100HablandoDePlexNextcloud.../%23017%20Podcast%20con%20Frank%20de%20Bateria2x100%2c%20hablando%20de%20Plex%2c%20Nextcloud....mp3" title="017. Podcast con Frank de Bateria2x100, hablando de Plex, Nextcloud...">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">017. Podcast con Frank de Bateria2x100, hablando de Plex, Nextcloud...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-68">
		<a href="https://ia801603.us.archive.org/24/items/016QueEsUnServidor/%23016%20Que%20es%20un%20servidor.mp3" title="016. Que es un Servidor (dudas oyentes), servidor web, ...">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">016. Que es un Servidor (dudas oyentes), servidor web, ...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-69">
		<a href="https://ia801603.us.archive.org/20/items/015AlmacenamientoTheNextcloud/%23015_almacenamiento_the_nextcloud.mp3" title="015. Como ampliar el almacenamiento de Nextcloud, combinar con nubes publicas y hacer copias de mis fotos.">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">015. Como ampliar el almacenamiento de Nextcloud, combinar con nubes publicas y hacer copias de mis fotos.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-70">
		<a href="https://ia601602.us.archive.org/11/items/NotasEnNextcloud/Notas%20en%20nextcloud.mp3" title="014. Notas en Nextcloud y Markdown">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">014. Notas en Nextcloud y Markdown</span>
		</a>
	</span>
</li>
<li>
	<span id="item-71">
		<a href="https://ia801601.us.archive.org/21/items/013NewsYFreshRSS.GestorDeNoticiasRSS/%23013%20News%20y%20Fresh%20RSS.%20Gestor%20de%20Noticias%20RSS.mp3" title="013. News y FreshRSS. Gestor de Noticias RSS.">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">013. News y FreshRSS. Gestor de Noticias RSS.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-72">
		<a href="https://ia801604.us.archive.org/21/items/013FDroidAplicacionesDeSoftwareLibre/%23013%20F-Droid%20Aplicaciones%20de%20Software%20Libre.mp3" title="013. bis F-Droid Tienda Android de aplicaciones de Software Libre y Actualizar las Noticias en Nextcloud.">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">013. bis F-Droid Tienda Android de aplicaciones de Software Libre y Actualizar las Noticias en Nextcloud.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-73">
		<a href="https://ia801601.us.archive.org/24/items/012CmoActualizarNextcloudY/%23012_c%c3%b3mo_actualizar_Nextcloud_y.mp3" title="012. Como actualizar Nextcloud y salir del modo de "mantenimiento"">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">012. Como actualizar Nextcloud y salir del modo de "mantenimiento"</span>
		</a>
	</span>
</li>
<li>
	<span id="item-74">
		<a href="https://ia801602.us.archive.org/16/items/011PodcastConFrankDeBateria2x100/%23011%20Podcast%20con%20Frank%20de%20Bateria2x100.mp3" title="011. Podcast con Frank de Bateria2x100, hablando un poco de todo...">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">011. Podcast con Frank de Bateria2x100, hablando un poco de todo...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-75">
		<a href="https://ia601603.us.archive.org/9/items/010ElSistemaOperativoDeBolsillo/%23010%20El%20Sistema%20Operativo%20de%20bolsillo.mp3" title="010. CloudReady el Chromium OS de bolsillo">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">010. CloudReady el Chromium OS de bolsillo</span>
		</a>
	</span>
</li>
<li>
	<span id="item-76">
		<a href="https://ia601602.us.archive.org/11/items/ComoCrearTuPodcastYTotalmenteGtatis/Como%20crear%20tu%20podcast%20y%20totalmente%20gtatis.mp3" title="009. Crea tu podcast en 3 simples pasos y totalmente gratis">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">009. Crea tu podcast en 3 simples pasos y totalmente gratis</span>
		</a>
	</span>
</li>
<li>
	<span id="item-77">
		<a href="https://ia801900.us.archive.org/13/items/008ComoGestionoMisNotas/%23008%20Como%20gestiono%20mis%20notas.mp3" title="008. Como gestiono mis Notas">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">008. Como gestiono mis Notas</span>
		</a>
	</span>
</li>
<li>
	<span id="item-78">
		<a href="hhttps://ia601902.us.archive.org/28/items/007LinuxEsUnaAlternativaReal/%23007%20Linux%20es%20una%20alternativa%20real.mp3" title="007. Linux es una alternativa real">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">007. Linux es una alternativa real</span>
		</a>
	</span>
</li>
<li>
	<span id="item-79">
		<a href="https://ia601900.us.archive.org/18/items/ElTrelloDeSoftwareLibreWekan/El_Trello_de_software_libre_Wekan.mp3" title="006. El Trello de Software Libre Wekan y Kanboard para Raspberry Pi. El sistema Kanban en tu servidor.">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">006. El Trello de Software Libre Wekan y Kanboard para Raspberry Pi. El sistema Kanban en tu servidor.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-80">
		<a href="https://ia601603.us.archive.org/9/items/005PaperDeDropbox/%23005%20Paper%20de%20Dropbox.mp3" title="005. Paper de Dropbox">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">005. Paper de Dropbox</span>
		</a>
	</span>
</li>
<li>
	<span id="item-81">
		<a href="https://ia601903.us.archive.org/19/items/004ServidorLinuxVsQNapSynology/%23004%20Servidor%20Linux%20Vs%20QNap-Synology.mp3" title="004. Servidor Linux Vs QNAP-Synology">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">004. Servidor Linux Vs QNAP-Synology</span>
		</a>
	</span>
</li>
<li>
	<span id="item-82">
		<a href="https://ia601903.us.archive.org/4/items/003Nextcloud/%23003%20Nextcloud.mp3" title="003. Nextcloud. Instalar tu Nube en menos de 2 minutos.">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">003. Nextcloud. Instalar tu Nube en menos de 2 minutos.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-83">
		<a href="https://ia801904.us.archive.org/20/items/DeQueVaEstoDeUGeek/De%20que%20va%20esto%20de%20uGeek%3f.mp3" title="002. "De qué va esto de uGeek?"">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">002. "De qué va esto de uGeek?"</span>
		</a>
	</span>
</li>
<li>
	<span id="item-84">
		<a href="https://ia801602.us.archive.org/21/items/HolaMundo_201701/Hola%20Mundo.mp3" title="001. Hola Mundo">
			<span class="isplaying"></span>
			<span class="logo ugeektecnologíaandroidlinuxservidoresymuchomás"></span>
			<span class="podcast">uGeek - Tecnología, Android, Linux, Servidores y mucho más...</span>
			<span class="track">001. Hola Mundo</span>
		</a>
	</span>
</li>


        </ul>
    </div>
</body>
</html>
