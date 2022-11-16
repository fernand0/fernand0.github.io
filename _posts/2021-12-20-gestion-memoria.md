---
layout: post
title: "Desbordamientos de enteros en aplicaciones del mundo real"
date: "2021-12-20 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- desarrollo
- desbordamiento
- enteros
- memoria
imagefeature: 'https://live.staticflickr.com/3413/4601500347_28e2118e04.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/4601500347/" title="El sorteo del Stock Travel Day. Números mágicos "><img src="https://live.staticflickr.com/3413/4601500347_28e2118e04.jpg" alt="El sorteo del Stock Travel Day. Números mágicos " width="240" style="float:left; margin:5px"></a>
Parece que no aprendemos nada: la gestión de memoria es uno de los problemas bien conocidos en los programas desarrollados en el lenguaje C. Seguimos encontrándolo casi donde miremos: en muchos casos porque hacemos desrrollos rápidos para avanzar, y en otros porque ni siquiera miramos.

En [BadAlloc: Microsoft looked at memory allocation code in tons of devices and found this one common security flaw](https://www.theregister.com/2021/04/29/microsoft_badalloc_iot/) lo cuentan desde una perspectiva informativa, y en [“BadAlloc” – Memory allocation vulnerabilities could affect wide range of IoT and OT devices in industrial, medical, and enterprise networks](https://msrc-blog.microsoft.com/2021/04/29/badalloc-memory-allocation-vulnerabilities-could-affect-wide-range-of-iot-and-ot-devices-in-industrial-medical-and-enterprise-networks/) desde una perspectiva más ténica. Nos hablan del tema, relacionado con un montón de dispositivos de IoT, industriales, médicos... donde además el problema se agrava porque la cultura de actualización está mucho menos extendida.

Cuando se habla de gestión de memoria, lo primero que nos viene a la cabeza es un desbordamiento de la zona reservada, pero hay más casos. Por ejemplo, desbordamientos de enteros. En este caso fuerzan la reserva de cantidades de memoria muy grandes. Esto es, en este caso no nos pasamos del tamaño reservado, pero reservar un espacio demasiado grande es también un problema. A veces.

> The team found a programming blunder common among much of the software: integer overflows during heap memory allocation. This occurs when an attacker is able to, usually via malicious data inputs, trick application code into making a very large memory allocation for a buffer to hold further incoming information.

Tiene que ver con que se trata de dispositivos de 32 bits y la aritmética relacionada con ello.

> The trouble is that a vulnerable memory allocator could take that large size – eg, 0xffffffff on a 32-bit embedded system – and add something like 8 to it because the requested memory block needs eight bytes of metadata to describe it. The size then overflows to 7 and the allocator finds space in memory that's seven bytes in size for the requested buffer.

Esto supone que, en las condiciones adecuadas, estaríamos asignando memoria más allá de lo que es posible y permitiendo sobreescribir valores importantes.

> This causes the application to overwrite the memory allocation metadata, structures, and contents. Now the attacker who sent over the data can take full control of the system by overwriting function pointers or altering other values.

Del desbordamiento de enteros se habla todavía menos que del desbordamiento de memoria y este será, a partir de ahora, uno de mis ejemplos favoritos sobre el tema.
