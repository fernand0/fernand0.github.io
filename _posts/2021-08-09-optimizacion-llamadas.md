---
layout: post
title: "Optimización con llamadas recursivas al final"
date: "2021-08-09 15:00:00 +0000"
category: desarrollo
tags:
- desarrollo
- programación
- recursividad
- transformación
- eficiencia
imagefeature: 'https://live.staticflickr.com/65535/51138531089_54bd94c69c.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/51138531089/in/dateposted/" title="Letras "><img src="https://live.staticflickr.com/65535/51138531089_54bd94c69c.jpg" alt="Letras " width="240" style="float:left; margin:5px"></a>
Algunas funciones recursivas se pueden convertir fácilmente en bucles (composiciones iterativas). En general se trata de una buena medida, porque evita las llamadas recursivas a la función y eso, por si solo, ya asegura una mayor velocidad de ejecución (todos sabemos que la llamada a la función provoca una serie de movmientos de información en la pila que tienen un coste, por pequeño que sea).

De eso hablan en [How Tail Call Optimization Works](https://eklitzke.org/how-tail-call-optimization-works). Nos explican cómo funcionan las llamadas a funciones, en particular la necesidad de copiar el contador de programa (*program counter*) en la pila, hacer un salto y luego otro...

> The PC is pushed onto the stack so the called function can return back to the right spot. To return from a function, a function executes ret which pops the top value on the stack and then jumps back to that location. 

Nos muestra el código en ensamblador y lo hace con bastante detalle. También cómo los compiladores son capaces de detectar los casos de este tipo de recursión 'al final' (*tail call optimization*) sustituyendo la llamada a la función  por un salto (esto es evitando la copia de datos y todo eso).

> This is tail call optimization. Tail call optimization happens when the compiler transforms a call immediately followed by a ret into a single jmp. This transformation saves one instruction, and more importantly it eliminates the implicit push/pop from the stack done by call and ret.

Una buena descripción del problema y la solución.
