---
layout: post
title: "Jugando con IMAP en Python"
date: "Sun Dec 06 12:25:01 +0100 2015"
category: programación
tags: [programación, python, correo, IMAP, scripts, código, threading]
---




<a href="https://www.flickr.com/photos/fernand0/415859306" title="Hilos"><img src="https://c1.staticflickr.com/1/52/415859306_e77c449fd3_m.jpg" width="240"  alt="Hilos" style="float:left; margin:5px"></a>
Hace no mucho parecía que [POP](https://es.wikipedia.org/wiki/Post_Office_Protocol) iba a ser el protocolo preferido para el correo. Sin embargo, con la movilidad permanente y la necesidad de consultar nuestro correo en cualquier parte parece que todo ha cambiado y las soluciones preferidas son los sistemas de correo basados en proveedores con sus aplicaciones (y típicamente su reflejo en *webmail* para el escritorio. Si nuestro proveedor no tiene aplicación, parece que la solución más adecuada es el [IMAP](https://es.wikipedia.org/wiki/Internet_Message_Access_Protocol). 
POP estaba orientado a la descarga, e IMAP estaba pensando para que el correo permaneciera en el servidor y se accediera a él mediante conexión.

A mi me gusta seguir [viviendo la ficción](https://mako.cc/copyrighteous/google-has-most-of-my-email-because-it-has-all-of-yours) de que una parte de mi correo es más o menos privada y eso pasa por usar los servidores del trabajo (o de un proveedor privado) con algunos inconvenientes: por un lado, malas herramientas de filtrado y gestión del correo; por otra parte, limitaciones en el espacio (todavía hay otra, y es la capacidad de buscar que pude solucionar -más o menos- con [mairix](https://github.com/rc0/mairix)).

Estas limitaciones me llevaron a montar un servidorcillo de correo (lo que viene llamándose en los últimos tiempos [hacer un Hillary Clinton](https://en.wikipedia.org/wiki/Hillary_Clinton_email_controversy)). Empecé montando los servicios por mi cuenta hasta que probé [Zentyal](http://www.zentyal.com/) que no es exactamente lo que necesito (tiene muchas más cosas y está pensada para algo más grande, pero me libera de algunas tareas de gestión). Miro con simpatía iniciativas como [mailinabox](https://github.com/mail-in-a-box/mailinabox) o el fallido -por ahora- [ownmailbox](https://www.own-mailbox.com/).
Zentyal me proporciona un sistema con [SOGo](http://www.sogo.nu/), [Dovecot](http://www.dovecot.org/), filtrado (pronto, espero, otra entrada específica sobre el tema), antispam (no va demasiado bien, al menos en mi experiencia) y algunas herramientas más.

De todas formas, lo que quiero presentar hoy aquí puede ser de utilidad para cualquier cuenta de correo. Se trata de borrar algunos mensajes de una carpeta IMAP basado en reglas sencillas: en nuestro caso, recibimos mensajes de diversas tareas de cron que repetitivamente (sobre todo cuando todo va bien) llegan a nuestro correo. Lo que haremos será recorrer las carpetas donde se reciben las copias de seguridad y borrarlas.

La primera tarea es buscar un poco para ver si existe algún proyecto que nos ayude en la tarea de programación. Python incluye la [imaplib](https://docs.python.org/2/library/imaplib.html) que permite hacer las tareas necesarias. El proceso será:

1. Leer la configuración de las cuentas que vamos a examinar
2. Solicitar las contraseñas
3. Seleccionar los mensajes y borrarlos

Además, para añadirle un poco de gracia a la cosa hemos añadido un uso muy básico de [threading](https://docs.python.org/2/library/threading.html) de manera que se hace el borrado de manera concurrente en las cuentas que haya configuradas. 
El código de la versión actual del programita se puede encontrar en [deleteCronMesgs.py](https://github.com/fernand0/scripts/blob/7aea007e0acf0daf9e15284d9c4f288481ef3532/deleteCronMsgs.py).

 
Comenzamos leyendo la configuración

{% highlight python %}
config = ConfigParser.ConfigParser()
config.read([os.path.expanduser('~/IMAP.cfg')])
{% endhighlight %}

En este fichero está la información de las cuentas de correo, tantas como sea necesario:

{% highlight python %}
[IMAP1]
server:imap.server.com
user:myAccount@server.com
[IMAP2]
server:imap.otherServer.com
user:myUsername
{% endhighlight %}

Ahora recorremos las cuentas configuradas y pedimos la contraseña (se podrían poner también en el fichero de configuración pero no termino de sentirme confortable con eso)

{% highlight python %}
for section in config.sections():
	SERVER = config.get(section, 'server')
	USER   = config.get(section, 'user')

	print SERVER
	PASSWORD = getpass.getpass()
{% endhighlight %}

El código para borrar los mensajes se encuentra en la función `mailFolder` y para ello realiza los siguientes pasos:

Primero nos conectamos al servidor, con los datos leídos del fichero de configuración y del teclado.

{% highlight python %}
	M = imaplib.IMAP4_SSL(SERVER)
	M.login(USER , password)
{% endhighlight %}

Seleccionamos la carpeta sobre la que vamos a trabajar (en este caso el INBOX) y en ella buscamos los mensajes que nos interesan (los que contienen la cadena 'Cron Daemon' en el campo 'FROM'):

{% highlight python %}
	M.select()
	typ,data = M.search(None,'FROM', 'Cron Daemon')
{% endhighlight %}

En `search` se devuelven dos valores, el estado (¿ha ido todo bien?) y una lista que contiene una cadena de caracteres con los números que identifican a los mensajes que cumplen las condiciones de búsqueda.

Ahora, para borrarlos recorremos la lista y actualizamos la marca (`flag`) para que refleje la condición de borrado:

{% highlight python %}
	if data[0]: 
		for num in data[0].split():
			M.store(num, '+FLAGS', '\\Deleted')
{% endhighlight %}

Además hemos incluido código para ir contando cuántos mensajes borramos y mostrar una actualización cada diez (que no mostramos aquí).
Finalmente, cerramos la conexión y terminamos:


{% highlight python %}
	M.close()
	M.logout()
{% endhighlight %}

La parte concurrente es muy sencilla, consta de tres pasos.

Para cada cuenta de correo se crea un hilo:

{% highlight python %}
	t = threading.Thread(target=mailFolder, args=(SERVER, USER, PASSWORD,space*i))
{% endhighlight %}

En `target` está la función que se ejecutará cuando se active el hilo y en `args` los parámetros de esa función.

Ahora acivamos los hilos (hemos separado la creación de la activación para que no haya interferencias de la salida que refleja la actividad con la entrada; podríamos prescindir de la realmientación y lanzarlas sobre la marcha):

{% highlight python %}
for t in threads:
	t.start()
{% endhighlight %}

Finalmente, necesitamos esperar a que terminen los hilos, con un par de instrucciones como:

{% highlight python %}
for t in threads:
	t.join()
{% endhighlight %}

Siguientes pasos: no tengo claro que el código de los hilos vaya a sobrevivir. Estuvo bien recordar un poquito (¡muy poquito!) de concurrencia pero en este caso no tiene demasiado interés. Tendría sentido poder incluir más reglas de borrado para otros mensajes e incluirlo en la configuración en lugar de en el propio código (por ejemplo, una lista de cademas para buscar o incluso algo más sofisticado). 

También me gustaría explorar sistemas alternativos de autentificación (GMail permite utilizar OAuth, si no me equivoco). Como mínimo, poder tener la contraseña cifrada en el fichero de configuración y tener sólo una contraseña manestra.

¿Ideas? ¿Comentarios? Estaremos escuchando en [@mbpfernand0](http://twitter.com/mbpfernand0) o en [@fernand0](http://twitter.com/fernand0).

**Actualización (2015-12-07)** quise terminar esta entrada rápido y olvidé otro ejemplo que tengo a mano. En este caso se trataría de borrar basado en el contenido. Recibimos ciertos mensajes repetidos que querríamos eliminar de nuestras coias de seguridad. Para examinar el contenido de los mensajes utilizaríamos:

{% highlight python %}
	typ, data = M.fetch(num, '(BODY.PEEK[TEXT])')
{% endhighlight %}

Para determinar si el mensaje en cuestión es repetido, calculamos el `hash` (que tenemos precalculado) y lo comparamos:

{% highlight python %}
	m = hashlib.md5()
	m.update(data[0][1])	
	if (binascii.hexlify(m.digest())==HASH):
		M.store(num, '+FLAGS', '\\Deleted')
		i = i + 1
{% endhighlight %}
