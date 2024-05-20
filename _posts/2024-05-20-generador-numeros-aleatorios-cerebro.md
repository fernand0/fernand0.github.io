---
layout: post
title: "Un método sencillo de generación de números seudoaleatorios"
date: "2024-05-20 15:00:00 +0000"
category: aleatoriedad
tags:
- aleatoriedad
- RNG
- random
- programación
imagefeature: "https://live.staticflickr.com/1255/1301539362_daa1107f13_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/1301539362/in/photolist-2Z1JiQ-qRSfg-5mvoPy" title="Los dados del r5"><img src="https://live.staticflickr.com/1255/1301539362_daa1107f13_z.jpg" width="480" height="640" alt="Los dados del r5"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Entre lo poco que escribimos aquí y que hacía ya algún tiempo que no nos encontrábamos una lectura interesante ha pasado tiempo desde la última vez que hablamos de generadores de números aleatorios.

En [An RNG that runs in your brain](https://www.hillelwayne.com/post/randomness/) encontré un generador 'sencillo' e interesante. No sería válido para aspectos criptográficos y de seguridad, pero nos puede ayudar a comprender mejor el concepto. El proceso es:

> Elegir un número de 2 cifras, por ejemplo 23, la 'semilla'

> Generar un nuevo número de dos cifras a partir del primero: a las decenas les sumamos 6 veces las unidades.

> El resultado con nuestra semilla sería: 23 –> 20 –> 02 –> 12 –> 13 –> 19 –> 55 –> 35 –> ...

> su periodo es el orden del multiplicador, 6, en el grupo de los residuos primos relativos al módulo, 10. (59 en este caso).

> Los "dígitos aleatorios" son las cifras unidad de los números de dos cifras, esto es: 3,0,2,2,3,9,5,... la secuencia módulo 10.

La pregunta ahora es, ¿cómo de buenos son los números generados de esta forma?, y el autor nos muestra algo de la teoría (y algunas pruebas) que hay detrás del métido.

Y la siguiente, ¿con qué semillas y otras combinaciones de números funcionaría?

No vamos a entrar en ello, pero me gustó porque me parece un ejercicio sencillo (pero no trivial) de programación, que además nos ayuda a pensar un poco en los temas relacionados con la aleatoriedad en los sistemas informáticos.
