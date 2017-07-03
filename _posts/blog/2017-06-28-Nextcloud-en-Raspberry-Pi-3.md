---
layout: page
title: "Nextcloud 12 en Raspberry Pi 3 con MariaDB, PHP 5 y lighttp"
date: 2017-06-28 19:10
tags: [blog, servidor, ubuntu, terminal,nextcloud, raspberry, PHP, lighttp, MariaDB]
categories: terminal
comments: true
---
#### Publicado por Angel

![usb](/img/post/nextcloud.png)


------


*Instalaremos Nextcloud con MariaDB*

* Instalamos MariaDB  


```
sudo apt install mariadb-server
```


Nos pedirá la contraseña

```
user:	root
paswd:
base:
```

Securizamos la instalación:

```
sudo mysql_secure_installation
```

Tras introducir la contraseña de root respondemos a las preguntas como sigue:

* Change the root password? [Y/n] n

* Remove anonymous users? [Y/n] y

* Disallow root login remotely? [Y/n] y

* Remove test database and access to it? [Y/n] y

* Reload privilege tables now? [Y/n] y

Accedemos a la consola de MariaDB:

```
mysql -u root -p

```

*Y ejecutamos los siguientes comandos cambiando “miusuario” y “micontraseña” al gusto:*
crear una base nueva mysql

```
mysqladmin -u root -p create NOMBRE-DE-DB

```

Ya tenemos lista la base de datos.


**Instalamos PHP5 y el servidor lighttp**


```
sudo apt install lighttpd php5-cgi php5-curl php5-gd php5-mysql~
```


* Adaptamos para que lighttpd funcione con PHP5


```
sudo nano /etc/lighttpd/lighttpd.conf
```


Hay que ir al apartado server.modules y añadir la siguiente linea:

```
"mod_fastcgi",
```
Y al final del archivo añadimos lo siguiente:

```
fastcgi.server = ( ".php" => ((
                   "bin-path" => "/usr/bin/php-cgi",
                   "socket" => "/tmp/php.socket"
                )))

```  
**Ahora ya funciona php en lighttp**


* Ahora vamos a la web de  [Nextcloud](https://nextcloud.com/install) y descargamos el archivo comprimido en:

```
cd /var/www/html
```

```
sudo wget https://download.nextcloud.com/server/releases/nextcloud-12.0.0.zip
```

```
sudo unzip nextcloud-12.0.0.zip
```

```
sudo rm nextcloud-12.0.0.zip
```

```
sudo chown -R www-data:www-data /var/www/html/nextcloud
```

Accedemos desde el navegador a nuestro servidor http://ip_de_la_raspberry.com/nextcloud/ y rellenamos todos los datos que nos pide el instalador:




Otros comandos.

* reiniciar lighttp

```
sudo service lighttpd restart
```




Fuentes: [miraspberrypi](https://miraspberrypi.wordpress.com/2016/07/28/nextcloud-en-raspbian/), [desdelinux](http://blog.desdelinux.net/10-comandos-para-administrar-bases-de-datos-con-mysqladmin/)


<!-- -------------------------------------Aquí abajo los comentarios -------------------------------------------  -->
[Canal en Telegram](https://t.me/uGeek)
[uGeekPodcast en Twitter](https://twitter.com/ugeekpodcast)

Tags: {% assign sorted_tags = page.tags | sort %} {% for tag in sorted_tags %} , <span class="tag"><a href="/tag#{{ tag }}">{{ tag }}</a></span> {% endfor %},


{% if page.comments %}
<div id="disqus_thread"></div>
<script>

/**
*  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
*  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/
/*
var disqus_config = function () {
this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = 'https://https-angelbcn-github-io-ugeek.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>

{% endif %}

<script id="dsq-count-scr" src="//https-angelbcn-github-io-ugeek.disqus.com/count.js" async></script>
