---
layout: post
title: "Añadiendo filtros de correo a mi sistema con sievelib"
date: "Sun Dec 13 19:35:01 +0100 2015"
category: programación
tags: [programación, python, correo, IMAP, sieve, sievelib, filtrado, scripts, código]
---




<a href="https://www.flickr.com/photos/fernand0/3699265044" title="Laberinto"><img src="https://c1.staticflickr.com/3/2424/3699265044_962fae8d8d_m.jpg" width="240"  alt="Laberinto" style="float:left; margin:5px"></a>
Otra tarea importante que necesitamos en el correo es el filtrado: tener en nuestra carpeta principal sólo los mensajes que pueden ser importantes y llevar a otras carpetas secundarias otros avisos, como mensajes de listas de correo y cosas así. A veces es bueno apartar algunos mensajes importantes que no podemos atender cuando estamos fuera de la oficina: cuando volvamos a lo mejor ya no los vemos como nuevos y no les dedicaremos la atención necesaria.

Como decíamos el otro día el sistema se basa en Zentyal, que incorpora un sistema de filtrado de correo (mediante el webmail y los filtros basados en el protocolo ManageSieve). 
El problema (para mi) es que no soy usuario habitual del correo web porque prefiero otros clientes y no me resultaba cómodo tener que lanzarlo para añadir un filtro, así que anduve investigando para averiguar si se podría utilizar alguna alternativa.
Mi opción preferida es un programa de línea de instrucciones.

Encontré  [sievelib](https://pypi.python.org/pypi/sievelib) y estuve haciendo algunas pruebas.
No estoy seguro de haber manejado adecuadamente la biblioteca: yo utilizo básicamente dos tipos de reglas, las de almacenar en alguna carpeta concreta, y las de redigir a otra cuenta de correo (por ejemplo 'newsletters' en html que se leen mejor en GMail -del que también soy usuario). Por este motivo, sólo me he concentrado en estas reglas y ni siquiera estoy seguro de haberlo hecho en toda su generalidad.
El resultado está en [addToSieve.py](https://github.com/fernand0/scripts/blob/27e3face16c6d2279cfd6e6d46e034f2be5a9e04/addToSieve.py) en el estado de la versión que se comenta aquí.

El servidor de correo almacena las reglas en ficheros y hace una pequeña gestión que le permite saber cuál de ellos está activo, así que hay que conectarse e identificarse y autentificarse. Habremos leído los datos de configuración de manera análoga a cómo hacíamos con el servidor IMAP como veíamos en [Jugando con IMAP en Python](http://fernand0.github.io/Jugando-con-IMAP-En-Python/) y seleccionar el 'script' que queremos modificar y analizarlo:


{% highlight python %}
from sievelib.managesieve import Client

...

        c = Client(SERVER)
        c.connect(USER,PASSWORD, starttls=True, authmech="PLAIN")

...

        script = c.getscript('sogo')
        p = Parser()
        p.parse(script)
{% endhighlight %}

Para crear la regla vamos a basarnos en el mensaje que queremos filtrar. Mostramos los 15 mensajes más recientes y el usuario elije uno de ellos:

{% highlight python %}
def selectMessage(M):
	M.select()
	data=M.sort('ARRIVAL', 'UTF-8', 'ALL')
	if (data[0]=='OK'):
		j=0
		msg_data=[]
		messages=data[1][0].split(' ')
		for i in messages[-15:]:
			typ, msg_data_fetch = M.fetch(i, '(BODY.PEEK[HEADER.FIELDS (From Sender To Subject List-Id)])')
			for response_part in msg_data_fetch:
				if isinstance(response_part, tuple):
					msg = email.message_from_string(response_part[1])
					msg_data.append(msg)
					print "%2d) %4s %20s %40s" %(j,i,msg['From'][:20],msg['Subject'][:40])
					j=j+1
		msg_number = raw_input("Which message? ")
		return msg_data[int(msg_number)] #messages[-10+int(msg_number)-1]
	else:	
		return 0
{% endhighlight %}

Creo que no hay mucho que comentar en este código, simplemente ordenamos los mensajes por orden de llegada y mostramos algunos campos de los 15 últimos (utilizamos `BODY.PEEK` para que no se marquen como leídos los mensajes que no lo estuvieran). Para extraer las cabeceras relevantes se utiliza `email.message_from_string`. Si todo va bien, devolvemos el mensaje `return msg_data[int(msg_number)]`.

Ahora que sabemos qué mensaje vamos a utilizar para el filtrado elegimos qué cabecera es la que utilizaremos para filtrar

{% highlight python %}
	(keyword, textHeader) = selectHeaderAuto(M, msg)
{% endhighlight %}

Nos interesan las siguientes cabeceras (al menos por ahora, esto puede ir evolucionando):


{% highlight python %}
msgHeaders=['List-Id', 'From', 'Sender','Subject','To', 'X-Original-To']
{% endhighlight %}

Además prefiero filtrar por `List-Id` siempre que sea posible, así que en `selectHeaderAuto` tenemos:

{% highlight python %}	
if msg.has_key('List-Id'): 
		return ('List-Id', msg['List-Id'][msg['List-Id'].find('<')+1:-1])
{% endhighlight %}

Notar que hemos 'limpiado' el contenido para eliminar todo lo que hay antes y después de los ángulos.
En caso de que no tenga esta cabecera, mostramos las otras con este código, que tiene en cuenta que algunas de ellas pueden no estar presentes:

{% highlight python %}	
		for header in msgHeaders:
			if msg.has_key(header):
				print i," ) ", header, msg[header]
			i = i + 1
		header_num=raw_input("Select header: ")
		
{% endhighlight %}

Tomamos la cabecera y el texto correspondiente:

{% highlight python %}	
		header=msgHeaders[int(header_num)-1]
		textHeader=msg[msgHeaders[int(header_num)-1]]
{% endhighlight %}

Y ahora lo limpiamos (si es una dirección de correo contendrá ángulos, y si es un asunto 'Subject' a veces contiene corchetes, que también nos pueden venir bien para filtrar).


{% highlight python %}	
		pos = textHeader.find('<')
		if (pos>=0):
			textHeader=textHeader[pos+1:textHeader.find('>',pos+1)]
		else:
			pos = textHeader.find('[')
			textHeader=textHeader[pos+1:textHeader.find(']',pos+1)]

		pos = textHeader.find('<')
		if (pos>=0):
			textHeader=textHeader[pos+1:textHeader.find('>',pos+1)]
		else:
			pos = textHeader.find('[')
			textHeader=textHeader[pos+1:textHeader.find(']',pos+1)]
		return (header, textHeader)
{% endhighlight %}

Con estas cabeceras ahora tenemos que decidir la acción que realizaremos con los mensajes que coindidan con las cabeceras seleccionadas. De esto se ocupa la función `selectAction`. Esta función nos ofrece como acciones posibles las que ya tengamos en los filtros (carpetas que ya hemos utilizado, `sievelib.commands.FileintoCommand`,  y redirecciones existentes, `sievelib.commands.RedirectCommand`), mostrando sus valores relevantes:

{% highlight python %}	
	i = 1
	for r in p.result:
		if r.children:
			if (type(r.children[0]) == sievelib.commands.FileintoCommand):
				print i, ") Folder   ", r.children[0]['mailbox']
			elif (type(r.children[0]) == sievelib.commands.RedirectCommand):
				print i, ") Redirect ", r.children[0]['address']
			else:
				print i, ") Not implented ", type(r.children[0])
		else:
			print  i, ") Not implented ", type(r)
	
{% endhighlight %}

Cada resultado es una regla, que tiene como 'hijo' la acción y la carpeta o la dirección donde se reenvía (en ambos casos puede haber varias acciones, como veremos luego). También indica las reglas que no han sido contempladas por el programa y que, por lo tanto no tenemos posibilidad de añadir (abriendo la puerta a futuras mejoras).
Finalmente, se ofrecen las opciones de añadir carpetas o redirecciones nuevas:

{% highlight python %}	
	print i, ") New folder "
	print i+1, ") New redirection"
{% endhighlight %}

Si reutilizamos alguna acción, simplemente copiamos lo que ya teníamos, añdiendo las carpetas o las redirecciones que haya y terminando con el `stop` que hace que no se analicen más reglas:

{% highlight python %}	
		action=p.result[int(option)-1].children

		for i in action:
			print i.arguments
			if i.arguments.has_key('mailbox'):
				actions.append(("fileinto",i.arguments['mailbox']))
			elif i.arguments.has_key('address'):
				actions.append(("redirect",i.arguments['address']))
			else:	
				actions.append(("stop",))
	
{% endhighlight %}

En el caso de que queramos utilizar una carpeta diferente, solicitamos el nombrey comprobamos que la carpeta existe (podríamos querer una carpeta que no existe, pero casi nunca es el caso, así que no contemplamos esa opción; esto nos permitirá evitar errores al teclear). Para esto es necesario estar autentificado con el servidor IMAP:

{% highlight python %}	
		folder= raw_input("Name of the folder: ")
		print "Name ", folder
		if (doFolderExist(folder,M)[0]!='OK'):
{% endhighlight %}

La carpeta (sólo una) se añade así:

{% highlight python %}	
			actions.append(("fileinto", folder))
			actions.append(("stop",))
{% endhighlight %}

En el caso de redirecciones la verificación se hace mediante una pregunta explícita:

{% highlight python %}	
		redir= raw_input("Redirection to: ")
		print "Name ", redir
		itsOK= raw_input("It's ok? (y/n)")
		if (itsOK!='y'):
{% endhighlight %}

Y en caso de que la validemos, añadimos la acción correspondiente:

{% highlight python %}	
			actions.append(("redirect", redir))
			actions.append(("stop",))
{% endhighlight %}

Aunque hemos seleccionado una cabecera para filtrar y la hemos limpiado es posible que no queramos utilizar la cabecera completa (ejemplo típico: en lugar de una dirección de correo, un dominio o una parte del usuario de correo) así que ofrecemos al usuario la posibilidad de escribir lo que considere oportuno:

{% highlight python %}
	print "Filter: (header) ", keyword,", (text) ", textHeader
	filterCond = raw_input("Text for selection (empty for all): ")

	if not filterCond:
		filterCond = textHeader
{% endhighlight %}

Ahora construimos la regla:

{% highlight python %}
	conditions=[]
	conditions.append((keyword, ":contains", filterCond))
{% endhighlight %}

Y creamos un filtro con ella (lo ideal sería añadirla al correspondiente si ya existía pero eso será objeto de una entrada posterior, tal vez) y lo almacenamos en un fichero (seguro que esta parte podría evitarse, pero no tengo claro cómo hacerlo):

{% highlight python %}
	fs = FiltersSet("test")
	fs.addfilter("",conditions,actions)
	fs.tosieve(open('/tmp/kkSieve','w'))
{% endhighlight %}

Lo abrimos para analizarlo igual que el original:

{% highlight python %}
	p2=Parser()
	p2.parse(open('/tmp/kkSieve','r').read())
	lenP2 = len(p2.result)
{% endhighlight %}

Y añadimos las reglas a las que teníamos, para finalizar escribiéndolas en un fichero:

{% highlight python %}
	p.result.append(p2.result[lenP2-1])	

	fSieve=open('/tmp/kkSieve','w')
	for r in p.result:
		r.tosieve(0,fSieve)
	fSieve.close()
{% endhighlight %}

Guardamos el fichero original para tener un histórico y también como copia de seguridad por si algo va mal:

{% highlight python %}
	name = time.strftime("%Y-%m-%d-%H-%M-%S", time.gmtime())
	c.putscript(name+'sogo',script)
{% endhighlight %}

Finalmente, ponemos el nuevo fichero como fichero de reglas de nuestra criba ('sieve'):

{% highlight python %}
	fSieve=open('/tmp/kkSieve','r')
	if not c.putscript('sogo',fSieve.read()):
		print "fail!"
{% endhighlight %}

Planes para el futuro: 

* Agrupar reglas para que las que corresponden a las mismas acciones estén juntas. 
* Modificar este programa para que la adición de reglas se haga añadiéndolas en el lugar que les corresponda, en vez de al final.
* Gestionar las copias de seguridad de los viejos filtros. Está bien tener algunas por si algo va mal, pero no vale la pena guardar toda la historia.
* Añadir un modo completamente manual (para el que ya hay código, pero no está integrado)
* Automatizar todavía más la extracción de reglas (por ejemplo, intentar 'adivinar' cuál es la acción que podríamos elegir (?).

¿Ideas? ¿Comentarios? Estaremos escuchando en [@mbpfernand0](http://twitter.com/mbpfernand0) o en [@fernand0](http:/twitter.com/fernand0).
