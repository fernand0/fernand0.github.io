--- 
layout: post
title: "Vulnerabilidades frecuentes en 'smart contracts'"
date: "Tue Oct 13 15:02:01 +0100 2020"
category: blockchain
tags: [desarrollo, blockchain, smart contracts, seguridad, problemas]
imagefeature: http://live.staticflickr.com/4115/4934690400_7359ac5382.jpg
---

<a href="https://www.flickr.com/photos/fernand0/4934690400/" title="Libro. Contrato con Dios "><img src="http://live.staticflickr.com/4115/4934690400_7359ac5382.jpg" alt="Libro. Contrato con Dios " width="240" style="float:left; margin:5px"></a>
De la mano de *blockchain* han venido los *smart contracts*: se trata de 'programas' o 'codificaciones' de intenciones, condiciones y consecuencias que gracias a esta tecnología permitirían que determinados contratos puedan ejecutarse sin necesidad de que los humanos intervengan (en la realización de los hechos del contrato en sí, se entiende).

Desde la ignorancia informada, uno siempre ha pensado que si se ha de codificar determinadas condiciones de la vida en un contrato la cosa ya es suficientemente compleja. Si a eso le añadimos la ejecución automatizada, es probable que haya que hilar más fino. Y, claro, aparecen los *bugs* y las vulnerabilidades.

De esto hablaban en [Las 5 vulnerabilidades más habituales de los Smart Contracts](https://www.securityartwork.es/2020/03/10/las-5-vulnerabilidades-mas-habituales-de-los-smart-contracts/) y lo más gracioso es que los fallos se parecen mucho a los de los programas 'normales'.

* Errores aritméticos con números enteros

Desbordamientos, falta de precisión, ...

* Vulnerabilidades del límite de block gas

> El límite de block gas es la forma que tiene Ethereum de asegurarse de que los bloques no crezcan demasiado. Simplemente significa que los bloques están limitados en la cantidad de gas que las transacciones contenidas en dichos bloques pueden consumir. En pocas palabras, si una transacción consume demasiado gas nunca cabrá en un bloque y, por lo tanto, nunca se ejecutará.

En determinadas circunstancias esto provoca que haya instrucciones de los contratos que nunca llegan a ejecutarse.

* Falta de parámetros o controles de precondición

Si hace falta que algo se cumpla a la hora de ejecutar un contrato, debemos estar seguros de que los datos que se reciben son adecuados.

* Frontrunning

> El frontrunning potencial es probablemente el tema más difícil de prevenir en nuestra lista de vulnerabilidades comunes. Este puede definirse como la apropiación de una transacción no confirmada, y es consecuencia de la propiedad de transparencia del blockchain.

* Bugs de lógica simples.

No hace falta buscar, de todas formas, fallos muy sofisticados. Parece que es frecuente encontrar:

> ... el problema más común que detectamos es la presencia de errores simples en la lógica del smart contract. Estos errores pueden ser el resultado de una simple errata, una mala comprensión de la especificación o un error de programación mayor ...

Interesante.
