---
layout: post
title: "Una pata robótica"
date: "Sun Feb 15 21:25:01 +0100 2015"
category: "Raspberry Pi"
tags: raspberry pi raspi servo movimiento hexápodo robot making
---



Esta entrada es más una 'nota para mi mismo' (note to self) que algo de valor real. Pero me encuentro con algunos pequeños avances, unas cuantas pestañas abiertas en el navegador y creo que es mejor compartirlo aquí para futura referencia que esperar a una (eventual) finalización de algo más avanzado.
Quién sabe si puede servirle a alguien para algo.

En [Una cámara móvil](https://mbpfernand0.wordpress.com/2014/07/20/una-camara-movil/) ya anticipábamos la posibilidad de hacer algo que se moviera. De hecho, ya se sugería la inspiración en [Stubby. Full featured, miniature hexapod](http://stubby.digitalcave.ca/stubby/assembly.jsp). También se puede ver información en [Stubby the (Teaching) Hexapod](https://hackaday.io/project/770-stubby-the-teaching-hexapod).

 Mi único problema con ese diseño eran las habilidades y herramientas necesarias: corte de madera, mecanizado...  Estuve dándole vueltas a las alternativas realizables y pensé en tubos de madera. Con la idea de que sólo sería necesario cortarlos a la medida adecuada, perforarlos y montar el armazón adecuado.

También descubrí otros proyectos interesantes como [A spider called "Chopsticks"](http://letsmakerobots.com/node/26107) que utilizaba palillos orientales para las patas y [Popsicle Stick Hexapod R.I.P.](http://letsmakerobots.com/node/36513) que utiliza palos de helado, lo que iba más en la línea de lo que estaba pensando y me animó bastante. También había visto [Build a 12-Servo Hexapod](http://www.robotoid.com/appnotes/project-build-12-servo-hexapod.html) que tiene menos posibilidades pero que también es muy interesante.

Buscando en la red hay un montón de proyectos más, como [Hexpider](http://maquinasquepiensan.com/?page_id=19) que sigue otro tipo de diseño (y es capaz hasta de escribir) y este otro [6-legged robot project](https://www.flickr.com/photos/dsnowdon/sets/72057594073228107) que me han servido para tener algunas ideas sobre movimiento y configuración de las articulaciones (a nivel básico, todavía no he estado pensando demasiado en esa parte). 

Con estas ideas me fui a la tienda de bricolaje más cercana a ver qué tenían. Aunque llevaba en la cabeza la idea de los tubos de madera allí encontré un tubo de plástico que me pareció muy adecuado: pensé allí mismo que sería más fácil de cortar y más ligero. También tenían tubos de aluminio que quedarían mucho más impactantes a la vista, pero de momento ese no es el objetivo.

<blockquote class="instagram-media" data-instgrm-captioned data-instgrm-version="4" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px; max-width:658px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:8px;"> <div style=" background:#F8F8F8; line-height:0; margin-top:40px; padding:50% 0; text-align:center; width:100%;"> <div style=" background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAsCAMAAAApWqozAAAAGFBMVEUiIiI9PT0eHh4gIB4hIBkcHBwcHBwcHBydr+JQAAAACHRSTlMABA4YHyQsM5jtaMwAAADfSURBVDjL7ZVBEgMhCAQBAf//42xcNbpAqakcM0ftUmFAAIBE81IqBJdS3lS6zs3bIpB9WED3YYXFPmHRfT8sgyrCP1x8uEUxLMzNWElFOYCV6mHWWwMzdPEKHlhLw7NWJqkHc4uIZphavDzA2JPzUDsBZziNae2S6owH8xPmX8G7zzgKEOPUoYHvGz1TBCxMkd3kwNVbU0gKHkx+iZILf77IofhrY1nYFnB/lQPb79drWOyJVa/DAvg9B/rLB4cC+Nqgdz/TvBbBnr6GBReqn/nRmDgaQEej7WhonozjF+Y2I/fZou/qAAAAAElFTkSuQmCC); display:block; height:44px; margin:0 auto -44px; position:relative; top:-22px; width:44px;"></div></div> <p style=" margin:8px 0 0 0; padding:0 4px;"> <a href="https://instagram.com/p/zFUu0YQB4M/" style=" color:#000; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none; word-wrap:break-word;" target="_top">Palo</a></p> <p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;">A photo posted by Fernando Tricas García (@ftricas) on <time style=" font-family:Arial,sans-serif; font-size:14px; line-height:17px;" datetime="2015-02-14T13:25:29+00:00">Feb 14, 2015 at 5:25am PST</time></p></div></blockquote>
<script async defer src="//platform.instagram.com/en_US/embeds.js"></script>

Como suponía, el tubo de plástico es fácil de trabajar y podemos hacerle un agujero y poner un tornillo para sujetar un servo sin complicarnos mucho la vida, como puede verse en esta foto:

<blockquote class="instagram-media" data-instgrm-captioned data-instgrm-version="4" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px; max-width:658px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:8px;"> <div style=" background:#F8F8F8; line-height:0; margin-top:40px; padding:50% 0; text-align:center; width:100%;"> <div style=" background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAsCAMAAAApWqozAAAAGFBMVEUiIiI9PT0eHh4gIB4hIBkcHBwcHBwcHBydr+JQAAAACHRSTlMABA4YHyQsM5jtaMwAAADfSURBVDjL7ZVBEgMhCAQBAf//42xcNbpAqakcM0ftUmFAAIBE81IqBJdS3lS6zs3bIpB9WED3YYXFPmHRfT8sgyrCP1x8uEUxLMzNWElFOYCV6mHWWwMzdPEKHlhLw7NWJqkHc4uIZphavDzA2JPzUDsBZziNae2S6owH8xPmX8G7zzgKEOPUoYHvGz1TBCxMkd3kwNVbU0gKHkx+iZILf77IofhrY1nYFnB/lQPb79drWOyJVa/DAvg9B/rLB4cC+Nqgdz/TvBbBnr6GBReqn/nRmDgaQEej7WhonozjF+Y2I/fZou/qAAAAAElFTkSuQmCC); display:block; height:44px; margin:0 auto -44px; position:relative; top:-22px; width:44px;"></div></div> <p style=" margin:8px 0 0 0; padding:0 4px;"> <a href="https://instagram.com/p/zIeZEpQB6f/" style=" color:#000; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none; word-wrap:break-word;" target="_top">La pata #raspi #servo</a></p> <p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;">A photo posted by Fernando Tricas García (@ftricas) on <time style=" font-family:Arial,sans-serif; font-size:14px; line-height:17px;" datetime="2015-02-15T18:47:37+00:00">Feb 15, 2015 at 10:47am PST</time></p></div></blockquote>
<script async defer src="//platform.instagram.com/en_US/embeds.js"></script>

La fotografía no es muy buena, pero creo que es suficiente para hacerse una idea de cómo se pueden unir las partes, es lo que más he agradecido ver en los proyectos de otra gente para copiar/inspirarme. Como puede verse, he elegido un diseño con tres servos

También podemos poner bridas de plástico para fijar una articulación con otra, aunque imagino que hará falta una sujección más sólida cuando llegue el momento de que todo esto se mueva. Pero nuevamente parece sencillo hacer rebajes y pegar unas piezas con otras cuando tengamos una idea más clara del proyecto.

Ha sido sorprendente para mi ver lo rápido que he podido llegar a tener esta configuración, ya veremos si después sigo avanzando tan rápido (con el inconveniente de que no tengo suficientes motores, así que hacen falta algunas compras y esas cosas). 

Para el movimiento de las articulaciones ya teníamos la experiencia de [Añadiendo movimiento: servos ](https://mbpfernand0.wordpress.com/2014/06/08/anadiendo-movimiento-servos/), si bien es cierto es que re-escribí casi todo el código siguiendo las ideas de [PiCam](https://github.com/MattStultz/PiCam); al fijar mejor la cámara (que es algo que no conté por aquí), el movimiento suave ya no era tan necesario. 

<blockquote class="instagram-media" data-instgrm-captioned data-instgrm-version="4" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px; max-width:658px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:8px;"> <div style=" background:#F8F8F8; line-height:0; margin-top:40px; padding:50% 0; text-align:center; width:100%;"> <div style=" background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAsCAMAAAApWqozAAAAGFBMVEUiIiI9PT0eHh4gIB4hIBkcHBwcHBwcHBydr+JQAAAACHRSTlMABA4YHyQsM5jtaMwAAADfSURBVDjL7ZVBEgMhCAQBAf//42xcNbpAqakcM0ftUmFAAIBE81IqBJdS3lS6zs3bIpB9WED3YYXFPmHRfT8sgyrCP1x8uEUxLMzNWElFOYCV6mHWWwMzdPEKHlhLw7NWJqkHc4uIZphavDzA2JPzUDsBZziNae2S6owH8xPmX8G7zzgKEOPUoYHvGz1TBCxMkd3kwNVbU0gKHkx+iZILf77IofhrY1nYFnB/lQPb79drWOyJVa/DAvg9B/rLB4cC+Nqgdz/TvBbBnr6GBReqn/nRmDgaQEej7WhonozjF+Y2I/fZou/qAAAAAElFTkSuQmCC); display:block; height:44px; margin:0 auto -44px; position:relative; top:-22px; width:44px;"></div></div> <p style=" margin:8px 0 0 0; padding:0 4px;"> <a href="https://instagram.com/p/yki0A2wB7D/" style=" color:#000; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none; word-wrap:break-word;" target="_top">Rápido-lento-rápido #raspi #err #errbot</a></p> <p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;">A video posted by Fernando Tricas García (@ftricas) on <time style=" font-family:Arial,sans-serif; font-size:14px; line-height:17px;" datetime="2015-02-01T19:53:35+00:00">Feb 1, 2015 at 11:53am PST</time></p></div></blockquote>
<script async defer src="//platform.instagram.com/en_US/embeds.js"></script>

En la parte de los programas, por ahora, he hecho un par de programitas que están en [servo](https://github.com/fernand0/raspi/tree/master/servo). 

El primero sirve para mover cada articulación de manera independiente desde la línea de órdenes (para poder establecer los puntos de referencia fácilmente): [legOneMove.py](https://github.com/fernand0/raspi/blob/8bbc3f49b50cc9f3af4160dc7d9a4f0dc8e337d8/servo/legOneMove.py).

Tenemos las tres articulaciones en los puertos GPIO correspondientes:

{% highlight python %}
servoGPIO=[17, 23,15]
{% endhighlight %}

y utilizamos una función para transformar un ángulo en el pulso necesario para mover el servo:

{% highlight python %}
def angleMap(angle):
    return int((round((1950.0/180.0),0)*angle)/10)*10+550
{% endhighlight %}

Y la función que mueve el motor es muy sencilla:

{% highlight python %}
def movePos(art, pos):
    servo = PWM.Servo()
    print art
    servo.set_servo(art, angleMap(pos))
    time.sleep(VEL)
{% endhighlight %}

Para mi vergüenza, notar sólo recientemente descubrí la necesidad del temporizador final, porque si no el programa no da tiempo a que el movimiento se complete. 
Finalmente, en 

{% highlight python %}
movePos(servoGPIO[int(sys.argv[1])], int(sys.argv[2]))
{% endhighlight %}

Directamente pasamos el primer argumento de la llamada como articulación que hay que mover (que se corresponderá, recordemos, con el GPIO adecuado) y el segundo es el ángulo de movimiento. No lo hagáis así, amiguitos: no os olvidéis nunca añadir en proyectos 'reales' los límites y comprobaciones adecuadas para no llevarnos más tarde sorpresas desagradables.

El segundo programa sería [legServo.py](https://github.com/fernand0/raspi/blob/e75b5145cadfcabd43f734c8ff398848f8b68b90/servo/legServo.py) que no es más que una simulación de lo que podrían ser los movimientos necesarios para que el hipotético robot ande: levantar un poco la pata, moverla hacia adelante, bajar la pata, moverla hacia atrás, ... Y así sucesivamente. Seguro que hay que hacer ajustes después pero nos da una cierta idea de que hemos llegado a algún sitio.

A continuación podemos ver un vídeo de estos movimientos repetidos varias veces, que he grabado con ayuda de mi hijo 

<blockquote class="instagram-media" data-instgrm-captioned data-instgrm-version="4" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px; max-width:658px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:8px;"> <div style=" background:#F8F8F8; line-height:0; margin-top:40px; padding:50% 0; text-align:center; width:100%;"> <div style=" background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAsCAMAAAApWqozAAAAGFBMVEUiIiI9PT0eHh4gIB4hIBkcHBwcHBwcHBydr+JQAAAACHRSTlMABA4YHyQsM5jtaMwAAADfSURBVDjL7ZVBEgMhCAQBAf//42xcNbpAqakcM0ftUmFAAIBE81IqBJdS3lS6zs3bIpB9WED3YYXFPmHRfT8sgyrCP1x8uEUxLMzNWElFOYCV6mHWWwMzdPEKHlhLw7NWJqkHc4uIZphavDzA2JPzUDsBZziNae2S6owH8xPmX8G7zzgKEOPUoYHvGz1TBCxMkd3kwNVbU0gKHkx+iZILf77IofhrY1nYFnB/lQPb79drWOyJVa/DAvg9B/rLB4cC+Nqgdz/TvBbBnr6GBReqn/nRmDgaQEej7WhonozjF+Y2I/fZou/qAAAAAElFTkSuQmCC); display:block; height:44px; margin:0 auto -44px; position:relative; top:-22px; width:44px;"></div></div> <p style=" margin:8px 0 0 0; padding:0 4px;"> <a href="https://instagram.com/p/zIfJPpwB8W/" style=" color:#000; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none; word-wrap:break-word;" target="_top">En movimiento #servo #raspi</a></p> <p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;">A video posted by Fernando Tricas García (@ftricas) on <time style=" font-family:Arial,sans-serif; font-size:14px; line-height:17px;" datetime="2015-02-15T18:54:11+00:00">Feb 15, 2015 at 10:54am PST</time></p></div></blockquote>
<script async defer src="//platform.instagram.com/en_US/embeds.js"></script>

También podemos ver en el siguiente vídeo algunas pruebas previas, aprovechando el sensacional editor de vídeos de YouTube, con dos articulaciones y con tres: 

<iframe width="460" height="315" src="https://www.youtube.com/embed/sEXojVp6paI" frameborder="0" allowfullscreen></iframe>

Los siguientes pasos deberían ser hacer el resto de las patas (como mínimo cuatro, aunque creo que quedará mejor con seis) y ver si será necesario algún *hardware* adicional (para controlar los 18 motores y, tal vez, algo más las salidas dela Raspberry podrían ser insuficientes) y alguna idea adicional para el 'cuerpo' del robot.
Seguiremos informando.
