---
layout: post
title: Algunos hallazgos sobre la seguridad de un marcapasos.
date: 2021-04-19 15:00:00 +0000
category: seguridad
tags:
- seguridad
- marcapasos
- medicina 
- vulnerabilidades
imagefeature: 'http://live.staticflickr.com/2301/1536605316_d158fb43bb.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/1536605316" title="Teruel. Corazones "><img src="http://live.staticflickr.com/2301/1536605316_d158fb43bb.jpg" alt="Teruel. Corazones " width="240" style="float:left; margin:5px"></a>
En la comunidad de investigadores es frecuente investigar con lo que se tiene más a mano que son los dispositivos caseros. Este es el caso de Marie Moe, que tiene implantado un marcapasos y se ha dedicado a analizar su seguridad, [Hacking Yourself: Marie Moe and Pacemaker Security](Hacking Yourself: Marie Moe and Pacemaker Security). 

Hace unos años inició su trabajo sobre la seguridad de los marcapasos y encontró cosas interesantes [ICS Medical Advisory (ICSMA-20-170-05)](https://us-cert.cisa.gov/ics/advisories/icsma-20-170-05). Fundamentalmente, problemas de:

* Autentificación incorrecta.
* Transmisión en texto claro de credenciales.
* Reutilización de credenciales.
* Almacenamiento de datos médicos en claro.
* Almacenamiento incorrecto de contraseñas en el dispositivo.

Es cierto que, aparentemente, no hay ataques conocidos públicos que saquen partido de estas vulnerabilidades y tampoco pueden usarse para cambiar la programación del dispositivo.

> Note for the record that so far, "no known public exploits specifically target these vulnerabilities," the Advisory says. Also note that these vulnerabilities can't be used to directly reprogram a pacemaker or hack someone's heart.

