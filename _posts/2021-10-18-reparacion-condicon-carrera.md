---
layout: post
title: "Una condición de carrera en el manejo de sesiones en GitHub "
date: "2021-10-18 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- desarrollo
- carrera
- sesiones
imagefeature: 'https//live.staticflickr.com/65535/49477090451_7df6db888a.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/49477090451/" title="Reloj y campanas "><img src="https://live.staticflickr.com/65535/49477090451_7df6db888a.jpg" alt="Reloj y campanas " width="240" style="float:left; margin:5px"></a>
En [How we found and fixed a rare race condition in our session handling](https://github.blog/2021-03-18-how-we-found-and-fixed-a-rare-race-condition-in-our-session-handling/) una historia sobre una condición de carrera en el manejo de sesiones en GiHub.

Las condiciones de carrera son fallos que aparecen en sistemas concurrentes, suelen ser difíciles de encontrar y solucionar, porque pueden aparecer o no, y podremos ver los resultados sólo en algunas ocasiones. Recordemos que una condición de carrera ocurre cuando se debe cumplir alguna condición durante un cierto tiempo pero, por algún motivo, esto no se cumple. Si nos encontramos en una situación así, el código se comporta como si la condición fuera cierta y los resultados pueden ser incorrectos.

Todo comienza cuando reciben un aviso de un usuario que habiéndose identificado con su usuario aparecía, de pronto, identificado como otro.

>  On March 2, 2021, we received a report via our support team from a user who, while using GitHub.com logged in as their own user, was suddenly authenticated as another user.

Aparentemente, el usuario recibía la respuesta correcta salvo la *cookie* de sesión que pertenecía a un usuario diferente.

> The affected users from the support reports received a session cookie from a user who very recently had a request handled inside the same process. In one case, the two requests were handled sequentially, one after the other. In the second case, there were two other requests in between.

Uno de los problemas de las condiciones de carrera es que son fallos que parecen casuales y suelen ser difíciles de redproducir. En este caso lo consiguieron,  determinando además que eran neceasrias algunas circunstancias adicionales.

> With this information, we tried to reproduce the issue in a development environment. When we attempted to sequence the exact requests, we found that one additional condition was needed and that was an anonymous request that started the whole sequence.  

En la entrada están los pasos, que no reproduciremos aquí. El resumen sería que podía ocurrir una excepción y a la vez se producían una serie de peticiones, la sesión era sustituida para el usuario.

> In summary, if an exception occurred at just the right time and if concurrent request processing happened in just the right sequence across multiple requests, we ended up replacing the session in one response with a session from an earlier response.  

Una vez detectado el problema, y solucionado para que no se volviera a producir era necesario saber quién podría haber estado afectado.

> In addition to fixing the underlying bug, we took action to make sure we identified affected user sessions. We examined our logging data for patterns consistent with incorrectly returned sessions. 

Para asegurarse de que todo sería correcto, el último paso fue revocar todas las sesiones activas.

> As a final step, we decided to take a further preventative action to ensure the safety of our users' data and revoked all active user sessions on GitHub.com.

Todo no termina aquí, porque ahora hay que asegurarse de que no puedan ocurrir fallos similares en otras partes del código.

> Lastly, we're looking at also improving the thread safety across our codebase in areas such as exception handling and instrumentation. We don't want to just fix this specific bug, we want to ensure that this class of issues can't happen again in the future 


