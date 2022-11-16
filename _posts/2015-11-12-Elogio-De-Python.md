---
layout: post
title: "Elogio de Python por el equipo de ingeniería de PayPal"
date: "Thu Nov 12 13:10:01 +0100 2015"
category: desarrollo
tags:  [desarrollo, python, mitos, listas, consejos, programación]
---





<a href="https://www.flickr.com/photos/fernand0/4748574677/" title="Portada Libro Python"><img src="https://c1.staticflickr.com/5/4097/4748574677_5c6d3db6cb_m.jpg" width="240"  alt="Portada Libro Python" style="float:left; margin:5px"></a>
Desde hace algún tiempo, cuando tengo que hacer un programita para resolver un problema de manera rápida mi lenguaje elegido es Python. También voy encontrándome mis limitaciones, esencialmente por no dedicarle atención suficiente a todo el entorno que ofrece para trabajar. De hecho, ya algunas entradas sobre [Python](http://fernand0.github.io/tags/python/) en esta bitácora. Principalmente desarrollos que he ido haciendo pequeñitos que tal vez podrían servirle a alguien más alguna vez.

Por eso me gustó leer [10 Myths of Enterprise Python](https://www.paypal-engineering.com/2014/12/10/10-myths-of-enterprise-python/) que es un elogio por parte del equipo de ingeniería de PayPal, tratando de aclarar algunas ideas erróneas sobre el lenguaje. Las listo:

1. Python is a new language
2. Python is not compiled
1. Python is not secure
1. Python is a scripting language
1. Python is weakly-typed
1. Python is slow
1. Python does not scale
1. Python lacks good concurrency support
1. Python programmers are scarce
1. Python is not for big projects

Vale la pena leerlas y echarles un vistazo para ver los argumentos.

Mi relación con Python se basa fundamentalmente en que es rápido para hacer pruebas (con la ventaja del intérprete para terminar de comprender cosas que no tienes muy controladas) y, a la vez, permitiría evolucionar a proyectos más grandes (que con scripts de shell no es trivial). También sus 'batteries included' con bibliotecas disponibles casi para cualquier cosa que podamos querer hacer.

Mis quejas con el lenguaje, que también las hay, tendrían que ver con su incómodo sistema de gestión de codificaciones (quién no se haya enfrentado nunca al problema que nos diga como lo hizo), y la transición a Python 3 que no termina de llegar del todo.

Entre mis carencias, la gestión y pruebas con distintas versiones del lenguaje y el lío que (creo que) tengo montado en mis sistemas con la instalación de bibliotecas de terceros de manera poco adecuada. Estoy empezando a explorar [Virtual Environments](http://docs.python-guide.org/en/latest/dev/virtualenvs/) y [pyenv](https://github.com/yyuu/pyenv) para ver si controlo estas cosas un poco mejor.
