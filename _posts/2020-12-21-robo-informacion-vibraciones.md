--- 
layout: post
title: "Técnicas novedosas de exfiltración de información: la vibración de los ventiladores"
date: "Mon Dec 21 15:02:01 +0100 2020"
category: seguridad
tags: [seguridad, espionaje, robo, información, exfiltrado, ventilador, vibraciones]
imagefeature: http://live.staticflickr.com/7476/15716695910_15030e55a7.jpg
---

<a href="https://www.flickr.com/photos/fernand0/15716695910/" title="Libro. Un médico novato "><img src="http://live.staticflickr.com/7476/15716695910_15030e55a7.jpg" alt="Libro. Un médico novato " width="240" style="float:left; margin:5px"></a>
Casi a título de inventario. Hay gente que se dedica a ver cómo se puede extraer información de un sistema a través de diversas aproximaciones 'laterales'  (el reflejo de la pantalla, el ruido del teclado, ...). En el propio artículo hay una buena lista.
En [Academics steal data from air-gapped systems using PC fan vibrations](https://www.zdnet.com/article/academics-steal-data-from-air-gapped-systems-using-pc-fan-vibrations/) hablan de utilizar las vibraciones del ventilador del PC.

La idea es que pueden robar información a través de ventiladores instalados en un PC para crear vibraciones controladas.

> Academics from an Israeli university have proven the feasibility of using fans installed inside a computer to create controlled vibrations that can be used to steal data from air-gapped systems.

El objetivo es tratar de extraer información sin ser detectado.

> Guri's research doesn't look at ways of compromising and planting malware on these super-secure systems but instead focuses on innovative and never-before-seen ways of getting the data out, without being detected, and through methods that network defenders are not aware of.

En este caso se instala software malicioso, que puede controlar la velocidad del ventilador (en particular, rebajarla) y utilizarla para transmitir información del mismo.

> Guri says that malicious code planted on an air-gapped system can control the speed at which fans work. By moderating fan speed up and down, the attacker can control the frequency of the vibrations coming off the fan.

Un atacante cercano puede grabar esos cambios en las vibraciones y decodificar la información 'transmitida'.

> Guri says that a nearby attacker can record these vibrations using accelerometer sensors found in modern smartphones, and then decode the information hidden in the vibration pattern to reconstruct the information stolen from the air-gapped system.

Este método no sería muy rápido pero, desde luego, abriría una vía de escape para la información.

> However, while the AiR-ViBeR technique is some pretty innovative work, transmitting data through vibrations is extremely slow.

Aunque, también reconocen que no es muy realista pensar que sea una buena solución.

> While the AiR-ViBeR attack might be deemed "feasible," it is highly unrealistic that attackers would ever use it in the wild, as they would most likely opt for other techniques that exfiltrate information at faster speeds.
