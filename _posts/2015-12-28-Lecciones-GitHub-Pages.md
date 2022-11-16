---
layout: post
title: "Lecciones aprendidas desarrollando GitHub pages"
date: "Mon Dec 28 23:35:01 +0100 2015"
category: desarrollo
tags: [desarrollo, GitHub, pages, comunidad, clientes, usuarios, proyectos]
---




<a href="https://cloud.githubusercontent.com/assets/282759/7324890/574b3fa6-ea88-11e4-9d3a-2cd599e0b7f9.png" title="Crecimiento GitHub Pages"><img src="https://cloud.githubusercontent.com/assets/282759/7324890/574b3fa6-ea88-11e4-9d3a-2cd599e0b7f9.png" width="240"  alt="Crecimiento GitHub Pages" style="float:left; margin:5px"></a>
Recientemente se ha cumplido un año que estamos escribiendo en este sitio [Cuata Etapa](http://fernand0.github.io/Cuarta-Etapa/).
Me viene bien recordarlo porque recientemente leíamos [Eight lessons learned hacking on GitHub Pages for six months](https://github.com/blog/1992-eight-lessons-learned-hacking-on-github-pages-for-six-months) en el que nos cuentan algunos principios generales aprendidos desarrollando el servicio. 

El primero de ellos (previo, más bien) es ser usuario de tu propio servicio para conocerlo bien, conocer sus virtudes, encontrar sus defectos...

Y luego la lista:

* Test, test, and then test again

Desarrollo basado en pruebas, para estar seguros de que cuando se introducen cambios nada va a fallar.

* Use public APIs, and when they don't exist, build them

En la línea del principio 'previo' no utilizar componentes secretos o privados y si se detecta la necesidad de algo que no existe, ponerlo a disposición de los usuarios.

* Let the user make the breaking change

Permitir a los usuarios que controlen los cambios importantes que pueden afectar a sus sitios.

* In every communication, provide an out

Cuando se comunican los errores se informa al usuario no sólo del problema sino también de dónde tiene que mirar para solucionar el fallo.

* Optimize for your ideal use case, not the most common

No hay que olvidar que el servicio es para dar a conocer los proyectos. Eso debería ser lo más fácil de hacer, independientemente de lo que la gente esté haciendo.

* Successful efforts are cross-team efforts

Como tantos proyectos, no son cosa sólo de un equipo que se encarga de ellos, sino que, seguramente, hará falta hablar y trabajar con otros equipos.

* Match user expectations, then exceed them

Que los usuarios tengan lo que esperaban del proyecto, pero mejor. No hay mucho que añadir aquí.

* It makes business sense to support open source

Una parte de su producto está basado en Jekyll, que es software libre y que ha ganado su propio espacio como producto independiente, que siguen apoyando y en el que siguen participando.
