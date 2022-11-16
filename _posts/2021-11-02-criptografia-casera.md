---
layout: post
title: "Estás desarrollando tu propia criptografía. Y (¿no?) lo sabes."
date: "2021-11-02 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- criptografía
- protocolos
- desarrollo
imagefeature: 'http://live.staticflickr.com/4771/39855842155_056cf6ec83.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/39855842155/" title="Enigma "><img src="https://live.staticflickr.com/4771/39855842155_056cf6ec83.jpg" alt="Enigma " width="240" style="float:left; margin:5px"></a>
Uno de los consejos que siempre se da con respecto a la criptografía es no meterse en ese negociado sin experiencia (*“don’t roll your own crypto”*). 

De este tema se habla en [Actually, You Are Rolling Your Own Crypto](https://galois.com/blog/2021/03/actually-you-are-rolling-your-own-crypto/).

Así que solemos preocuparnos por los algoritmos y, sin embargo, lo cierto es que solo son una parte del tema. Luego hay que tener en cuenta más aspectos, que podrían tener consecuencias nefastas.

> What they might not realize is that the algorithms themselves are the first in a series of traps, each of which can have catastrophic effects on the outcomes of cryptography use.

La elección de los algoritmos, su uso y su inclusión en otros procesos (protocolos) también tienen sus dificultades.

> Algorithm selection, algorithm use, and protocol creation are all potential pitfalls that await once you’ve decided not to create your own algorithm. 

En cuanto a la selección de algoritmos, podemos empezar por la diferencia entre criptografía simétrica y asimétrica, y dentro de ellas las distintas opciones disponibles.

> There are a massive number of existing algorithms that do a wide range of things. The encryption space, for example, can first be broken down into symmetric and asymmetric. Each of those categories has a number of usable algorithms, and many of those algorithms have some other number of usable modes. 

No sólo eso, no hay que olvidar que esos algoritmos pueden quedarse obsoletos con el tiempo (y por eso no comentaremos nada aquí sobre ellos).

En cuanto al uso, comenta que hay que tener cuidado con las opciones, como se inicializan... sin olvidar que hay que tener en cuenta nuestro contexto y luego elegir las implementaciones.

> So you’ve chosen a secure algorithm in a secure mode that fits your operational environment. Now you need an implementation, no problem!...

Y ahora, hay que usarlos dentro de un proceso que permite algún tipo de comunicación segura: un protocolo. Es posible que no haya ninguno que se adapte bien a nuestro caso y entonces comienzan nuestros problemas.

> your crypto is probably going to be deployed inside a protocol scheme that enables secure communication. When it comes to protocols, there is rarely an off-the-shelf solution. As a result, developers are often forced to implement their own protocols, even though they understand it is risky.

Muchas veces serán modificaciones de otros conocidos, pero que necesitamos adaptar a nuestras necesidades. Y aquí podríamos estar introduciendo debilidades, o suponiendo propiedades que no se cumplirán en el nuevo contexto.

> They frequently need to be modified to meet the constraints of a particular operating environment. What’s often overlooked is that even small deviations to the designs can completely invalidate a security argument. What’s more, the threat model under which the original protocol was designed may not be valid for the environment in which it is deployed. 

El consejo sería utilizar los bloques predefinidos más grandes posibles que se adapten a nuestras necesidades. Primitivas de alto nivel, protocolos ya desarrollados y, en general, algo que sea de uso amplio y que no tenga muchas opciones para configurarlo.

> always use the biggest pre-built building blocks possible that meet your needs. For primitives, you can consider using the highest level interfaces of a library such as NaCl. For protocols, see if something such as an existing TLS implementation will meet your needs. In general, something widely used and with fewer configuration choices will be harder to misuse than something highly configurable.


Interesante.
