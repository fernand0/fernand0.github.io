---
layout: post
title: "Control de versiones desde Python"
date: "Sat Jan 23 18:35:01 +0100 2016"
category: programación
tags: [programación, python, correo, IMAP, sieve, sievelib, filtrado, scripts, código, git, versiones]
---




<a href="https://www.flickr.com/photos/fernand0/5543104159" title="Pantalla y fichas"><img src="https://c2.staticflickr.com/6/5059/5543104159_98fb5c9008_m.jpg" width="240"  alt="Pantalla y fichas" style="float:left; margin:5px"></a>
Aunque el sistema de filtros que introdujimos en [Añadiendo filtros de correo a mi sistema con sievelib](http://fernand0.github.io/Gestionando-Los-Filtros-Correo/) ha seguido evolucionando con varias características hoy quería traer aquí una que me preocupaba un poco: si vamos añadiendo reglas es bastante probable que en algún momento nos equivoquemos y añadamos alguna errónea. Como además estamos utilizando un sistema que controla los filtros también podría ocurrir que una actualización sobre-escriba las reglas que hayamos creado. 
La solución adoptada era guardar la historia de los cambios. Pero queríamos ir un poco más allá: ¿tendría sentido gestionar el histórico con un sistema de control de versiones? ¿Sería posible hacerlo?

Buscando encontramos [GitPython](http://gitpython.readthedocs.org/en/stable/tutorial.html) que nos proporcionaba una interfaz adecuada para lo que estábamos plateando. El código completo en su estado actual se puede ver en [addToSieve.py](https://github.com/fernand0/scripts/blob/6e0364239b7802d34adb45a365f6c3b36888c271/addToSieve.py) y nos vamos a dedicar a su parte final. Aviso: el resto del código no está muy bien organizado pero funciona razonablemente bien en mi día a día.

Hay que declarar el módulo:

{% highlight python %}
from git import Repo
{% endhighlight %}

Al final, cuando ya hemos actualizado las reglas las pasamos al sistema de control de versiones. Instanciamos un repositorio con nuestro directorio de copias de seguridad. `repoDir` es una cadena de texto que contiene el directorio de trabajo (en mi caso es `~/Documents/config` donde guardo varias configuraciones con control de versiones).

{% highlight python %}
	repo = Repo(repoDir)
	index = repo.index
{% endhighlight %}

Elegimos el fichero de reglas que acabamos de grabar, lo almacenamos en el fichero que estamos utilizando (en mi caso se llama `sogo.sieve`, añadimos todos los ficheros del directorio al repositorio y hacemos el `commit` (con el nombre y la fecha como mensaje):

{% highlight python %}	
	sieveFile=c.getscript('sogo')
	file=open(repoDir+repoFile,'w')
	file.write(sieveFile)
	file.close()
	index.add(['*'])
	index.commit(name+'sogo')
{% endhighlight %}

Finalmente borraremos del servidor algunos filtros almacenados, dejando los últimos cinco nada más.
No se hace el `push` dentro del programa para evitar el tener que teclear otra contraseña y no parece necesario.

Buscando otros proyectos he visto que en [history.py](https://github.com/marcwebbie/passpie/blob/master/passpie/history.py) hacen algo parecido en un programa de gestión de contraseñas que estoy probando, [passpie](https://github.com/marcwebbie/passpie).
