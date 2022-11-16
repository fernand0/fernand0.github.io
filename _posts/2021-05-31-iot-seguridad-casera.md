---
layout: post
title: IoT, nuestra casa y la seguridad
date: 2021-05-31 15:00:00 +0000
category: seguridad
tags:
- IoT
- seguridad
- casa 
- ataques
- riesgos
- amenazas
imagefeature: 'https://avecesunafoto.files.wordpress.com/2019/06/img_20190518_103012.jpg'
---
<a href="https://avecesunafoto.wordpress.com/2019/06/21/puerta/" title="Puerta."><img src="https://avecesunafoto.files.wordpress.com/2019/06/img_20190518_103012.jpg" alt="Puerta." width="240" style="float:left; margin:5px"></a>
Troy Hunt ha estado domotizando su casa y ha escrito una serie de entradas sobre las decisiones que iba tomando. Me pareció particulamente interesante el aspecto de la seguridad, siendo un experto como es él. Lo contaba en [IoT Unravelled Part 3: Security](https://www.troyhunt.com/iot-unravelled-part-3-security/). 

En el internet de las cosas *IoT*, siempre se nombra la seguridad como una preocupación (dispositivos pequeños, poco potentes... Pero también falta de madurez, fabricantes muy diversos y algunos oportunistas...).
Lo resumía así:

> In part 1 of this series, I posited that the IoT landscape is an absolute mess but Home Assistant (HA) does an admirable job of tying it all together.

Algunos fabricantes ya dan cuenta de la seguridad con dispositivos que se actualizan automáticamente. Si nos salimos del camino, es posible que nos metamos en líos.

> For your average consumer (and remember, that's probably 99%+ of people buying TP-Link smart plugs), automatically updating firmware is key. For the rest of us, we need to recognise that we take on risks when using IoT devices in ways they weren't designed for. 
 
Otro debate interesante es analizar si nuestros dispositivos deben 'vivir' dentro de nuestra red local, o tener interacciones con la nube.

> This whole discussion about devices updating their firmware raised another philosophical debate which I want to delve into now, and that's the one about how self-contained the IoT ecosystem should be within the LAN versus having cloud dependencies.

La nube, y los fabricantes emergentes nos pueden colocar en situaciones comprometidas: ¿qué sucedería si el fabricante de nuestros dispositivos deja de proporcionar sus servicios?

> That resiliency extends beyond just a cloud outage too; what if Tuya shuts down the service? Still want to be able to turn your lights on? 

Desde un punto de vista, entonces, de seguridad y privacidad, parece natural apostar por aparatos que dependan exclusivamente de nuestra propia red.

> That said, from a simple security and privacy perspective (and often a performance perspective too), I always prioritise local communication. 

También hay que considerar la compartimentalización: una solución es aislar estos dispositivos en su propia red, para que si hay problemas de seguridad no afecten al resto de nuestra vida.

> One popular approach is to isolate the network the IoT things are on from the network the non-IoT things are on. This mindset is akin to putting all the potentially bad eggs in the one basket and the good eggs (such as your PC) in another basket.

Pero queremos poder controlar nuestros dispositivos desde nuestro 'dispositvo seguro' y empieza el lío de interactuar entre esas redes diferentes.

> The main problem is that you end up with all sorts of scenarios where a particular IoT device needs to see the app that controls it but because the very purpose of the VLAN is to lock the IoT things away, things would fail. 

Entonces, hay que asegurar la cosa, y ... usar sólo lo que realmente queramos/necesitemos, porque no podemos perder lo que no tenemos (por ejemplo, a la hora de apuntar una cámara):

> 1. You cannot lose what you do not have ... As it relates to my own approach to IoT, all cameras I have point at places that are publicly observable. 

Y, por lo tanto, más vale ser selectivos en lo que conectamos. Hace nuestro análisis de riesgos, decidiendo qué cosas buenas tendremos y qué cosas malas pueden pasar.

> 2. Be selective with what you connect: ... The point here is that I'm effectively doing my own little risk assessment on each IoT device, and you can too. What upside does it bring you? What downside does it present?

Finalmente, estar seguros de en quién confiamos. Fabricantes, instaladores, apartos...
Lo barato puede salirnos muy caro. Y, ojo, una marca conocida no siempre será una garantía de buena calidad.

> 3. Choose who to trust: ... These companies invest serious dollars in their security things in just the same way Amazon does with their Echo devices.

También hay que vencer la inercia: si no tenemos nada conectado, ¿por qué asumir ese riesgo? Hunt dice que su vida es mejor y más cómoda y, en ese sentido, puede valer la pena.

> There will be those who respond to this blog post with responses along the lines of "well, you really don't need any of these things connected anyway, why take the risk?" There's an easy answer: because it improves my life. 

Tampoco hay que olvidar que un experto puede hacer muchas cosas que alguien menos interesado no hará. Y allí puede estar el peligro para esta persona.

> Coming back to a recurring theme from this series, the security situation as it relates to normal everyday people using IoT devices isn't great and I've given plenty of examples of why that's the case. I also don't believe the approaches taken by enthusiasts solves the problem in any meaningful way ...


