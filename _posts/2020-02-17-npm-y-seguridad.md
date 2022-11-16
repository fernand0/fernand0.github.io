--- 
layout: post
title: "¿Depende tu sistema de programas vulnerables?"
date: "Tue Feb 17 15:05:01 +0100 2020"
category: seguridad
tags: [seguridad, desarrollo, dependencias, npm, vulnerabilidades]
imagefeature: http://live.staticflickr.com/2348/2137644411_23bae9346f.jpg
---

<a href="https://www.flickr.com/photos/fernand0/2137644411/" title="¡Oh! ¡Qué bonito! "><img src="http://live.staticflickr.com/2348/2137644411_23bae9346f.jpg" alt="¡Oh! ¡Qué bonito! " width="240" style="float:left; margin:5px"></a>
Cada vez vivimos un mundo más cómodo en informática: ya no hay que descargarse un código fuente y seguir las instrucciones de compilación e instalación sino que cada vez el modelo 'tienda' se extiende más y todo se basa en sistemas que nos evitan este trabajo. Hace algún tiempo hablábamos de [Los nombres y la seguridad. El caso de Python y PyPi](https://fernand0.github.io/Python-Y-Ocupacion-Nombres/) donde el caso se daba en un conocido sitio de descarga de módulos en Python y ahora podemos hablar de [Small world with high risks: a study of security threats in the npm ecosystem](https://blog.acolyer.org/2019/09/30/small-world-with-high-risks/).
En este caso se habla de las dependencias entre distintos paquetes y cómo eso puede hacer problemáticos un montón de desarrollos.

Nos hablan de un estudio sobre 'npm' (el sistema de paquetes para JavaScript) donde podemos ver el grafo de paquetes y sus mantenedores a lo largo del tiempo.

> This is a fascinating study of the npm ecosystem, looking at the graph of maintainers and packages and its evolution over time.

Un gran poder, una gran responsabilidad. Esto es, se habla de las cosas malas que pueden pasar cuando dependemos de un ecosistema que se mueve demasiado rápido.

> ...  the high risks involved in depending on a open and fast-moving ecosystem.

Con algunos paquetes como dependencias de ... demasiados paquetes.

> Looking at this in the other direction, we can consider the package reach of a package as the number of other packages that directly or indirectly include it. In other words, if a given target package is compromised, how big is the blast radius? The average blast radius for a package has also been growing over time

¿Y cuando hay problemas de seguridad? Pues se heredan, claro
Se estima que hasta un 40% de paquetes podrían depender de paquetes vulnerables.

> Just looking at known published vulnerabilities, the authors estimate that up to 40% of all packages rely code known to be vulnerable

No hay que olvidar que uno de los consejos de seguridad que se dan habitualmente es comprobar las dependencias de nuestros productos [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/). Porque ya lo decían en el Top 10 de OWASP en 2013. El A-9 era utilizar componentes con vulnerabilidades conocidas.

> A9-Using Components with Known Vulnerabilities

Hay que estar atentos.
