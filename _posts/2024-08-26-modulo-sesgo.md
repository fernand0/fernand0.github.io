---
layout: post
title: "Operaciones modulares y sesgos en la aleatoriedad"
date: "2024-08-26 15:00:00 +0000"
category: seguridad
tags:
- sesgos
- modulo
- números
- aleatoriedad
imagefeature: "https://live.staticflickr.com/1255/1301539362_daa1107f13_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/1301539362/in/photolist-2Z1JiQ-qRSfg-5mvoPy" title="Los dados del r5"><img src="https://live.staticflickr.com/1255/1301539362_daa1107f13_z.jpg" width="480" height="640" alt="Los dados del r5"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

El diablo está en los detalles y la realidad se empeña en mostrárnoslo (poco a poco, eso sí) continuamente. En este caso, [The definitive guide to “Modulo Bias and how to avoid it”!](https://research.kudelskisecurity.com/2020/07/28/the-definitive-guide-to-modulo-bias-and-how-to-avoid-it/) habla de lo que llaman sesgo del módulo (*modulo bias*), y sus consecuencias.

Como sabemos, nos dice, las operaciones modulares se utilizan ampliamente en criptografía,  y también en informática en general.

> The modulo operation is used a lot in Cryptography, since we are usually dealing with number theory and algebraic structures that rely on the modulo operation at their core. But it is also used more broadly in Computer Science. It is typically represented in code by the symbol % and it is a binary operator that will take two integers as input and give one integer as output.

Pero el sesgo aparece cuando elegimos un número aleatorio y queremos obtener valores en un determinado rango. La causa es que típicamente utilizaremos un generador que proporciona números en otro rango diferente, y nosotros haremos la conversión. Pero si la cantidad de números de uno y otro rango no son compatibles (la grande es múltiplo de la pequeña), nos vamos a llevar un disgusto si medimos las frecuencias de los números generados: los primeros (el exceso de ese múltiplo) va a estar ligeramente sobre-representados.

> The problem is basically the same as when you’re cutting a rope into smaller pieces of a given size: the last piece will most likely not be of the same size as the others, except if the initial length of your rope was perfectly divided by the length of the pieces.

No parece un problema muy grave, nos dice, pero quién sabe por dónde pueden evolucionar las técnicas de criptoanálisis.

> It is true in general that biases are “just” reducing the actual entropy of a randomly generated value and thus are not as dangerous as for the above schemes, but future cryptanalytic breakthroughs might exploit them. As such we definitively prefer to have uniformly distributed random values, plus they also usually allow us to really rely on the mathematical proofs of security, when we have one.

¿Se puede remediar?

Existen varias formas, la primera sería descartar los valores que no pertenecen a nuestro rango a la hora de obtener números aleatorios.

> Rejection sampling consists in sampling a random value and rejecting all values that do not fall into the right range.

El problema de este método es que si la diferencia entre rangos es muy grande podemos añadir un coste extra a la obtención de valores. Se puede aliviar un poco truncando el número al tamaño adecuado, pero no resuelve el problema completamente.

Otra posibilidad es seguir usando el módulo, pero teniendo en cuenta las limitaciones señaladas: esencialmente se puede utilizar el módulo para un conjunto de valores 'equilibrado'; esto es, los números del final, que son los que nos provocarían las desigualdades pueden ser rechazados cuando salgan y calcular el módulo para el resto.

> As we discussed earlier, if you are generating a value between 0 and 106, using one byte of randomness, then you can combine both rejection sampling and modulo reduction

Siguen pudiendo aparecer problemas, sobre todo si el exceso de números con respecto a la operación modular es grande.

Me gustó mucho leerlo, y no era consciente del problema, la verdad.
