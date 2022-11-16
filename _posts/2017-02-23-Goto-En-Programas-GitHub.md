---
layout: post
title: "Estudio sobre el uso del goto en GitHub"
date: "Thu Feb 23 16:10:01 +0100 2017"
category: programación
tags: [programación, desarrollo, goto, estructuras, control, github, demoscopía]
imagefeature: https://c1.staticflickr.com/9/8722/17081552519_f28c31a3fc_m.jpg
---





<a href="https://www.flickr.com/photos/fernand0/2524986421" title="Siga la flecha"><img src="https://c1.staticflickr.com/3/2040/2524986421_b3fed21dc3_m.jpg" width="240"  alt="Siga la flecha" style="float:left; margin:5px"></a>
Parece que GitHub es una fuente inagotable de aprendizaje. Traemos hoy [[PDF] An empirical study of goto in C code from GitHub repositories](https://peerj.com/preprints/826.pdf). En este caso estudian la utilización de esta conocida estructura de control que permite romper el flujo de cualquier programa cuando se cumplen determinadas condiciones (o dejan de cumplirse). 

En general es una estructura de control que está mal vista desde el punto de vista del desarrollo estructurado de programas. Podemos recordar aquí el famoso [[PDF] Edgar Dijkstra: Go To Statement Considered Harmful](http://homepages.cwi.nl/~storm/teaching/reader/Dijkstra68.pdf), de  Edsger Dijkstra, uno de los padres de la programación estructurada. Sin embargo, es cierto que en algunos casos la estructura del programa puede mejorar mucho si se utiliza con 'sabiduría'.

El artículo habla del uso del 'goto' por parte de los programadores (si lo utilizan y para qué) y su aparición en la correción de fallos después de lanzar una versión.

Se usa. A nivel de fichero:

> Considerable use of goto at the file level: We find that 246,657 out of the 2,150,387 files (or 11.47%) examined in our study have at least one goto statement. 

A nivel de proyectos:

> We find that 3,093 out of the 11,627 projects (or 26.60%) have at least one file with a goto statement. We also find that more than half the projects have about 20% of the files that have at least one goto statement.

Se utiliza, fundamentalmente, para código de sistema y de red, pero también para otras cuestiones.
Mirando en las funciones parece que el uso principal es para gestión de errores, limpieza (liberación de memoria, etc.).
Otra característica interesante es que la mayoría de los saltos son hacia adelante y raramente se hacen hacia atrás.

> We find that, in general, the use of goto is actually well disciplined. Most uses of goto statements are reasonably structured, filling the void of miss- ing higher-level constructs found in other languages. There are of course usages that are unstructured as Dijkstra feared, but they are overall in

Después de publicar una versión la tendencia era a que se mantengan más o menos el mismo número de 'gotos' en el código, por lo que los proyectos no parecen considerarlos como algo perjudicial y desaconsejable.

> If we assume bugs in the post-release phase of a project as a measure of harm, then the small number of goto statements being removed/modified in bug fixes implies that goto statements were not consid- ered harmful enough to be removed/modified in the post-release phase of the project in most cases.

Interesante.
