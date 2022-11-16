---
layout: post
title: No desarrolles tu propia criptografía
date: 2021-03-30 15:00:00 +0000
category: seguridad
tags:
- seguridad
- criptografía
- cifrado
- protocolos
- implementación
imagefeature: 'http://live.staticflickr.com/7602/16880496915_0e7618390c.jpg'

---
<a href="https://www.flickr.com/photos/fernand0/16880496915" title="Libro. ¿Qué son y para qué sirven los numeroso? "><img src="http://live.staticflickr.com/7602/16880496915_0e7618390c.jpg" alt="Libro. ¿Qué son y para qué sirven los numeroso? " width="240" style="float:left; margin:5px"></a>
En cualquier texto de seguridad informática que miremos por ahí leeremos el consejo de 'no desarrollar nuestra propia criptografía'. En [So you want to roll your own crypto?](https://vnhacker.blogspot.com/2020/08/so-you-want-to-roll-your-own-crypto.html?m=1) hay ideas interesantes sobre el tema.

Parte de una pregunta que no es despreciable: ¿cómo vamos a aprender (de nuestros errores) si no podemos hacer nuestra propia criptografía?

> How are people supposed to learn (from mistakes) if they don't roll their own crypto?

Y la respuesta también es secncilla: hazlo, pero no utilices lo que hagas en producción.

> The short answer is do roll your own crypto, but don't use it in production until it's vetted by professionals. The long answer below might take a few years to hash out.

Equivocarse es un proceso inevitable para conseguir aprender (y aquí hablamos en sentido amplio) aunque también podemos aprender de los errores de otros. Cursos, retos,  ...

> I found that the cheapest way to learn from mistakes is to learn from other people’s mistakes. I recommend taking Cryptography I, doing CTFs, and solving crypto challenges. This won't take long, and very quickly you'd be pretty dangerous because you'd be able to find many crypto bugs.


Sin embargo, todo esto puede ser insuficiente. Leer código es una buena forma de aprender, pero en criptografía esto no es tan sencillo.  El código no es obvio, tiene detalles sutiles y la mala criptografía produce muchas veces resultados indistinguibles de la buena.

> They say you can become a better programmer by reading good code. Unfortunately, I've learned the hard way that this rule usually does not work in crypto, ...

Tampoco hay un buen sustituto de aprender los fundamentos. Sin embargo, después de conocerlos a lo mejor tampoco es un buen momento para desarrollar nuevos sistemas criptográficos, porque el campo es amplio y cada una de sus partes tiene sus propias características.

> The funny thing is that after spending years studying these resources, you still don’t have a free pass to roll all the crypto in the world. You'd realize and appreciate that crypto is a deep and vast field of study with a very long food chain. Sitting on top are cryptanalysts who...

Y tampoco hay que olvidar las interacciones entre ellas.
Esto significa que incluso utilizando los protocolos desarrollados por otros nos podemos equivocar (y lo haremos).

Así que la conclusión es que deberemos estar seguros de que comprendemos bien lo que tenemos entre manos, y estudiar para eliminar nuestras limitaciones.

> So if you want to roll your own crypto, make sure you understand where you are in the crypto food chain and what are the reasons preventing you from moving up. Study and eliminate said reasons. Good luck and have fun!
