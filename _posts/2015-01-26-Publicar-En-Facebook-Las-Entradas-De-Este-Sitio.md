---
layout: post
title: "Publicar en Facebook las entradas de este sitio usando Python"
date: "Mon Jan 26 13:30:01 +0100 2015"
category: programación
tags: programación desarrollo facebook rss redes sociales difusión python api
---



<a href="https://plus.google.com/112862240851570159916/posts/Ps9VHx71gCW" title="Enlaces"><img src="https://lh3.googleusercontent.com/-IVdMXNs-UyE/VLK46RXRP1I/AAAAAAAAJ7E/rvp7ZzTOy4I/w521-h423-no/2015-01-11-FacebookPage.png" width="240"  alt="Enlaces en Página de Facebook" style="float:left; margin:5px"></a>

Ya anticipamos esta entrada hace un par de semanas en [Extraer enlaces de una página web](http://fernand0.github.io/Extraer-Enlaces-De-Una-Pagina-Web/). Allí hablábamos de formatear una entrada de este sitio (u otro que proporcione RSS) para publicarla en Facebook (o donde nos parezca, claro). 
También en [Publicar en Twitter las entradas de este sitio usando Python](http://fernand0.github.io/publicar-en-twitter-las-entradas-de-este-sitio/) vimos algunas ideas sobre este tema, entonces para Twitter. 

En este caso utilizamos el [API oficial de Facebook](https://developers.facebook.com/) y un paquete no oficial que la implenenta en Python, [Facebook Python SDK](https://github.com/pythonforfacebook/facebook-sdk). 

Podemos instalarlo 

{% highlight bash %}
fernand0@aqui:~$ sudo pip install facebook-sdk
{% endhighlight %}

Para su correcto funcionamiento necesita `BeautifulSoup` y `requests` y tal vez algunos módulos más. Si no están instalados en nuestro sistema, recibiremos las 'quejas' correspondientes.

Para obtener las credenciales tenemos que registrar nuestra aplicación en [Facebook My Apps](https://developers.facebook.com/apps/). Hace falta ir al menú avanzado (es más fácil registrar aplicaciones web, la verdad) y se nos asignarán algunos identificadores  (fundamentalmente el token OAUTH, que podemos mirar en `https://developers.facebook.com/tools/explorer/APPID/?method=GET&path=me%3Ffields%3Did%2Cname&version=v2.2`, donde APPID es el que nos hayan asignado), que en nuestro caso almacenamos en  `~/.rssFacebook` y leeremos desde el programa.

El programa es muy sencillo, se puede descargar en [rssToPages.py V.2015-01-26](https://github.com/fernand0/scripts/blob/a29e021e9b73378ae554411c1e5117beccc50b26/rssToPages.py) (enlazo a la versión actual por si en el futuro hago algún cambio).  

Como decíamos arriba, empezamos leyendo la configuración relativa a los blogs de los que queremos leer para elegir uno. Si sólo hubiera uno se elegiría directamente: 

{% highlight python %}
config = ConfigParser.ConfigParser()

config.read([os.path.expanduser('~/.rssBlogs')])

print "Configured blogs:"

i=1
for section in config.sections():
	print str(i), ')', section, config.get(section, "rssFeed")
	i = i + 1

if (int(i)>1):
	i = raw_input ('Select one: ')
else:
	i = 1

print "You have chosen ", config.get("Blog"+str(i), "rssFeed")
{% endhighlight %}


Esta configuración debe contener una sección por blog y para cada uno de ellos contendrá la fuente RSS, el nombre de la cuenta de Twitter y el nombre de la cuenta de Facebook. Para este sitio tendría el siguiente aspecto:


	[Blog1]
	rssFeed:http://fernand0.github.io/feed.xml
	twitterAc:mbpfernand0
	pageFB:fernand0.github.io

También puede contener un campo más, `linksToAvoid` que se usa en el programa de extraer los enlaces para evitar algunos de ellos (lo uso en otro blog para eliminar los enlaces a las categorías).

{% highlight python %}
if (config.has_option("Blog"+str(i), "linksToAvoid")):
	linksToAvoid = config.get("Blog"+str(i), "linksToAvoid")
else:
	linksToAvoid = ""
{% endhighlight %}

Leemos la última entrada del blog y extraemos el texto y los enlaces de manera similar a como hacíamos en [Extraer enlaces de una página web](http://fernand0.github.io/Extraer-Enlaces-De-Una-Pagina-Web/).  

Y para evitar los enlaces que no queríamos a la hora de generar el contenido de la página:

{% highlight python %}
		print linksToAvoid
		print re.escape(linksToAvoid)
		print str(link['href'])
		print re.search(linksToAvoid, link['href'])
		if ((linksToAvoid =="") 
			or (not re.search(linksToAvoid, link['href']))):
			link.append(" ["+str(j)+"]")
			linksTxt = linksTxt + "["+str(j)+"] " + link.contents[0] + "\n"
			linksTxt = linksTxt + "    " + link['href'] + "\n"
			j =  j + 1
{% endhighlight %}

Finalmente, buscamos si la entrada contiene alguna imagen. Si no la hay no pondremos nada, pero Facebook lo hará su cuenta (puede ser nuestra foto, un botón, lo primero que haya). 
Tal vez podríamos configurar una por defecto cuando nuestra entrada no tenga una, si no nos gusta la que sale por defecto (en mi caso es mi foto; como no me gusta verla allí esto me obliga siempre a pensar en una foto para el post):

{% highlight python %}
pageImage = soup.findAll("img")
#  Only the first one
if len(pageImage) > 0:
	imageLink = (pageImage[0]["src"])
else:
	imageLine = ""
{% endhighlight %}

Leemos la configuración para Facebook y empezamos a trabajar, solicitando la lista de páginas de las que somos administradores (el nombre de la página en la que queremos publicar lo habremos puesto en `~/.rssBlogs`):

{% highlight python %}
config.read([os.path.expanduser('~/.rssFacebook')])
oauth_access_token= config.get("Facebook", "oauth_access_token")

graph = facebook.GraphAPI(oauth_access_token)
pages = graph.get_connections("me", "accounts")
{% endhighlight %}

El fichero de configuración tiene este aspecto en este caso:

	[Facebook]
	oauth_access_token:XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

Podría haber más cuentas de Facebook, pero no lo he probado así que no garantizo que todo vaya a funcionar correctamente. 

De las páginas que gestionamos se elige la que queremos (que se pone en el apartado de configuración del blog, `~/.rssBlogs`).

{% highlight python %}
for i in range(len(pages['data'])):
	if (pages['data'][i]['name'] == pageFB):
		print "Writing in... ", pages['data'][i]['name']
		graph2 = facebook.GraphAPI(pages['data'][i]['access_token'])
		graph2.put_object(pages['data'][i]['id'], 
			"feed", message = theSummary, link=theLink, 
			picture = imageLink, 
			name=theTitle, caption='',
			description=theSummary.encode('utf-8'))

statusTxt = "Publicado: "+theTitle+" "+theLink
{% endhighlight %}

Ya llevo más de un mes probando con un par de blogs y la solución parece que funciona bastante bien. Lo más molesto fue conseguir las credenciales y dar de alta la aplicación (con un 'falso' paso a producción; falso porque no la usa nadie más, al ser de escritorio).

Dudas, comenarios, ideas... ¡Hazme un `pull request` o un `issue`!
 
