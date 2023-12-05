---
layout: post
title: "¿Un ataque sofisticado o 'paso de contarte lo que sucedió'?"
date: "2023-12-05 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- artículo
- investigación
- research
- paper
- ataques
imagefeature: 'https://live.staticflickr.com/65535/53339576738_f542de08ed.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/53339576738/in/datetaken/" title="Muro, torre y almenas"><img src="https://live.staticflickr.com/65535/53339576738_f542de08ed.jpg" alt="Muro, torre y almenas" class="img-responsive img-centered"></a>

Últimamente tenía la impresión de que se ha convertido en tendencia anunciar que hemos sido víctimas de un ataque informático, decir que han utilizado medios muy sofisticados y seguir con nuestra vida.
Esa impresión significaba, para mi, que era una forma fácil de eludir contar lo que había sucedido (y los medios se conformaban con la explicación, que ya les parecía suficiente). 
El caso ese que descubrí hace no mucho (aunque tiene más de un año) el trabajo: [[PDF] A “sophisticated attack”? Innovation, technical sophistication, and
creativity in the cybercrime ecosystem](https://weis2022.econinfosec.org/wp-content/uploads/sites/10/2022/06/weis22-collier.pdf) publicado en [WEIS 2022](https://weis2022.econinfosec.org/) que parece apoyar lo que suponíamos:

> We observe that almost every cybercrime is reported to be a “sophisticated attack” and explain how incentives align to misrepresent very run-of-the-mill events in this manner. We describe the cybercrime ecosystem, analysing the distinct parts and discussing what forms of sophistication and incentives can be found in each kind of work. We move on discuss how framing cybercrime as technically sophisticated attacks performed by skilled criminals has distorted criminological analysis and contributed to misaligned incentives within criminal justice and security policy. We conclude that the criminal justice system is aiming the wrong types of interventions at the wrong kinds of actor.

La cuestión es que nadie hace casi nunca más trabajo del necesario y que, en muchos casos, con poco esfuerzo se consiguen grandes resultados, al menos en el mundo de los ataques informáticos.

De las conclusiones:

> We argue that this mis-attribution of sophistication is not a mere irritation or fringe issue, i.e. something which security professionals and academics might decry on social media but which bears no real impact; it is in fact contributing to a far wider mood music within law enforcement and sentencing practice, and academia that has had serious negative effects. As long as this narrative of sophistication persists, it creates perverse incentives to widen the net of law enforcement, to design interventions along misleading lines, and to draw attention away from the real drivers of harm.

Esto es, no hay tantos expertos capaces de realizar atanques verdaderamente sofisticados y esta banalización de la información puede llevarnos a tomar malas decisiones y a enfocar el problema de manera inadecuada.

En el artículo definen media docena de tipos de atacantes, que puede ser interesante señalar:

* Expertos en investigación básica y cambios de paradigma *Hacking – basic research and paradigm shifts*.

En este caso hablamos de incentivos y motivaciones económicas complejas, aunque esta es una pequeña parte de todo el ecosistema.
Es costosa en tiempo, conocimientos, ...

* Atacantes avezados, expertos en penetración y amenazas persistentes avanzadas *Skilled actors, penetration testers and APTs*.

Aquí ya tenemos a personas con buenos conocimientos de lo que han encontrado otros. Son hábiles en aplicar este conocimiento y realizar los ataques. Aquí entraría la parte económica relacionada con la realización del ataque (o la defensa) y la venta de este conocimiento a quien lo pueda demandar.

* Constructores de herramientas y proveedores de infraestructura *Tool builders and infrastructure providers*

Los ataques se han convertido en muchos casos en ataques como servicio *‘crime as a service*, lo que significa que aparecen organizaciones que proporcionan las herramientas para que otros las usen en su propio beneficio. Esto ocurre tanto en las herramientas de ataque, como en la infraestructura necesaria para desplegarlas y no tener que preocuparse demasiado de ellas.

* Emprendedores *Entrepreneurs*

Esencialmente, los usuarios de las herramientas y los servicios anteriores, que sacan provecho de su conocimiento de la infraestructura.

* Piratillas y ladrones de poca monta *‘Script kiddies’ and petty fraudsters*

Son gente que está empezando y que usan los servicios de otros sin mucho conocimiento, simplemente siguiendo guías y recomendaciones que otros han preparado.

* Hacktivistas y otras personas sin motivación económica *Hacktivists and other non-monetary motives*

No sólo hay gente interesada en estos asuntos por el dinero, sino también por ideales, ideología o principios 'más elevados'. Son pocos, muy motivados y con muy diversos niveles en sus capacidades tecnológicas.

Por cierto, que esta clasificación me ha recordado otro artículo interesante [I Watched You Roll the Die: Unparalleled RDP Monitoring Reveal Attackers' Tradecraft](https://www.blackhat.com/us-23/briefings/schedule/index.html#i-watched-you-roll-the-die-unparalleled-rdp-monitoring-reveal-attackers-tradecraft-33110) donde clasificaban a los atacantes en cinco categorias: 

* Bardos (*bards*), sin un gran nivel cuyo único objetivo es usar sistemas informados para sus propios intereses (muchas veces de simple entretenimiento, accediendo a recursos que no tienen disponibles por el motivo que sea).

* Guardabosques (*rangers*), que exploran los sistemas y encuentran algunos vulnerables o poco progegidos, abriendo el camino para otros atacantes.

* Ladrones (*thieves*), que son los que tratan de obtener beneficio económico de los sistemas atacados.

* Bárbaros (*barbarians*), que serían los que usan herramientas, básicamente mediante fuerza bruta, para entrar en diversos sistemas.

* Magos (*wizards*), que  utilizan estos recursos para esconder su verdadero oriigen y poder realizar acciones de su interés.

En este caso se trata de una *honeynet* utilizada para ver cómo se comportaban diferentes agentes que utilizan ataques a través de las herramientas de escritorio remoto *RDP*. Los autores habrían observado a los atacantes y su actividad cuando descubrían los recursos vulnerables.

Se puede leer algo de información en [How Unparalleled RDP Monitoring Reveal Attackers’ Tradecraft](https://www.gosecure.net/blog/2023/08/09/how-unparalleled-rdp-monitoring-reveal-attackers-tradecraft/)
