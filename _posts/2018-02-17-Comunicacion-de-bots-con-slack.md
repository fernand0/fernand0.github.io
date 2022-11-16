---
layout: post
title: "Comunicación de bots usando Slack"
date: "Sat Feb 17 16:18:01 +0100 2018"
category: chatbot
tags: [chatbot, errbot, python, proyectos, making, bot, coordinación, slack]
imagefeature: https://c2.staticflickr.com/4/3039/3046816128_c5345d9b84_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/3046816128" title="Mensajes"><img src="https://c2.staticflickr.com/4/3039/3046816128_c5345d9b84_m.jpg" width="240"  alt="Mensajes" style="float:left; margin:5px"></a>
Ya hemos hablado en alguna ocasión de las pruebas que voy haciendo con un `bot` conversacional (aviso: nada de inteligencia artificial ni procesado del lenguaje: sólo un conjunto de instrucciones predefinidas por mi mismo). 
Se puede ver un ejemplo en [Segundo bot: avanzamos](https://mbpfernand0.wordpress.com/2014/06/15/segundo-bot-avanzamos/). 
Creo más en el concepto de [Un chatbot como asistente personal](http://fernand0.blogalia.com/historias/77312) que en otras ideas que podemos ver por ahí.
Para estos desarrollos me gusta mucho el proyecto [Errbot](http://errbot.io/) que nos proporciona una infraestructura para desarrollar bots conversacionales porque se desarrolla en Python, tiene un mecanismo de plugins para añadir instrucciones, una comunidad bastante amistosa y además mecanismos para interactuar a través de diversos canales.  

Pero (siempre hay un pero) los desarrolladores no han contemplado la posibilidad de que un bot pueda escuchar en distintos canales a la vez. Yo empecé con un bot que escuchaba XMPP, pero los clientes no son muy cómodos y terminé pasándolo a Telegram: hay clientes para el teléfono móvil, para el escritorio, ... 

A veces preferiría enviar instrucciones al bot a través de un sistema basado en texto (tal vez la línea de instrucciones) y decidí probar con el IRC.

Algunos hemos pedido esta característica, pero no parece una prioridad para suficiente gente: [multibackend](https://plus.google.com/+ErrbotNet/posts/3oDqwKXzdCa), [Support multiple backends in one instance](https://github.com/errbotio/errbot/issues/1137).

Una posible solución sería tener dos bots replicados e indpendientes y que cada uno responda según se le vaya pidiendo. Sin embargo, dándole vueltas pensé en la posibilidad de establecer un mecanismo de coordinación: añadimos una función `forward` (`fw` para escribir menos) y si estoy en el canal del bot que no sabe ejecutar mi instrucción, le pido que la redirija a otro que pueda ser capaz. 
Por ejemplo, para saber el estado del otro bot, que es una instrucción estándar de `Errbot` (de momento estoy trabajando con dos, uno reconoce instrucciones que empiezan con '!', y el otro con ',') escribiríamos: 

    !fw ,status

Una vez planteada la funcionalidad, la decisión era como establecer la comunicación entre los bots. Una posibilidad sería comunicarlos directamente intercambiando mensajes entre ellos, pero entonces puede ocurrir que uno esté desconectado o inactivo y eso sería un problema. 

¿Por qué no utilizar un mecanismo similar a los de mando y control (*command and control*) a través de un canal acordado donde los bots pueden escribir y leer? 

Podemos definir una sintaxis (un lenguaje de comunicación) y hacemos que la instrucción `fw` escriba en el canal. Establecemos también un mecanismo de lectura del canal y cuando el bot encuentre un mensaje para él lo interpreta, lo ejecuta, y publica en el canal el resultado. Si el bot encuentra un mensaje de respuesta para él, envía dicha repuesta por su mecanismo de comunicación al usuario que pidió su ejecución.

Como prueba de concepto podemos echar un vistazo a [err-forward](https://github.com/fernand0/err-forward/blob/c2bc2e0297506d946970dcd1c5f35f0f4de2f2de/errForward.py) (enlace a la versión actual porque es un proyecto vivo y podría evolucionar en el futuro) y también ver un vídeo de dos bots transmitiéndose instrucciones. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/_tEDXFvuWpE" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Para su desarrollo se han utilizado:

* el mecanismo de **creación de plugins** de Errbot
* el mecanismo de **programación de actividades** ([Scheduling](http://errbot.io/en/latest/user_guide/plugin_development/scheduling.html)).
* un **canal común** donde escribir y leer las instrucciones.

Todos conocemos sistemas de mando y control basados en IRC, correo electrónico, Twitter, ...
En nuestro caso había que elegir uno para nuestros bots. No soy un gran fan de [Slack](https://slack.com/) pero quería darle una oportunidad de uso y pensé que una buena forma sería creando allí el canal de intercambio de mensajes. 
Slack tiene un API y módulos en Python para interactuar con los canales ([slackclient](https://pypi.python.org/pypi/slackclient)), así que parecía una buena opción para intentarlo.

De momento hemos definido tres tipos de mensajes:

* **`Msg`** para **mensajes textuales** (saludos y despedidas de los bots y otros).
* **`Cmd`** para **instrucciones**
* **`Rep`** para **respuestas**

La creación de un bot en estas circunstancias se basa, entonces, en las siguientes funciones:

* **Inicialización**: el bot empieza a funcionar, se conecta al canal y escribe un mensaje de 'saludo'.
* **Escritura**: el bot puede escribir un mensaje de cualquiera de los tres tipos anteriores en el canal.
* **Lectura**: el bot lee el canal y es capaz de identificar los mensajes que puede interpretar, realizando las acciones oportunas y escribiendo en el mismo canal las respuestas, si procede.

No entraremos en detalles aquí pero para que un bot pueda leer y escribir en un canal de Slack es necesario tener un *token* que permita inteactuar con, por ejemplo, la [Slack Web API](https://api.slack.com/web).

Siguiendo desarrollos anteriores, almacenamos el *token* en un fichero denominado `~/.rssSlack` con el formato:

    [Slack]
    api-key:......

La leemos utilizando el módulo `configparser`, creamos el cliente y publicamos el primer mensaje. El canal donde se comunicarán los bots es un parámetro de configuración del módulo, al que se accede a través de 

```python
    self._check_config('channel') 
```

Además el bot almacena el usuario del sistema oporativo y el nombre de la máquina, que se usará para enviar las respuestas cuando proceda. 
El mensaje de saludo incluye la dirección IP:

```python
self['sc'] = SlackClient(slack_token)
self['chan'] = str(self._check_config('channel'))
self['userName'] = pwd.getpwuid(os.getuid())[0]
self['userHost'] = os.uname()[1]

self.publishSlack(typ = 'Msg', args = 'Hello! from %s' % self.getMyIP())
```

Aquí se ha utilizado el método `publishSlack` que sirve para escribir en el canal (lo comentaremos luego).

Después se inicializa el *poller* que lee periódicamente el canal para ver si hay algo que el bot pueda hacer:

```python
    self.start_poller(60, self.readSlack)
```

Aquí se utiliza el método `readSlack` que sirve para leer en el canal (lo comentaremos luego) y, en esta configuración se ejecuta una lectura cada 60 segundos.

El método de publicación (`publishSlack`) es muy sencillo, simplemente prepara el mensaje y lo escribe en el canal. De momento, un mensaje tiene el formato:

```python
    msg = {'userName': usr, 'userHost': host,
            'frm': str(frm), 'typ': typ, 'cmd': cmd, 'args': args }
```

Incluye el nombre de usuario y de la máquina del usuario, un campo `frm` que viene de la comunicación del bot, un tipo (`typ`) tal y como se explicó arriba, y los campos `cmd` y `args` que también provienen de la forma de funcionar de Errbot (instrucción y argumentos).
El mensaje se codifica para que no se interprete como html, se transforma en *json* para que sea más fácil leerlo luego y se publica en el canal:

```python
    chan = self['chan']
    self['sc'].api_call( "chat.postMessage", channel = chan, text = msgJ)
```

El método de lectura (`readSlack`) es algo más complicado: tiene que leer en el canal la lista de mensajes, decidir si alguno de ellos es para el bot en cuestión, interpretarlo, ...

La lectura del canal es sencilla:

```python
    chan = self.normalizedChan(self._check_config('channel'))
    history = self['sc'].api_call("channels.history", channel=chan)
```

Luego hay que recorrer la lista de mensajes y actuar según proceda:

```python
for msg in history['messages']:
     msgJ = self.extractArgs(msg)
     if ('typ' in msgJ):
         if msgJ['typ'] == 'Cmd':
             # It's a command 
             self.manageCommand(chan, msgJ, msg)
         elif msgJ['typ'] == 'Rep':
             # It's a reply 
             self.manageReply(chan, msgJ, msg)
``` 

Como puede verse, se utilizan algunas funciones auxiliares.

El método `extractArgs` extrae los campos del `json` que lee del canal y, si no es un mensaje (los mensajes simplemente se ignoran), hace la conversión de los argumentos (están codificados para que no se interpreten como html porque algunas instrucciones utilizan este lenguaje):

```python
if msgJ['args'] and (msgJ['typ'] != 'Msg'):
    # Unquoting the args
    self.log.debug("Reply args before: %s " % msgJ['args'])
    tmpJ = urllib.parse.unquote(msgJ['args'])
    msgJ['args'] = tmpJ
```

El método `manageCommand` determina si el mensaje es para el bot y, en su caso, trata de realizar lo que corresponda:

```python
listCommands = self._bot.all_commands
if msgJ['cmd'].startswith(self._bot.bot_config.BOT_PREFIX):
    cmd = msgJ['cmd'][len(self._bot.bot_config.BOT_PREFIX):]

    self.log.debug("Cmd: %s"% cmd)
    if cmd in listCommands:
```

Esto es, obtiene una lista de instrucciones, comprueba que la instrucción comienza con el caracter adecuado, y luego verifica si es una instrucción conocida para el bot. Posteriormente, la ejecuta.
Para ello, identifica el método asociado:

```python
    method = listCommands[cmd]
```

Y la ejecuta:

```python
    replies = method("", msgJ['args'])
```

Con un tratamiento ligeramente diferente si se trata de un generador (puede haber varias respuestas) o no.

En ambos casos guarda como texto la respuesta para devolverla convenientemente.

```python
   self.publishSlack(typ = 'Rep', usr= msgJ['userName'],
       host=msgJ['userHost'], frm = msgJ['frm'], args = txtR)
```

En algunos casos las instrucciones utilizan plantillas ([templating](http://errbot.io/en/latest/user_guide/plugin_development/messaging.html#templating)) y, por ello, el intérprete necesita tener en cuenta esto:

```python
    txtR = txtR + tenv().get_template(method._err_command_template+'.md').render(reply)
```

Después de interpretar la instrucción, ejecutarla y escribir la respuesta, el bot borra el mensaje del canal (la referencia a mensajes concretos se realiza basada en un identificador basado en el momento de publicación del mensaje):

```python
    self.deleteSlack(chan, msg['ts'])
```

Finalmente, el mensaje podría ser una respuesta. Para ello se utiliza el méotodo `manageReply`.
Este método tiene que identificar si la respuesta es para el bot:

```python
if ((msgJ['userName'] == self['userName'])
        and (msgJ['userHost'] == self['userHost'])):
    # It's for me
    self.log.info("Yes. It's for me")
    replies = msgJ['args']
```

Y enviarla al usuario que lanzó la instrucción:

```python
    self.send(msgTo, replies)
```

Para después borrarla:

```python
    self.deleteSlack(chan, msg['ts'])
```

Todavía no hemos hablado del método para redirigir mensajes, que se llama `forwardCmd` y que funciona como sigue: 
Si la instrucción tiene parámetros, los separa con

```python
if args.find(' ') >= 0:
     cmd, argsS = args.split()
```

Y luego publica el mensaje en el canal:

```python
self.publishSlack(mess=mess,
        usr=self['userName'], host= self['userHost'],
        typ = 'Cmd' , cmd = cmd, args = argsS)
```

Tiene un par de alias, `fw` y `forward`.

Para utilizar este plugin podemos cargarlo en cada bot (podríamos hacerlo directamente desde GitHub):

    !repos install https://github.com/fernand0/err-forward

Definiremos un canal en Slack y configuramos los bots con: 

    !plugin config ErrForward {'channel': *el nombre*}

**Algunas consideraciones finales:**

* Hemos utilizado Slack pero podría utilizarse cualquier canal, con las adaptaciones oportunas. Probablemente haya mecanismos mejores.
* Sería interesante disponer de diferentes canales de comunicación, mejorando el *plugin* para que se pudiera elegir uno, por ejemplo, en la configuración. No se si sería 'abusar' montar otra infraestructura de plugins para esto. En todo caso, me encantaría ver si alguien sigue estas ideas y hace otros 'redirectores'.
* La redirección se hace escribiendo la instrucción para el bot completa, utilizando el caracter especial de inicio de instrucción ('!', ',' en nuestro caso). Esto podría evitarse, y que el bot simplemente intentase interpretar cualquier instrucción.
* Si hay varios bots que son capaces de ejecutar la misma instrucción podemos terminar ejecutándola más de una vez, no se ha previsto un bloqueo para evitarlo. Esto podría causar problemas al intentar borrar el mensaje por segunda vez.
* Se ha conseguido el objetivo de tener varios bots (dos) que son capaces de ejecutar distintas instrucciones y comunicarse entre ellos.
* Hemos aprendido algunas de las *interioridades* de Errbot que permiten interpretar las instrucciones y ejecutarlas, aplicar plantillas, etc.

Llevo probando este mecanismo durante unas semanas con un par de bots (como decía arriba, uno está escuchando en Telegram y el otro en un canal de IRC) y funciona de manera bastante robusta para las instrucciones que yo suelo utilizar: se pueden ver en mi GitHub ([GitHub de fernand0](https://github.com/fernand0/)), todos mis módulos empiezan con `err-`.
