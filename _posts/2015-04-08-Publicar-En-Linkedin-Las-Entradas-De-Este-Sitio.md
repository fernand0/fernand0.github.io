---
layout: post
title: "Publicar en Linkedin las entradas de este sitio usando Python"
date: "Wed Apr 08 17:45:01 +0100 2015"
category: programación
tags: programación desarrollolinkedin rss redes sociales difusión python api
---



Seguimos tratando de difundir el contenido de este sitio en diferentes redes sociales. Me da la impresión de que Google no presta demasiada atención a estos blogs (tampoco estoy muy seguro de que nadie fuera a buscar esto, en cualquier caso) pero sí que creo que se les puede dar (algo de) visibilidad en diferentes redes sociales.

Ya hicimos el acercamiento a Twitter ([Publicar en Twitter las entradas de este sitio usando Python](http://fernand0.github.io/publicar-en-twitter-las-entradas-de-este-sitio/)) y Facebook ([Publicar en Facebook las entradas de este sitio usando Python](http://fernand0.github.io/Publicar-En-Facebook-Las-Entradas-De-Este-Sitio/)). 

<a href="https://plus.google.com/u/1/112862240851570159916/posts/Sn8MeNeD53T" title="El resultado en LinkedIn"><img src="https://lh3.googleusercontent.com/-FoV-EJ9o5QA/VSVJJVPyt1I/AAAAAAAAKFU/tuSWqyDzXtc/w506-h900/15%2B-%2B1" width="240"  alt="Enlaces en Página de Facebook" style="float:left; margin:5px"></a>


Suelo compartir en Linkedin (y en los otros sitios) entradas de mi bitácora de enlaces, [Notas Rápidas](http://fernand0.tumblr.com/). Normalmente se trata de información que voy viendo por ahí; muchas veces la pongo incluso antes de leerla. De vez en cuando, alguien comenta, re-comparte... 
Pensé que también tendría sentido publicar allí lo que voy poniendo en mis blogs. 

LinkedIn  utiliza Oauth para la autentificación. En la sección de [desarrolladores](https://developer.linkedin.com/) explican estas cosas y en [Share on Linkedin](https://developer.linkedin.com/docs/share-on-linkedin) explican la parte de publicar allí. En [Authenticating with OAuth 2.0](Authenticating with OAuth 2.0) nos indican qué cosas hay que configurar: dar de alta la aplicación en nuestro espacio de trabajo, lo que generará las correspondientes "API Key" y "Secret Key" y también los tokens "OAuth 1.0a User Token" y "OAuth 1.0a User Secret" que podremos incluir en nuestro programa (esto es, por ahora no necesitamos utilizar los tokens de la versión 2 de OAuth). 
También podríamos pasar por el proceso de autorización con el programita (que es algo que no he hecho) o bien utilizar las herramientas que nos proporcionan otros.

Una búsqueda rápida de algún módulo para interactuar con LinkedIn en Python nos conduce a [python-linkedin](https://github.com/ozgur/python-linkedin).

Con este módulo todo se parece a los programas que hemos hecho en otras ocasiones (y me saltaré los detalles aquí). Se puede ver el código en su versión actual en [rssToLinkedin.py](https://github.com/fernand0/scripts/blob/201c7bd6a48f6c1c8ce14dc3c12518ae7c3bef3f/rssToLinkedin.py).

* Se leen los blogs que estén configurados (igual que otras veces) y se selecciona uno para publicar. 
* Se obtiene el título, el contenido y el enlace de la última entrada. 

Una nota para el contenido: LinkedIn tiene límites sobre lo que se puede poner (actualmente 700 caracteres), así que hay que tener cuidado. Reservamos 7 caracteres para indicar que el texto sólo es un resumen. 

{% highlight python %}
print theSummary.encode('utf-8')[0:693].rsplit(' ', 1)[0]+" [...]"
{% endhighlight %}

* Luego se busca una imagen y se incluye si la hay.

A partir de aquí comienza el proceso de autentificación:

{% highlight python %}
authentication = linkedin.LinkedInDeveloperAuthentication(
			config.get("Linkedin", "CONSUMER_KEY"),
			config.get("Linkedin", "CONSUMER_SECRET"),
			config.get("Linkedin", "USER_TOKEN"),
			config.get("Linkedin", "USER_SECRET"),
			config.get("Linkedin", "RETURN_URL"),
			linkedin.PERMISSIONS.enums.values())
{% endhighlight %}

Seguidamente ponemos un texto (en mi caso 'Publicado') a modo de introducción y luego publicaremos el resto:

{% highlight python %}
comment='Publicado!'

application.submit_share(comment, theTitle, theSummary, theLink, imageLink)
{% endhighlight %}

Con el trabajo desarrollado para los programas anteriores lo que hay que hacer aquí es simplemente utilizar el método adecuados para publicar.

Siguientes pasos: tengo tres programas para publicar en diferentes redes sociales y me pregunto si debería unificarlos para utilizar las partes comunes (esencialmente selección del blog porque el resto tiene pequeñas diferencias), o pensar en una mejor organización. 

Pero esto será algo para pensar más adelante.
