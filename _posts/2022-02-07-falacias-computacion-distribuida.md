---
layout: post
title: "Algumos mitos sobre computación distribuida"
date: "2022-02-07 15:00:00 +0000"
category: desarrollo
tags:
- desarrollo
- computación
- distribuida
- redes
imagefeature: 'https://live.staticflickr.com/65535/51455780657_716abcbc56.jpg'
---
<a href="https://flickr.com/photos/fernand0/51455780657/" title="Nasas "><img src="https://live.staticflickr.com/65535/51455780657_716abcbc56.jpg" alt="Nasas " width="240" style="float:left; margin:5px"></a>
La computación distribuida trata de sacar partido de diferentes recursos de cálculo que podemos tener a nuestra disposición. Es un modelo que tiene sus ventajas (aumento de capacidad) y sus inconvenientes (complicaciones). En [Navigating the 8 fallacies of distributed computing](https://ably.com/blog/8-fallacies-of-distributed-computing) nos habla de algunos mitos.

Los mitos:

* La red es fiable. Las redes son complejas, dinámicas y a veces impredecibles. Hay demasiadas cosas que pueden fallar.

> Networks are complex, dynamic, and often unpredictable. Many reasons could lead to a network failure

* La latencia es cero. Mientras que en una red de área local esto puede ser cierto, en redes más amplias veremos rápidamente que no.

> Latency may be close to zero when you’re running apps in your local environment, and it’s often negligible on a local area network. However, latency quickly deteriorates in a wide area network. 

* El ancho de banda es infinito. Cuando usamos la red parece que no tenemos limitaciones, sin embargo, si tenemos que manejar volúmenes de datos importantes, encontraremos rápidamente las dificultades.

> ... the capacity of networks is not infinite (partially because our appetite for generating and consuming data has also increased). When a high volume of data is trying to flow through the network, and there is insufficient bandwidth support, various issues can arise...

* La red es segura. Nuevamente, muchas cosas pueden fallar:  fallos, vulnerabilidades, ataques, ...

> There are many ways a network can be attacked or compromised: bugs, vulnerabilities in operating systems and libraries, unencrypted communication, oversights that lead to data being accessed by unauthorized parties, viruses and malware, cross-site scripting (XSS), and DDoS attacks, ...

* La topología no cambia. La forma en que se conectan los equipos y las redes entre sí es algo más o menos permanente, menos cuando no lo es: fallos, accidentes, ... pero también reconfiguraciones y rediseños.

> In a nutshell, network topology refers to the manner in which the links and nodes of a network are arranged and relate to each other. In a distributed system, network topology changes all the time. Sometimes, it’s for accidental reasons or due to issues, such as a server crashing. Other times it’s deliberate — we add, upgrade, or remove servers.

* Hay un administrador. Si el sistema es muy pequeño, puede ser cierto (y también que no haya ninguno). En cualquier sistema un poco más grande las posibilidades aumentan.

> There might be only one administrator in the case of a very small system, or perhaps in the context of a personal project. Beyond that, there is usually more than one administrator of a distributed system in nearly all real-life scenarios.

* El coste de transporte es cero. Vivimos en la ficción de que el coste de enviar información por las redes es cero. Sin embargo, la infraestructura tiene coste, los aparatos también y luego hay que gestionar y mantener esos recursos.

> First of all, networking infrastructure has a cost. Servers, network switches, load balancers, proxies, firewalls, operating and maintaining the network, making it secure, not to mention staff to keep it running smoothly — all of these cost money. The bigger the network, the bigger the financial cost. 

* La red es homogénea. Esto no es cierto ni en una red doméstica. En muchos casos las redes van creciendo de forma casi orgánica, con sistemas diferentes, protocolos, etc.

> Often, not even your home network is homogenous. It’s enough to have just two devices with different configurations (e.g., laptops or mobile devices) and using different transport protocols, and your network is heterogeneous.

Como conclusión, lo que anticipábamos arriba: construir sistemas distribuidos es difícil.

> A brief conclusion: building distributed systems is hard
