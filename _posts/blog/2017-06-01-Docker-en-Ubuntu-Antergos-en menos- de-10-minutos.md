---
layout: page
title: "Docker en Ubuntu, Antergos y derivadas en menos de 10 minutos"
date: 2017-06-01 15:15
tags: [blog, docker, servidor, ubuntu, antergos, terminal]
categories: terminal
comments: trueaplicacione
---
#### Publicado por Angel

![usb](/img/post/docker.png)


------

**Instalación en Ubuntu**

Agregamos clave GPG:  
`sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D`  

Agregamos repositorio:  
`sudo apt-add-repository 'deb https://apt.dockerproject.org/repo ubuntu-xenial main'`

Actualizamos:  
 `sudo apt-get update`

Instalamos docker:  
 `sudo apt-get install -y docker-engine`

Docker tiene que estar iniciado y ejecutándose. Revisamos que realmente funcione:   
`sudo systemctl status docker`

---

**Instalación en Antergos**

Instalar Docker   
`sudo pacman -S docker`

Correr Docker   
`sudo systemctl start docker`
`sudo systemctl enable docker`

---

**Instalación de Portainer**  
Ahora vamos a instalar Portainer. Una servicio web para gestionar nuestro containers:

Instalación:   
`sudo docker pull portainer/portainer`
`sudo docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer`

Ahora escribimos en nuestro navegador:   
`localhost:9000`

Ponemos una contraseña de administrador para gestionar el servicio.

Señalamos la primera opción de las 2 que aparecen para conectarnos y
listo...  

---

**Instalación de Containers**



**Instalar Dockers desde Hub de Docker**

vamos a: <https://hub.docker.com/search/>

1.  Buscamos el Nombre del Docker,lo copiamos
2.  Vamos a la sección **Images** de portainer y pegamos el nombre en
    **Name**
3.  Clicamos el botón que pone **pull**
4.  En **Images** aparecen todos los containers que tenemos
5.  Vamos a la sección **Containers** y clicamos **+ Add container**
6.  Ponemos un nombre que queramos y en **Image**, el nombre de la
    imagen y pulsamos **start**
