---
layout: post
title: "Extraer enlaces de una página web"
date: "Sun Jan 11 19:05:01 +0100 2015"
category: Python
tags: python desarrollo programación Facebook enlaces HTML Beautiful Soup
---


<a href="https://plus.google.com/112862240851570159916/posts/Ps9VHx71gCW" title="Enlaces"><img src="https://lh3.googleusercontent.com/-IVdMXNs-UyE/VLK46RXRP1I/AAAAAAAAJ7E/rvp7ZzTOy4I/w521-h423-no/2015-01-11-FacebookPage.png" width="240"  alt="Enlaces en Página de Facebook" style="float:left; margin:5px"></a>

Hace algunas semanas hablábamos de [Publicar en Twitter las entradas de este sitio usando Python](http://fernand0.github.io/publicar-en-twitter-las-entradas-de-este-sitio/) y prometíamos hacer lo mismo con Facebook. 

Echando un vistazo al [API de Facebook](https://developers.facebook.com/) y haciendo algunas pruebas me encontré con que no podía publicar enlaces con su texto (Facebook los transforma para  que podamos pinchar en ellos, pero no permite -o no encontré la forma- que los pongamos con su texto y esas cosas). 
Por otro lado, quería experimentar con la posibilidad de publicar las entradas de esta bitácora completas allí; Facebook no favorece que introduzcamos textos largos porque nos muestra un trocito y permite abrir 'el resto'.

Siempre me ha llamado la atención la 'netiqueta' de algunas listas de correo donde suele ponerse al lado del texto de los enlaces un número y al final del mensaje la lista de esos enlaces, cada uno asociado al número correspondiente. 

Esto fue lo que decidí hacer para publicar en la [página de Facebook de fernand0.github.io](https://www.facebook.com/fernand0.github.io) (y otras, claro). El programa que traemos hoy hace justamente eso, como paso previo a la publicación en la página de Facebook (y, tal vez, ¿para poder enviar las entradas por correo a los interesados?).

El programa puede verse en [rssToLinks.py](https://github.com/fernand0/scripts/blob/8788002216df672393b5c1e63f9cea0c78a2beca/rssToLinks.py) (apuntamos, como siempre, la versión actual por si hubiera cambios en algún momento).

Algunas formas de extraer los enlaces serían: buscarlos con expresiones regulares, o también con algún parser de HTML (en el [Blogómetro](http://blogometro.sourceforge.net/) hace años utilizábamos el [Simple SGML parser](https://docs.python.org/2/library/sgmllib.html).
Buscando un poco encontré el proyecto [Beautiful Soup](http://www.crummy.com/software/BeautifulSoup/) que presume de ser una manera rápida de recorrer el contenido de una página web y decidí darle una oportunidad.

Para utilizarlo incluímos los módulos necesarios. Para obtener el contenido utilizamos la fuente RSS, así que también necesitaremos `feedparser`:
{% highlight python %}
import feedparser
from bs4 import BeautifulSoup
from bs4 import NavigableString
from bs4 import Tag
{% endhighlight %}

Leemos la fuente RSS y vamos recorriendo las entradas:
{% highlight python %}
feed = feedparser.parse(url)

for i in range(len(feed.entries)):
{% endhighlight %}

Y empieza la 'magia' de `Beautiful Soup`:
{% highlight python %}
        soup = BeautifulSoup(feed.entries[i].summary)
        links = soup("a")
{% endhighlight %}

Esto es, le pasamos los datos al analizador, y lanzamos la pregunta de lo que queremos extraer. En este caso tenemos una entrada en el `summary` y queremos obtener los enlaces (etiqueta `a`) para la entrada que ocupa la posición `i`. 
Nos devolverá una lista de elementos html que incluyen dicha etiqueta.

En algunas entradas ponemos imágenes, que no queremos que aparezcan en el texto, así que utilizamos `isinstance` para comprobar si dentro del contenido del enlace hay otra etiqueta para evitarla (¿es posible que encontremos algún caso más adelante que sea problemático?). Recorremos la lista de enlaces (que vienen con las etiquetas y todo, claro). Ademas utilizamos el contador `j` para ir asociándoles números a los sucesivos enlaces (en el HTML original, todavía no lo hemos eliminado):
{% highlight python %}
	j = 0
	linksTxt = ""
	for link in links:
		if not isinstance(link.contents[0], Tag):
			# We want to avoid embdeded tags (mainly <img ... )
			link.append(" ["+str(j)+"]")
			j =  j + 1
{% endhighlight %}

El contenido del enlace (ahora que ya sabemos que no es una etiqueta HTML) estará en `link.contents[0]` (puede haber más contenido, nuestros enlaces suelen ser 'sencillos'). 
{% highlight python %}
	linksTxt = linksTxt + "["+str(j)+"] " + link.contents[0] + "\n"
{% endhighlight %}

El enlace está en `link['href']`.
{% highlight python %}
	linksTxt = linksTxt + "    " + link['href'] + "\n"
{% endhighlight %}

Ahora necesitamos el texto del HTML:
{% highlight python %}
	print soup.get_text()
{% endhighlight %}

En algunos casos el texto puede tener muchos saltos de línea, espacios, ... Se podrían eliminar. Nuestras entradas suelen estar bien estructuradas y no aparece ese problema.

Ahora, si había algún enlace (¿publicaremos alguna vez una entrada sin ningún enlace?), lo añadimos al final:
{% highlight python %}
	if linksTxt != "":
		print
		print "Links :"
		print linksTxt
{% endhighlight %}
