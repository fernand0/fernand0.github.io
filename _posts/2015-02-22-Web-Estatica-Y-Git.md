---
layout: post
title: "Mantener una web estática con Git"
date: "Sun Feb 22 20:52:01 +0100 2015"
category: meta
tags: meta git control versiones web estática local servidor
---



<a href="https://www.flickr.com/photos/fernand0/11389222363/" title="Tela de araña"><img src="https://farm4.staticflickr.com/3721/11389222363_04d2d8ac3e_m.jpg" width="240"  alt="Tela de araña" style="float:left; margin:5px"></a> 
Mantengo una página web con las cosas del trabajo desde hace bastante tiempo (la primera versión que hay en archive.org tiene una página que pone 1996, pero la verdad es que no recuerdo la fecha exacta, podría ser un poco antes). 
Se puede ver en [Fernando Tricas WWW Homepage](http://webdiis.unizar.es/~ftricas/).
Entonces no había sistemas de gestión de contenidos ni nada parecido y la manera en que hacíamos las páginas era copiando alguna que nos gustaba y poniendo nuestro contenido. 

En algún momento empecé a gestionarla de la siguiente manera: mantenía una copia local donde editaba; cuando estaba satisfecho (o quería ver los cambios) copiaba los ficheros cambiados al servidor (con un programita que busca los ficheros que han sufrido cambios desde la última versión y `scp`). 
El objetivo era doble: evitar editar en el servidor, y tener una copia de seguridad local (que se sumaría a la que nos hacen en el servidor).
En su momento (allá por el 2004) integré un blog con la página (esencialmente publico en la página los titulares de mi blog docente -por cierto, por si alguien le interesa lo mantengo con [PyBlosxom](http://pyblosxom.github.io/)-). La página web sigo usándola para información más permanente (aunque tengo compañeros que han dado el salto a blogs o wikis con páginas concretas dedicadas a eso mismo).

Evalué en algún momento manejar la página con un sistema de control de versiones (CVS era lo que se usaba entonces) pero no me decidí. Últimamente estoy re-pensando un poco algunos flujos de trabajo para tener un sistema mejor de copias de seguridad, con control de versiones. Además estoy trabajando bastante con **git** y he ido añadiendo partes de mi trabajo que están controladas con ese sistema, así que pensé que era el momento de mi página web.

Hice una búsqueda rápida en internet y encontré [Using Git to manage a web site](http://toroid.org/ams/git-website-howto). Aunque hay alguna pequeña diferencia, me ha servido como guía. 

Lo primero que quería hacer era pasar la copia local de mi ordenador de trabajo (que ya no está encendido tanto tiempo como solía) a otro que actúa como servidor para otras cosas y que siempre suele estar en marcha. Para ello, lo primero es crear un directorio:

{% highlight bash %}
ftricas@localServer:~/Documents$ mkdir www && cd www
{% endhighlight %}

Después, lo inicializamos como repositorio git y copiamos el contenido de la webdesde donde la teníamos.

{% highlight bash %}
ftricas@localServer:~/Documents$ git init
ftricas@localServer:~/Documents$ ssh ftricas@webServer "tar cpf - /home/ftricas/directorioWeb/* " | tar xpf - -C .
{% endhighlight %}

Añadimos a git estos ficheros

{% highlight bash %}
ftricas@localServer:~/Documents$ git add .
ftricas@localServer:~/Documents$ git commit -am"Primera versión de la web"
{% endhighlight %}

En el servidor donde se aloja la web necesitamos crear otro repositorio git:


{% highlight bash %}
ftricas@webServer:~/git-backup$ mkdir www.git && cd www.git
ftricas@webServer:~/git-backup$ git init --bare
{% endhighlight %}

Ahora en el servidor que vamos a usar como copia local de trabajo, ponemos este como remoto

{% highlight bash %}
ftricas@localServer:~/git-backup$ git remote add www ssh://webServer/home/ftricas/git-backup/www.git
ftricas@localServer:~/git-backup$ git push www +master:refs/head/master
{% endhighlight %}

En mi caso además hizo falta decirle a git dónde están algunos programas auxiliares de git en el servidor (seguramente esto no es necesario en muchos servidores):

{% highlight bash %}
ftricas@localServer:~/Documents$ git config remote.www.receivepack /donde/esta/git-receive-pack
ftricas@localServer:~/Documents$ git config remote.www.uploadpack /donde/esta/git-upload-pack
{% endhighlight %}

Y ya podemos sincronizar los repositorios:

{% highlight bash %}
ftricas@localServer:~/Documents$ git push www +master:refs/head/master
{% endhighlight %}

Este paso era para tener la primera versión, que ya estaba en el servidor en la web. Ahora necesitamos un paso más, para que podamos automatizar un poco la subida de los ficheros cuando hagamos cambios. Para ello utilizamos un *hook* y la variable **GIT_WORK_TREE** que permite tener la parte de control en el directorio que hemos creado antes y los ficheros en otro directorio diferente: no me gustaba la idea de tener mezclada la parte del control de versiones con los ficheros de la web y esto soluciona ese problema.

Para esto hacemos en el servidor web:

{% highlight bash %}
ftricas@webServer:~/git-backup$ cat > hooks/post-receive
#!/bin/sh
GIT_WORK_TREE=/var/www/miWeb git checkout -f
ftricas@webServer:~/git-backup$ chmod +x hooks/post-receive
{% endhighlight %}

O sea, copiamos esas dos líneas en el fichero `post-receive` y le damos permiso de ejecución.
La idea es que este programita se ejecuta cada vez que hacemos una petición push con los ficheros que hayan cambiado.

Si cambiamos algo, habrá que hacer el correspondiente `commit`, si añadimos ficheros o directorios habrá que utilizar las instrucciones correspondientes `add` y luego enviarlas al servidor:

{% highlight bash %}
ftricas@localServer:~/Documents$ git push www
{% endhighlight %}

Con versiones modernas de git puede ser necesario tener en cuenta que puede ser necesario fijar el comportamiento por defecto del `push`. Yo elegí:

{% highlight bash %}
ftricas@localServer:~/Documents$ git config --global push.default simple
{% endhighlight %}

Lo explican, por ejemplo, en [Warning: push.default is unset; its implicit value is changing in Git 2.0](http://stackoverflow.com/questions/13148066/warning-push-default-is-unset-its-implicit-value-is-changing-in-git-2-0) aunque el propio git nos avisa de lo que podríamos hacer.  

A partir de este momento, cada vez que editamos en local la web y ya estamos satisfechos (o simplemente queremos subir algo al servidor web para ver cómo queda9 podemos hacer el `commit` correspondiente y después el `push`. 
La web se irá actualizando, y tendremos las versiones controladas para el caso de que queramos recuperar la evolución de nuestra página web.

Algunos recursos adicionales:

* [Initing a new remote git repository with existing files](https://crashingdaily.wordpress.com/2009/09/02/initing-a-new-remote-git-repository-with-existing-files/)
* [Using Git to manage a web site](http://toroid.org/ams/git-website-howto)
* [git-upload-pack: command not found, how to fix this correctly](http://stackoverflow.com/questions/225291/git-upload-pack-command-not-found-how-to-fix-this-correctly)
* [Git Loves the Environment](http://git-scm.com/2010/04/11/environment.html)
