---
layout: post
title: "Habemus tags"
date: "Mon Feb 2 11:55:01 +0100 2015"
category: meta
tags: [meta, blog, github, jekyll, pages]
---



<a href="https://500px.com/photo/66381679/giteando-by-fernando-trica://500px.com/photo/97643829/etiquetas-en-fernand0-github-io-by-fernando-tricas" title="Etiquetas"><img src="https://ppcdn.500px.org/97643829/4f7cc1049c0c4d5036da1cffb2af9321b1fdfcfb/3.jpg" width="240"  alt="Meta" style="float:left; margin:5px"></a>


Uno de los problemas que encontré con este alojamiento es que no tiene etiquetas (tags). De hecho, no sólo no las tiene sino que no está previsto que se incluyan fácilmente con la configuración actual porque no hay  plugins disponibles [Using Jekyll Plugins with GitHub Pages](https://help.github.com/articles/using-jekyll-plugins-with-github-pages/) (Wow, un plugin de emojis, y otro de menciones!).

Pongo estas ideas aquí por si alguien me da pistas sobre cómo hacerlo mejor y/o por si alguien más puede aprovecharlas en su sitios.

Puesto que no puedo añadir plugins para las etiquetas y tampoco quiero generar todo el sitio estáticamente (quiero imaginar que es mejor utilizar jekyll en las `github pages`) pensé utilizar alguno de los plugins que hay para generar sólo las etiquetas. De los que encontré estoy probando [jekyll-tagging](https://github.com/pattex/jekyll-tagging) que ha sido bastante fácil de instalar y configurar, como se explica más abajo.
Hay más formas, como [jekyll-tags-plugin](https://github.com/polymetis/jekyll-tags-plugin/blob/master/_layouts/tag_index.html), y en [Tags In Jekyll](http://charliepark.org/tags-in-jekyll/) hay otra explicación.
Incluso llegué a pensar en hacerme un programita para generarlo pero me parecía demasiado trabajo tener que ver cómo va el sistema de plantillas y todo eso...  

Primero, hago una **nueva** copia del sitio en local (con `git clone`): me servirá para generar el sitio con sus etiquetas y todo.

En este sitio sigo las instrucciones de los desarrolladores del plugin [README](https://github.com/pattex/jekyll-tagging/blob/master/README.rdoc) para instalarlo. En particular, instalar la gema, generar el fichero `Gemfile`, poner el código en el directorio `_plugins` y modificar el `_config.yml`.

* Genero el sitio con `jekyll build --watch` y en `_site` lo tengo en estático.
* Copio al sitio donde mantengo el repositorio local (donde edito, genero y publico los posts) el directorio `_site/tags` a la raíz (parte estática [pages](http://jekyllrb.com/docs/pages/)) , lo añado con `git add` y publico. 
* Ahora tengo el sitio servido por `jekyll` con las etiquetas en modo estático. 

Los problemas de esta forma de trabajar parecen evidentes: necesito dos copias en local del sitio, el flujo de trabajo complicado (aunque se puede automatizar).
¿Las ventajas? Tratar de mantener en la medida de lo posible el funcionamiento en `github.io` obteniendo la funcionalidad que nos ofrezcan.
Veremos si es acertado o será mejor cambiar más adelante pero ... 
¡Tachán! 
Tenemos etiquetas.

Próximamente: 
Entiendo que podremos generar las categorías de una forma parecida (espero que no haga falta una tercera copia). 
Nunca he recibido muchos comentarios, pero espero poder incluirlos de alguna forma: la gente utiliza sitios como [disqus](https://disqus.com/) pero fantaseo con algo más cercano a GitHub (¿tal vez a través de las *issues*? Veo que no soy el
primero que lo piensa en [GitHub hosted comments for GitHub hosted blogs](http://ivanzuzak.info/2011/02/18/github-hosted-comments-for-github-hosted-blogs.html).
La limitación será entonces que para usarlo será necesario estar registrado en GitHub pero ... ¿Saben por qué me apunté yo aquí? ¡Justo! Porque alguien me sugirió que lo hiciera ([vimblog.vim: publicar en wordpress.com fácilmente](https://mbpfernand0.wordpress.com/2009/02/13/vimblogvim-publicar-en-wordpresscom-facilmente/)).  

Seguiremos informando.
