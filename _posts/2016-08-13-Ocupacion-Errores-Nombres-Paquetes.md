---
layout: post
title: "Ataques por ocupación de nombres de paquetes en diversos lenguajes"
date: "Sat Aug 13 10:25:01 +0100 2016"
category: seguridad
imagefeature: https://c1.staticflickr.com/3/2348/2137644411_23bae9346f_m.jpg
tags: python, Node.js, ruby, typosquatting, ocupación, nombres, paquetes, módulos, ataques, programación, desarrollo
---



<a href="https://www.flickr.com/photos/fernand0/2137644411" title="Paquete"><img src="https://c1.staticflickr.com/3/2348/2137644411_23bae9346f_m.jpg" width="240"  alt="Paquete" style="float:left; margin:5px"></a>
Queremos que todo sea fácil: descubrir algo, instalarlo, que se ejecute sin problemas y pasar a pensar en otra cosa.
Basándose en la idea del *typosquatting* basado en DNS (esto es, cuando tecleamos de manera incorrecta el nombre de un sitio web), Nikolai Philipp Tschacher pensó en explorar la posibilidad de hacer algo parecido con los repositorios de código de diversos lenguajes: se crean paquetes con nombres parecidos a los de algunos de uso frecuente y se monitoriza el número de instalaciones de los mismos.

Lo cuenta en [Typosquatting programming language package managers](http://incolumitas.com/2016/06/08/typosquatting-package-managers/) y desde allí se puede acceder a un documento completo en pdf.

Los resultados son interesantes: más de 17.000 máquinas instalaron esos paquetes y ejecutaron el código, siendo alrededor de la mitad las instalaciones realizaddas con permisos de administrador.

> As a sample data set I will make use of my workout progress data between May 2016 and August 2016.

> - 17000 computers were forced to execute arbitrary code by typosquatting programming language packages/libraries
> - 50% of these installations were conducted with administrative rights
> - Even highly security aware institutions (.gov and .mil hosts) fell victim to this attack
> - a typosquatting attack becomes wormable by mining the command history data of hosts
> - some good defenses against typosquatting package managers might look like

Es cierto que los investigadores de seguridad se dieron cuenta con cierta rápidez de que estaba ocurriendo el problema (unos días). El experimento se realizó entre noviembre de 2015 y enero de 2016, subiendo un cierto número de paquetes de los que más de la mitad se había generado el nombre de manera aleatoria. Los lenguajes elegidos para el ataque fueron Python, Node.js (recuerden el incidente con aquél paquete ...) y Ruby, aunque otros podrían tener problemas similares con los repositorios análogos (con GitHub y otros alojamientos podrían pensarse ataques similares, si alguien se toma la molestia).

Dice el autor que los requisitos para que un ataque así funcione se basa en:

* Posibilidad de registrar cualquier nombre de paquete y subir código sin supervisión.
* Posilibidad de conseguir ejecución de código con el paquete descargado.
* Accesibilidad y disponibilidad de buena documentación para subir y distribuir paquetes en los repositorios.
* Dificultad para aprender rápidamente el lenguaje objetivo.

Por supuesto, la ejecución del código no es imprescindible si pensamos en paquetes de infraestrcutura, bibliotecas y módulos, etc., que terminarán siendo ejecutadas por los programas que las invocan.

Entre las contramedidas, habría que evaluar la prohibición de determinados nombres (en particular, paquetes importantes cuyo nombre cambió con el tiempo y paquetes del *core*), reducir el número de caracteres disponibles para el nombre de los paquetes, añadir espacios de nombres y, claro, hacer las cosas más difíciles evitando la ejecución directa de código en la ejecución.

También se puede utilizar lo aprendido en los gestores de paquetes de código (por ejemplo, los de algunas distribuciones de Linux), así como analizar los errores que comenten los usuarios para tratar de poner las contramedidas adecuadas.

En el apartado de anécdotas y sucesos, parece que poca gente prestó atención al experimento aunque se lanzaban los avisos adecuados aunque sí que hubo alguien que lanzó un contra-ataque tratando de explotar alguna vulnerabilidad mediante inyección de SQL.
También había usuarios (IPs) que realizaban instalaciones repetidas, invistiendo en el error.

