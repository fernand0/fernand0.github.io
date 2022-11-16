---
layout: post
title: "Publicar en Twitter las entradas de este sitio usando Python"
date: "Sun Dec 07 21:30:01 +0100 2014"
category: programación
tags: programación desarrollo twitter rss redes sociales difusión python
---

No creo que el RSS esté muerto. Pero vemos que mucha gente prefiere recibir información a través de los sitios de redes sociales. Hasta publicaba lo que aparece en mis blogs utilizando servicios como [IFTT](http://ifttt.com/) y [dlvr.it](http://dlvr.it/). 
Son bastante cómodos y funcionan muy bien. Sin embargo, uno siempre se pregunta si podría hacerse unos programas a medida que nos permitan gestionar esa parte de la publicación y aprender un poco de paso.

Empecé con la publicación en páginas de Facebook pero todavía no estoy satisfecho del resultado así que hablaremos primero de Twitter: al fin y al cabo sólo tenemos que publicar el título de la entrada y el enlace (y, tal vez, algún texto introductorio).

Encontré el proyecto [twitter](https://pypi.python.org/pypi/twitter) que ya tiene una parte importante del trabajo realizada. Podemos instalarla con pip:

{% highlight bash %}
fernand0@aqui:~$ sudo pip install twitter
{% endhighlight %}

Para su correcto funcionamiento necesita `BeautifulSoup` y tal vez algunos módulos más. Si no están instalados en nuestro sistema, recibiremos las 'quejas' correspondientes.

Después podemos ejecutarlo. 
Nos vendrá bien porque necesitamos autentificarnos en Twitter y el programita que he preparado no se ocupa de esta parte. Hace no tanto se podía leer y escribir tuits simplente con el usuario y la contraseña pero Twitter decidió pasarse a un sistema de autentificación más sofisticado basado en [OAuth](http://oauth.net/).

{% highlight bash %}
fernand0@aqui:~$ twitter
{% endhighlight %}

Cuando hacemos esto se lanza el navegador para que nos autentifiquemos y demos permiso a la aplicación para actuar en nuestro nombre. Esto genera los tokens adecuados de identificación/autenticación, que se almacenan en `~/.twitter_oauth` (en un sistema de tipo Unix, se agradecerán comentarios sobre otros sistemas) que podremos reutilizar en nuestro programita.


El programa es muy sencillo, se puede descargar en [rssToTwitter.py V.2014-12-07](https://github.com/fernand0/scripts/blob/6cf31041196b4c3149f9e595a34fa605208b2a78/rssToTwitter.py) (enlazo a la versión actual por si en el futuro hago algún cambio).

Empezamos leyendo la configuración:

{% highlight python %}
config = ConfigParser.ConfigParser()

config.read([os.path.expanduser('~/.rssBlogs')])
rssFeed = config.get("Blog1", "rssFeed")
twitterAc = config.get("Blog1", "twitterAc")
{% endhighlight %}

Esta configuración debe contener una sección por blog (este programa sólo utiliza la configuración del primero) y para cada uno de ellos contendrá la fuente RSS, el nombre de la cuenta de Twitter y el nombre de la cuenta de Facebook. Para este sitio tendría el siguiente aspecto:


	[Blog1]
	rssFeed:http://fernand0.github.io/feed.xml
	twitterAc:mbpfernand0
	pageFB:fernand0.github.io


Este programa no utiliza la página de Facebook, claro.
Por otro lado, también hay que leer la configuración para Twitter:

{% highlight python %}
config.read([os.path.expanduser('~/.rssTwitter')])
CONSUMER_KEY = config.get("appKeys", "CONSUMER_KEY")
CONSUMER_SECRET = config.get("appKeys", "CONSUMER_SECRET")
TOKEN_KEY = config.get(twitterAc, "TOKEN_KEY")
TOKEN_SECRET = config.get(twitterAc, "TOKEN_SECRET")
{% endhighlight %}

Allí aparecen los datos de la aplicación (los podemos copiar directamente de la que nos hemos instalado; en mi sistema están en `/usr/local/lib/python2.7/dist-packages/twitter/cmdline.py` y los tokens estarán en el fichero `~/.twitter_oauth`

El fichero de configuración tiene este aspecto en este caso:

	[appKeys]
	CONSUMER_KEY:xxxxxxxxxxxxxxxxxxxxxx
	CONSUMER_SECRET:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
	[mbpfernand0]
	TOKEN_KEY:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
	TOKEN_SECRET:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

Podría haber más cuentas de Twitter, si se desea. Nótese que el nombre de la segunda sección corresponde con el que se ha utilizado en el fichero de configuración anterior.

A continuación leemos la fuente RSS para extraer los datos que nos interesan:

{% highlight python %}
feed = feedparser.parse(rssFeed)

i = 0 # It will publish the last added item

soup = BeautifulSoup(feed.entries[i].title)
theTitle = soup.get_text()
theLink = feed.entries[i].link
{% endhighlight %}

Lo primero de todo, utilizamos `feedparser` para decargar la fuente RSS y procesarla.

Elegimos la entrada que ocupa la primera posición (la 0), que será la última publicada. Para Twitter seleccionamos el título y el enlace.
El título lo procesamos con BeautifulSoup para evitar las posibles etiquetas que pueda contener (de estilo, entidades HTML, ...) 

Finalmente, construimos el tuit:

{% highlight python %}
statusTxt = "Publicado: "+theTitle+" "+theLink
{% endhighlight %}

Nos identificamos, autentificamos y publicamos:

{% highlight python %}
t = Twitter(
	auth=OAuth(TOKEN_KEY, TOKEN_SECRET, CONSUMER_KEY, CONSUMER_SECRET))

t.statuses.update(status=statusTxt)
{% endhighlight %}

