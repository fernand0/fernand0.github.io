---
layout: post
title: "Primeros pasos con Omega2"
date: "Sun Jan 22 16:50:01 +0100 2017"
category: making
tags: [making, omega2, soc, ordenador, pruebas, compras]
imagefeature: https://scontent-mad1-1.cdninstagram.com/t51.2885-15/e35/12976346_479978868864256_1204108015_n.jpg
---





Hace unos meses se anunció el proyecto de financiación de un nuevo ordenadorcito, el [Omega2: $5 Linux Computer with Wi-Fi, Made for IoT](https://www.kickstarter.com/projects/onion/omega2-5-iot-computer-with-wi-fi-powered-by-linux). Tengo que decir que lo vi y no le presté atención, así que no participé en el proyecto. Mi hermano lo hizo y además encargó un par de cacharritos para darme uno.

Lo tengo en casa desde navidad pero hasta ahora no había tenido tiempo de escribir esta nota. En este caso lo probé y pude configurarlo con mucha rapidez. 
Desde el punto de vista de puesta en marcha el proyecto ha trabajado muy bien si nos olvidamos de un par de detalles que comentaremos luego: alimentamos la placa, esperamos a que arranque y crea un punto de acceso WiFi. 
La documentación es clara y se sigue bien.
Desde cualquier otro ordenador podemos conectarnos a ese punto de acceso. Navegando desde esa red podremos conectarnos a la dirección del Omega y hacer la configuración inicial desde el navegador (o mediante ssh). Entre otras cosas le proporcionamos los datos de nuestra red WiFi y entonces se conecta. 
Personalmente me gusta más la configuración inicial del C.H.I.P. pero encuentro esta bastante cómoda y amigable (y mucho más que tener que buscar una pantalla a la que conectar el cacharrito, aunque sea la de la TV).

En cuanto a las pegas inciales dos, pero notables: la alimentación de la placa es a 3.3V (si compramos el 'dock' entonces podremos tener acceso a un puerto USB y alimentar el cacharrito desde allí, entre otras ventajas. Pero entonces hablamos de un ordenador de 20 dólares y no 5). La segunda pega es la separación de los pines: no es la estándar de una placa de prototipado así que no es posible pincharía allí y cablear, hay que poner los cables directamente a los pines (a lo mejor hay placas de prototipado con esa ditancia de pines, lo desconozco). 
La estoy alimentando gracias a que tenía una fuente de alimentación [YwRobot](https://www.sunfounder.com/wiki/index.php?title=How_to_use_YwRobot_Power_Supply_Properly).

<div align="center">
<a href="https://www.instagram.com/p/BO205s2huVt/" title="Omega 2"><img src="https://scontent-mad1-1.cdninstagram.com/t51.2885-15/e35/15877016_109941836177356_5328287142667878400_n.jpg" width="240"  alt="Omega 2" style="float:center"></a>
</div>

Como decíamos arriba la documentación para ponerla en marcha y dar los primeros pasos está muy bien [Onion Omega2 Documentation](https://docs.onion.io/omega2-docs/) y ponerla en marcha es sencillo.

Una vez que conseguimos que arranque disponemos de un sistema funcionando que configuramos a nuestro gusto y podemos empezar a trabajar. 
Como punto positivo frente a otras placas nos ha parecido muy buena idea que genere su propia red y de manera simultánea pueda conectarse al router mediante interfaces virtuales. Así se pueden hacer proyectos (la documentación lo explica) para hacer un extensor de WiFi (llevar la WiFi a algún punto lejano, haciendo de repetidor), un punto de acceso, ... 
Otro punto interesante es que utiliza LinuxWRT, con el inconveniente de tener que aprender a manejar otro gestor de paquetes, el opkg (aunque la documentación ayuda también en este aspecto).

Entramos por ssh:

<div align="center">
<a href="https://www.instagram.com/p/BO3CXNLBAy1/" title="El ssh en Omega 2"><img src="https://scontent-mad1-1.cdninstagram.com/t51.2885-15/e35/15802878_1766875116970729_9193410125954547712_n.jpg" width="240"  alt="El ssh en Omega 2" style="float:center"></a>
</div>

En cuanto al uso, tengo sentimientos enfrentados: es pequeñita, barata y sencilla de poner en marcha. Pero cuando empezamos a trabajar con el modelo básico, casi no podemos hacer nada (por falta de espacio): para empezar, hay que elegir entre tener Git o Python, porque no hay espacio libre suficiente para los dos. 
Podríamos aumentar el almacenamiento disponible (y hay instrucciones para ello) pero sería mejor teniendo un puerto USB para conectarlo.

Entre sus características 

* Procesador 580MHz MIPS CPU.
* Memoria 64MB (el Omega 2+ tiene 128) y 16 Mb de almacenamiento (32 en el caso del Plus).
* b/g/n Wi-Fi
* Varios puertos para conectividad con diversos sistemas externos.

Tiene USB 2.0, pero sin el dock no tendremos el conector.

El tamaño es pequeñito, la mitad de lo que ocupa el C.H.I.P. aproximadamente y un poquito más que un [NodeMCU](http://www.nodemcu.com/).

<div align="center">
<a href="https://www.instagram.com/p/BPk-Pp3BKcb/" title="Comparando tamaños: C.H.I.P., Omega2, NodeMCU, Arduino, Pine64, Raspberry Pi"><img src="https://scontent-mad1-1.cdninstagram.com/t51.2885-15/e35/16123689_1241192719307368_6007765382805323776_n.jpg" width="240"  alt="Comparando tamaños: C.H.I.P., Omega2, NodeMCU, Arduino, Pine64, Raspberry Pi" style="float:center"></a>
</div>

Una cosa que me preocupaba de estos aparatitos son las prestaciones. Son bastante limitadas y he preparado una tabla para que se vea mejor. La comparación se hará con una Raspberry Pi (Model B), un C.H.I.P., una Pine 64 y también he hecho comparaciones con un PC de escritorio viejo (fecha alrededor de 2008), y mi portátil, que también tiene unos cuantos años (fecha alrededor de 2011):

|---------------|-------------------------|-------------|----------|------------------------------------------|
| Dispositivo   | microsegundos/iteración | Nº de cores | bogomips | Procesador                               |
|---------------|-------------------------|-------------|----------|------------------------------------------|
| Raspberry Pi  | 5.944                   | 1           | 697,95   | ARMv6-compatible processor rev 7 (v6l)   |
| Omega 3       | 3.916                   | 1           | 385,84   | MIPS 24KEc V5.5                          |
| C.H.I.P.      | 1.125                   | 1           | 1001,88  |  ARMv7 Processor rev 2 (v7l)             |
| Pine 64       | 624                     | 4           | 624      | AArch64 Processor rev 4 (aarch64)        |
|---------------|-------------------------|-------------|----------|------------------------------------------|
| PC Escritorio | 204                     | 1           | 6800,56  | Intel(R) Pentium(R) 4 CPU 3.40GHz        |
| Portátil      | 69                      | 2           | 5382,47  | Intel(R) Core(TM) i7-2620M CPU @ 2.70GHz |
|---------------|-------------------------|-------------|----------|------------------------------------------|

La conclusión para mi fue que estos cacharritos pueden cumplir un papel en muchos momentos (y lo cumplen) pero no debemos olvidar las limitaciones en cuanto a potencia, que no permitirían (aún) pensar en ellos como sustitutos de un computador de sobremesa (salvo que tengamos requisitos muy austeros).

El sistema utilizado para medir las 'prestaciones' es muy básico, utilicé el código que proporcionaban en [Performance Comparison - C++ / Java / Python / Ruby/ Jython / JRuby / Groovy](http://blog.dhananjaynene.com/2008/07/performance-comparison-c-java-python-ruby-jython-jruby-groovy/). 

En esta serie hemos publicado hasta ahora:

* [Primeros pasos con Pine64](http://fernand0.github.io/making/2016/07/18/Primeros-Pasos-Con-Pine.html)
* [Primeros pasos con el C.H.I.P.](http://fernand0.github.io/making/2016/07/11/Primeros-Pasos-Con-Chip.html)

Sobre la Raspberry no hice un primeros pasos. 
