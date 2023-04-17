---
layout: post
title: "Inyección de fallos en eBay para conseguir sistemas más robustos"
date: "2023-04-17 15:00:00 +0000"
category: código
tags:
- desarrollo
- código
- inyección
- fallos
imagefeature: 'https://live.staticflickr.com/2300/2057080889_26faf3ac79.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/2057080889/" title="Mi nueva pistola "><img src="https://live.staticflickr.com/2300/2057080889_26faf3ac79.jpg" alt="Mi nueva pistola " class="img-responsive img-centered"></a>

Ya hemos hablado algunas veces de *fuzzing* para tratar de mejorar la calidad de las aplicaciones: la idea es probar a enviar entradas aleatorias (basura) a nuestras aplicaciones y estudiar como fallan.
Traemos hoy aquí un artículo donde se habla de [How eBay’s Notification Platform Used Fault Injection in New Ways](https://tech.ebayinc.com/engineering/how-ebays-notification-platform-used-fault-injection-in-new-ways/). No se trata exactamente de inyección de entradas aleatorias, pero sí de provocar fallos de manera deliberada, con el objetivo de observar cómo se comporta la plataforma.

>  Fault injection is the process by which we deliberately introduce faults into the system. We can observe the system behavior with the injected faults to identify the weakness of the system.

Como se trata de una plataforma de la que dependen otras, el objetivo es ver qué sucederá al introducir los problemas cuando estos sistemas reciban las respuestas defectuosas provacadas por los fallos.

> Any faults in these dependent services will directly impact the stability of the system, so it’s quite valuable to run experiments in the system containing the failures of these dependencies, in order to understand the behaviors and mitigate any weaknesses. 

El tipo de fallos de los que estamos hablando son muy diversos: desde fallos de red (desconectar la conexión temporalmente, por ejemplo), llenar un sistema de ficheros (para provocar fallos de falta de espacio), a nivel de infraestructura.

> For example, to introduce the http disconnection or timeout error, one option is to turn off the network or shut down the downstream services temporarily; to introduce the disk full error, one option is to create a bunch of files in the file system.

Pero también podemos pensar en crear fallos a nivel de la aplicacion. En lugar de desconectar una interfaz de red, insertar en la biblioteca correspondiente algún retraso significativo. O, directamente, un código de respuesta de error.

> For example, to inject the http timeout fault, we add the latency in the http client library; to simulate the internal service error, we simulate the response code with 500 http status code. The faults are restricted to the API level and do no harm to the underlying infrastructure resources. 

Para conseguir este tipo de fallos lo que se hace es instrumentar las bibliotecas correspondientes (esto es, modificarlas para que contengan las respuestas que nos interesa que aparezcan).

> To simulate the faults for the client libraries by instrumentation is challenging. Our main task is to force the invoked methods to experience failures. One method to do this is to inject failure directly into the method, by, for example, throwing the exception in the method body.

Fundamentalmente, se utilizan tres métodos: bloquear o interrumpir la lógica del método, cambiar el estado de los parámetros del método, o reemplazar el valor de los parámetros del método.

> 1. Block or interrupt the method logic
> 2. Change the state of method parameters 
> 3. Replace the value of method parameters

Para poder manejar todo esto con cierta soltura parece imprescindible poder cambiar el contexto con facilidad, y para eso es necesaria una buena gestión de configuraciones.

> To dynamically change the configuration for the fault injections in the runtime, we have implemented a configure management console in the Java agent. 

Muy interesante.
