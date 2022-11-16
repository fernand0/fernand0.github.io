---
layout: post
title: "Cadenas de formato en Windows"
date: "Mon Oct 1 16:02:01 +0100 2018"
category: seguridad
tags: [seguridad, vulnerabilidades, cadenas, formato, c, windows]
imagefeature: https://c1.staticflickr.com/9/8242/8647192601_77d9b533f8_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/8647192601" title="Ventanas"><img src="https://c1.staticflickr.com/9/8242/8647192601_77d9b533f8_m.jpg" width="240"  alt="Ventanas" style="float:left; margin:5px"></a>
En el apartado de problemas de seguridad no tan conocidos pero que tienen su interés están los fallos relacionados con las cadenas de formato. En C, cuando en una instrucción de escritura *printf* y similares no se pone cadena de formato, puede ocurrir que la entrada proporcionada por el usuario termine interpretándose como tal. Si a eso añadimos la característica (no tan conocida) de que algunos formatos no son sólo de salida sino que permiten leer y escribir, y además también podemos suministrarle las direcciones para hacerlo, tenemos abierta la puerta al desastre.

En [Exploiting Format Strings in Windows](https://osandamalith.com/2018/02/01/exploiting-format-strings-in-windows/) nos hablaban justamente de este tema, en Windows. 

Para las personas a las que les gusta tocar y jugar con los fallos.
