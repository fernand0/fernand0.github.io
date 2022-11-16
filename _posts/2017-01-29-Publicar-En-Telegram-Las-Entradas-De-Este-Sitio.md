---
layout: post
title: "Publicar en Telegram las entradas de este sitio usando Python"
date: "Sun Jan 29 18:05:01 +0100 2017"
category: programación
tags: programación desarrollo telegram rss redes sociales difusión python api
imagefeature: https://lh3.googleusercontent.com/ZbSfwyeeqhIzBVwG-RLkSD-1SKUn0mno2jsdrqp9TkLChv0OtZTHXHVQVjVGWiPQVmebjp1sIVF6jm8N9-mzUGVTH_9sKj49_4ixlLM-d-0oy7P-c7ceJb8AO7gC9S5_Y6oEBFVYGsf_7kH4fDILlGNhX6lynhH1hzo3fDbDZK9n8xkdKFi8-WBUu79s52FZwg_7_9kHNR_Q7np8i2ZovqJ3Zs_sGnxrL8WmZz4mbFwI8A7hKwoBLo0oHGnq0Q_2eoq7-iubsEYJ-9rnpq9zpGh03ODF_UtYTk9vCT3lRe2Y7FLorTIsTq0KNDSEMJRdoOemAdnlmR-a02VZ_Jz-AAEEDMFEUbYjgFzKpso5Wo-p3pU6doZzdD4l8UARhQkI0IjgyILiw5fx3-Bhp1LlyJ0TZ2JOV_BJIYf5lq5Zbeiqxyoh7ntbH3S2NoCW7uAFrNCCmUK2w6Zy0W5JiU_Jr4t1ZPZPS3jUn6kZ8Gk3TQxmu7-dGH2OzGuzbvaKVXqcR9MLJNoba9aqLVejdyEcYbUOR0aIMTqgMrPXpMXEIMMWf8RuGCTTOzxE7URDMWNFgpvq_zjklv9u8OC9o28QQ53deLBb_HVZqbfCx8aUe4zFZ0RFMt9s8NdBa5MeUAhmI4adjIzGvR0TL9qQ7dAH8U-pX-d6ZnOn1H5aSSiTYQ=w425-h319-no
---



<a href="https://photos.google.com/share/AF1QipPLwN5PAVtbI7ps9SdsMmOcKUWTmkiZaQVT6pBBjIsuvM8PRh0vAU2ir4s9jF3Lfw/photo/AF1QipMfDKuKgP55rNPoYQh9q_gneLwz43edbXiIGDax?key=QXNpYlI0Qm9yUmJEcXdfQmJRMjlsRFBrNWlVN1VR" title="Interactuando con el bot"><img src="https://lh3.googleusercontent.com/ZbSfwyeeqhIzBVwG-RLkSD-1SKUn0mno2jsdrqp9TkLChv0OtZTHXHVQVjVGWiPQVmebjp1sIVF6jm8N9-mzUGVTH_9sKj49_4ixlLM-d-0oy7P-c7ceJb8AO7gC9S5_Y6oEBFVYGsf_7kH4fDILlGNhX6lynhH1hzo3fDbDZK9n8xkdKFi8-WBUu79s52FZwg_7_9kHNR_Q7np8i2ZovqJ3Zs_sGnxrL8WmZz4mbFwI8A7hKwoBLo0oHGnq0Q_2eoq7-iubsEYJ-9rnpq9zpGh03ODF_UtYTk9vCT3lRe2Y7FLorTIsTq0KNDSEMJRdoOemAdnlmR-a02VZ_Jz-AAEEDMFEUbYjgFzKpso5Wo-p3pU6doZzdD4l8UARhQkI0IjgyILiw5fx3-Bhp1LlyJ0TZ2JOV_BJIYf5lq5Zbeiqxyoh7ntbH3S2NoCW7uAFrNCCmUK2w6Zy0W5JiU_Jr4t1ZPZPS3jUn6kZ8Gk3TQxmu7-dGH2OzGuzbvaKVXqcR9MLJNoba9aqLVejdyEcYbUOR0aIMTqgMrPXpMXEIMMWf8RuGCTTOzxE7URDMWNFgpvq_zjklv9u8OC9o28QQ53deLBb_HVZqbfCx8aUe4zFZ0RFMt9s8NdBa5MeUAhmI4adjIzGvR0TL9qQ7dAH8U-pX-d6ZnOn1H5aSSiTYQ=w425-h319-no" alt="Interactuando con el bot"></a>
Siguiendo la línea de publicaciones anteriores, y tratando de alcanzar mayor difusión de las entradas de este sitio (y otro) decidimos probar el API de publicación de Telegram. Como siempre, es sencillo si encontramos las bibliotecas adecuadas y tenemos un poco de paciencia.

Pero primero tenemos que crear el bot. Siguiendo las instrucciones del [BotFather](https://core.telegram.org/bots#6-botfather). En este caso le pedimos el nuevo bot con:

    /newbot

El botfather nos pide un nombre para nuestro bot, y un nombre de usuario (que deberá terminar en 'bot'). Como respuesta nos envía el 'token' que nos servirá para identificarnos y poder interactuar con él. A partir de allí nuestra misión es mandarle cosas al bot. 

Yo he elegido hacer un programita en Python, utilizando [telepot](https://github.com/nickoala/telepot). Las instrucciones están en [telepot documentation](http://telepot.readthedocs.io/en/latest/) El código que se muestra allí es muy sencillo. 

    import telepot
    bot = telepot.Bot('***** AQUÍ VA EL TOKEN *****')

Y mandar un mensaje sería algo así como:

    bot.sendMessage(999999999, 'Hola mundo')

En este caso '999999999' es el identificador del bot, se puede utilizar el nombre asignado anteriormente.

En nuestro caso, como queremos que el bot avise automáticamente a sus seguidores cuando haya novedades utilizamos la [fuente RSS del blog ](http://fernand0.github.io/feed.xml) y algunos módulos de Python como feedparser. 

Nos vamos a saltar esta parte porque ya la hemos contado en otro sitio y también la parte de obtener el título, el contenido y el enlace a la última entrada.

En este caso hay ciertos límites, no se pueden superar los 4096 caracteres en UTF8. Además, para que el texto tenga algo de gracia nos permiten algunas [etiquetas de formato](https://core.telegram.org/bots/api#text-formatting) (que pueden ser HTML o Markdown). Como estamos leyendo la fuente RSS habremos leido HTML y la única prevención que hay que tener es utilizar sólo las etiquetas permitidas (negrita, cursiva, enlaces, código y texto pre-formateado). Para esto hice una chapucilla, consistente en eliminar todas las etiquetas que no le gustan al sistema:

Extraemos todas las etiquetas de nuestro texto:

    tags = [tag.name for tag in soup.find_all()]

Y luego las recorremos:

    for tag in tags:

Eliminando las que no son válidas:

       if tag not in validTags:

con `unwrap`. Previamente hemos tenido una consideración especial con las citas añadiéndoles delante y detrás unas comillas para que se refleje adecuadamente en el resultado final.

{% highlight python %}
def cleanTags(soup):
    tags = [tag.name for tag in soup.find_all()]
    validTags = ['b', 'strong', 'i', 'em', 'a', 'code', 'pre']

    if soup.blockquote:
        soup.blockquote.insert_before('«')
        soup.blockquote.insert_after( '»')

    for tag in tags:
        if tag not in validTags:
            for theTag in soup.find_all(tag):
                theTag.unwrap()
{% endhighlight %}


Para enviar el mensaje necesitamos crear un canal [FAQ channels](https://telegram.org/faq_channels) y dar de alta como administrador al bot, para que pueda escribir en el canal:

    bot.sendMessage('@'+channel, str(soup)[:4096], parse_mode='HTML')

El código está integrado en mi proyecto [rssToSocial](https://github.com/fernand0/scripts/blob/master/rssToSocial.py) que no es un código para sentirse especialmente orgulloso. Pero permite hacer estas publicaciones sin tener que hacerlo a mano.

La explicación del código para publicar en otras redes sociales está en:

* [Publicar en Linkedin las entradas de este sitio usando Python](http://fernand0.github.io/Publicar-En-Linkedin-Las-Entradas-De-Este-Sitio/)
* [Publicar en Twitter las entradas de este sitio usando Python](http://fernand0.github.io/publicar-en-twitter-las-entradas-de-este-sitio/)
* [Publicar en Facebook las entradas de este sitio usando Python](http://fernand0.github.io/Publicar-En-Facebook-Las-Entradas-De-Este-Sitio/)

A partir de ahora (o dentro de un poco, que tengo que configurarlo) ya pueden recibir notificaciones siguiendo a  [mbpfernand0 en Telegram](https://t.me/mbpfernand0).
