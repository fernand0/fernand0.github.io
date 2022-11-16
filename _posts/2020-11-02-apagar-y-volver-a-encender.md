--- 
layout: post
title: "Si quieres tener la información correcta en el avión, apaga y vuelve a encender"
date: "Mon Nov 02 15:02:01 +0100 2020"
category: seguridad
tags: [seguridad, avión, aviación, sistemas, apagar, encender]
imagefeature: http://live.staticflickr.com/5521/29714269554_275366bec3.jpg
---

<a href="https://www.flickr.com/photos/fernand0/29714269554/" title="Alavionismo "><img src="http://live.staticflickr.com/5521/29714269554_275366bec3.jpg" alt="Alavionismo " width="240" style="float:left; margin:5px"></a>
El viejo truco informático, sobre todo en sistemas domésticos o poco comprometidos, es apagar y volver a encender el sistema en cuestión antes de dar ningún otro paso. Eso no siempre es posible, y uno esperaría que en sistemas más profesionales esto no fuera necesario.
Sin embargo, y en el apartado de cosas que uno no esperaría que puedan suceder en este curioso artículo [Boeing 787s must be turned off and on every 51 days to prevent 'misleading data' being shown to pilots](https://www.theregister.com/2020/04/02/boeing_787_power_cycle_51_days_stale_data/) nos cuentan que los sistemas informáticos de estos aviones necesitan apagarse y volverse a encender para estar seguros de que mostrarán la información correcta a los pilotos.

Como anécdota personal, en cierta ocasión no funcionaba el sistema de entretenimiento (la pantallita) y la azafata la arregló apagando y volviendo a encender mi ordenadorcito, no sin insistir un poco porque no parecía darle importancia.

Esta necesidad viene en forma de orden de la Administración Federal de Aviación de EEUU:

> The US Federal Aviation Administration has ordered Boeing 787 operators to switch their aircraft off and on every 51 days to prevent what it called "several potentially catastrophic failure scenarios" – including the crashing of onboard network switches.

El problema sería que los pilots podrían ver información incorrecta:

> According to the directive itself, if the aircraft is powered on for more than 51 days this can lead to "display of misleading data" to the pilots, with that data including airspeed, attitude, altitude and engine operating indications. On top of all that, the stall warning horn and overspeed horn also stop working.

Por devolver la fe sobre estas cosas siempre le podemos echar la culpa en el caso del Boeing a que se trata de  sistemas antiguos. El otro día podíamos leer [U.S. Air Force Performs First Ever Code Change On A Flying U-2 Spyplane Running Kubernetes](https://theaviationist.com/2020/10/19/u-s-air-force-performs-first-ever-code-change-on-a-flying-u-2-spyplane-running-kubernetes/).
Allí nos explican un caso de un avión espía U-2 actualizando código mediante este sistema de contenedores, en vuelo.
Eso sí, no está claro el alcance de la actualización.

> We don’t have the whole details here, so the extent of the “update” is not clear (actually, the deployment of a new container in Kubernetes can be seen more like a configuration update than a code change). Anyway, the achievement of the latest milestone proves that the U.S. Air Force is continuing to advance in its program to give its weapons system the ability to leverage the power of containerization.

Interesante.

**Actualización (2020-11-03):** En otros modelos de la casa, nos enteramos de que [Boeing 747s still get critical updates via floppy disks](Boeing 747s still get critical updates via floppy disks). 

> Pen Test Partners discovered a 3.5-inch floppy disk drive in the cockpit, which is used to load important navigation databases. It’s a database that has to be updated every 28 days, and an engineer visits each month with the latest updates.
