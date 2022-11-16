---
layout: post
title: "Desarrollo de criptografía para no especialistas"
date: "2022-01-17 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- desarrollo
- criptografía
imagefeature: 'https://live.staticflickr.com/282/32534213772_0900d11508.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/32534213772/" title="Candados y cintas rojas "><img src="https://live.staticflickr.com/282/32534213772_0900d11508.jpg" alt="Candados y cintas rojas " width="240" style="float:left; margin:5px"></a>
En [Cryptography is not Magic](https://loup-vaillant.fr/articles/crypto-is-not-magic) hablan sobre el tema de diseñar sistemas criptográficos y programarlos.

Trata de atraer a más desarrolladores a la materia porque, afirma, los consejos habituales hacen que alguna gente se eche para atrás.

Sin embargo, nos dice, la realidad es que programar primitivas criptográficas requiere poco conocimiento sobre criptografía. Lo más delicado sería la elección de cuales (por aquello de no elegir algún método obsoleto).

> Perhaps surprisingly, implementing cryptographic primitives & protocols requires little cryptographic knowledge. Choosing what to implement is more delicate (you need to know the state of the art), but once you've made your choice, your only worries are side channels and correctness.

Nos habla sobre los canales laterales y remarca que la idea fundamental es no permitir el flujo de datos hacia ellos. La mayoría pueden ser ignorados sin demasiados problemas (energía, emisiones electromagnéticas, ...) pero que nunca hay que olvidar los relacionados con el tiempo.

> Side channels have one rule: don't let any data flow from secrets to that channel. Interesting side channels include timings, energy consumption, electromagnetic emissions… Most can be ignored most of the time (energy consumption for instance requires physical access), except timings. Never ignore timings, they're part of most threat models.

Sobre la corrección, nos avisa de su importancia: cualquier error hará que nuestro sistema sea inadecuado.

> Then we have correctness. The slightest error may throw cryptographic guarantees out the window, so we cannot tolerate errors. Your code must be bug free, period. It's not easy, but it is simple: it's all about tests and proofs.


Sobre el diseño de protocolos dice que si el desarrollo criptográfico es tedioso, el diseño de protocolos es delicado.

> That's where things become interesting. Where implementing crypto was mostly tedious, designing protocols is delicate. One is not necessarily harder than the other, but they're very different.

Habla de las amenazas para recordarnos que una vez que conocemos a las que se enfrentan nuestros casos de uso (*threat model*) es necesario demostrar que el protocolo las maneja adecuadamente.

> Once you know your threat model, you need to demonstrate that your protocol addresses it.

Termina diciendo que desarrollar nuestra propia criptografía no es sencillo. Es fácil equivocarse, pero eso no significa que no pueda hacerse

> I won't sugar coat it, rolling your own crypto is not easy. Mistakes are easy to make, and the stakes are often high — getting it wrong can even get people killed. Don't rush it, and if you can, seek guidance and feedback. Some communities are very welcoming.

En mi opinión, no es un campo donde yo me desenvolvería a gusto. Pero, tal vez, una aproximación más activa nos ayudaría a aprender y a mejorar.
