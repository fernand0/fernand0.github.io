--- 
layout: post
title: "La seguridad, el análisis de riesgos, lo viejo y lo nuevo"
date: "Mon Apr 08 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, cerraduras, inteligentes, smart, nuevo, viejo]
imagefeature: https://live.staticflickr.com/8515/8586515627_84181d2ec3_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/8586515627" title="Puerta"><img src="https://live.staticflickr.com/8515/8586515627_84181d2ec3_m.jpg" width="240"  alt="Puerta" style="float:left; margin:5px"></a>
Me gustó mucho leer [Those Bashing Smart Locks Have Forgotten How Easy it is to Pick Regular Ones](https://danielmiessler.com/blog/those-bashing-smart-locks-have-forgotten-how-easy-it-is-to-pick-regular-ones/) por dos motivos: el contenido sobre las cerraduras inteligentes (y no tanto) y también porque cuando aparece un elemento tecnológico que propone sustituir otro más tradicional, siempre hay quién trata de atacar al nuevo porque tiene algunos inconvenientes. El caso más paradigmático sería el del coche autónomo y esas preguntas que podemos leer por ahí sobre a quién debería atropellar un coche autónomo en caso de tener delante diferentes 'alternativas de atropello'. No digo que no sea un debate interesante y, si se pudiera elegir, habría que pensar en ello. Pero olvidamos que un pobre conductor humano, en una circunstancia análoga no podría elegir con una alta probabilidad: haría lo que pudiera; seguramente, poco. Atropellaría a cualquiera de las alternativas disponibles sin haber podido evaluar (ni un poquito) la situación.

En este caso hablamos de cerraduras y como parece que hay gente criticando a las nuevas, y defendiendo las bondades de las de toda la vida.
En cierto modo, nos dice Daniel Miessler, la situación consiste en que hemos olvidado los inconvenientes de la tecnología vieja y ya hemos aceptado los riesgos que supone:

> The problem I see in this discussion is that we’ve somehow—in the information security community—forgotten about the risk that we have already accepted. For hundreds of years we’ve protected our homes  ...

Luego pasa a hacer un análisis de amenazas, que es como debería actuarse frente a un problema de seguridad. No voy a detallar sus conclusiones, pero descataré algunos comentarios de las conclusiones.

Es cierto que pueden tener sus vulnerabilidades y problemas pero atacar un sistema de este tipo tendría sentido si hubiera muchos en los alrededores y pudiéramos sacar ventaja de un ataque a mayor escala:

> So we did see a few situations where attacking a smart lock could make sense, assuming they were similar enough for it to be quick and easy—like in a housing complex for tech employees (in say 5 years).

Por lo demás, en condiciones normales es más sencillo hacer lo que haríamos con una puerta que tenga una cerradura de estilo tradicional: echarla abajo de una patada, o entrar por una ventana.

> It’s easier to kick in the door or go through a window (or pick the lock) than it is to even look at a smart lock, or...

Por otro lado, es fácil imaginar que los atacantes asocien cerraduras inteligentes (smart) con otros sistemas añadidos de vigilancia (¿cámaras? ¿vigilancia remota?...) que sumarían como elementos disuasorios.

> Attackers are likely to start associating smart locks with video capture, remote monitoring, and lots of other IoT-ish functionality, which will mean a higher risk of getting caught.

En definitiva, cuando nos encontremos con una medida de seguridad, vale la pena hacer un análisis más completo (en este caso leerlo) para comprender mejor el escenario y si, efectivamente, aporta o no ventajas.
