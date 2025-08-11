---
layout: post
title: "Manejo de errores en aplicaciones: algunas ideas y estrategias"
date: "2025-08-11 15:00:00 +0000"
category: desarrollo
tags:
- desarrollo
- arquitectura
- errores
- problemas
- gestión
imagefeature: "https://live.staticflickr.com/2044/1557977187_7383ad79f1_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/1557977187/in/photolist-3j8EhR-3nF3kD-vvAdGo-wqhJmU-wsB5YX-wt4Rep-4EoeJv-5oNqK9-7MgQmV-9Q1Pfj-arFkMV-aCC4NF-aCC4X6-aCEKBm-aCEKJC-ezqgNF" title="Teruel. Torre mudéjar."><img src="https://live.staticflickr.com/2044/1557977187_7383ad79f1_z.jpg" width="640" height="480" alt="Teruel. Torre mudéjar."/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

En [The Ultimate Guide to Error Handling in Python](https://blog.miguelgrinberg.com/post/the-ultimate-guide-to-error-handling-in-python) una lista de consejos sobre manejo de errores programando en Python que me gustó leer, aunque se pueden aplicar casi a cualquier otro lenguaje.

Primero comenta las dos aproximaciones típicas para afrontar los problemas:

- Mirar antes de avanzar (verificar que se cumplen las condiciones necesarias para realizar la acción que vamos a llevar a cabo).

> The "look before you leap" pattern for error handling says that you should check that the conditions for performing an action that can fail are proper before triggering the action itself.

El problema es que es difícil saber todo lo que puede salir mal a la hora de realizar una acción, así que es fácil que nuestro código siga teniendo problemas. También pueden aparecer condiciones de carrera (cuando algo cambia entre la verificación y la realización de la acción).

- Es mejor pedir perdón que pedir permiso (esto es, realizamos la acción y si falla, manejamos los errores).

> The competing pattern says that it is "easier to ask forgiveness than permission". What does this mean? It means you should perform the action, and deal with any errors afterwards.

El problema en este caso es que podemos capturar el fallo, pero es posible que en muchos casos la captura sea genérica, poco informativa y cuando vayamos a mirar lo sucedido no lo sepamos muy bien.

> On the other side, we need to know what exceptions to write down in the except clause, because any exception classes that we miss are going to bubble up and potentially cause the Python application to crash.

Una vez establecidas estas ideas nos lleva por algunos detalles interesantes.

Primero, saber si estamos ante un error, o se trata de un error de otra parte del código que nos llega.

>  You either need to introduce a new error yourself and put it in the system for some other part of the application to handle, or you received an error from somewhere else and need to decide what to do with it.

A continuación, hay que tener en cuenta que hay errores de los que nos podemos recuperar, y otros de los que no.

> Recoverable vs. Non-Recoverable Errors

Si encontramos errores de los que el código que tenemos es el responsble, podemos manejarlos, añadiendo instrucciones que gestionen el problema y nos permita continuar con la tarea.

> What do you think is the best way to handle this case? Well, recover from the error and continue, without bothering anyone else!

También puede ocurrir que los errores vengan de otra parte del código y en ese caso aplicamos la estrategia de mejor pedir perdón que pedir permiso, y añadimos instrucciones para remediar lo que tengamos entre manos.

> How do we handle this case? We use EAFP to catch the error, and then we do whatever needs to be done to recover from it and continue.

Pero también pueden aparece errores que no son recuperables. En este caso, podemos interrumpir la ejecución de esa parte del código y lanzar el error hacia arriba, con la esperanza de que en un nivel superior puedan manejarlo.

> The only reasonable action that can be taken is to stop the current function and alert one level up the call stack of the error, with the hope that the caller knows what to do.

De cualquier modo, habrá errores que nosotros no hayamos sido capaces de manejar, pero que los niveles superiores tampoco podrán.

> Now we have a piece of code that called some function, the function raised an error, and we in our function have no idea how to fix things up so that we can continue, so we have to consider this error as non-recoverable. What do we do now?

Al final, este tipo de errores podrían capturarse al máximo nivel para estar seguros de que el programa no hará nada extraño.

> The reason is that at this level we really cannot let any exceptions reach Python because we do not want this program to ever crash, so this is the one situation in which it makes sense to catch all exceptions.

También discute sobre si el tratamiento de errores se debería hacer a más bajo nivel o más alto, y es partidario de llevarlo hacia arriba, para tener código más limpio y fácil de mantener.

> In fact, you should design your applications so that as much code as possible is in functions that do not need to concern themselves with error handling. Moving error handling code to higher-level functions is a very good strategy that helps you have clean and maintainable code.

Cambiando el terreno, luego habla de los errores en producción frente a los errores en desarrollo. Parece claro que en la fase de programación el fallo catastrófico de una aplicación no debería ser un problema.
Incluso es bueno, porque nos permite encontrar los errores y poder arreglarlos.

> During development, there is actually nothing wrong with the application crashing and showing a stack trace. In fact, this is a good thing, since you want errors and bugs to be noticed and fixed.

Y también dice que es más fácil gestionarlo cuando los errores se manejan al máximo nivel (fuera de la lógica del programa).

> This becomes much easier to implement when the error handling is in one place and separate from the application logic.

Simplemente el tratamiento sería diferente: en desarrollo dejamos al programa fallar y que pase lo que tenga que psar; en producción, capturamos el problema, informamos y hacemos una salida 'limpia'.

> When we are running in development mode we now re-raise the exceptions to cause the application to crash, so that we can see the errors and the stack traces while working.

Interesante, recordatorio y organización de las ideas.



