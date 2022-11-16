---
layout: post
title: "Identificación de programadores mediante su código"
date: "Mon Mar 6 14:10:01 +0100 2017"
category: programación
tags: [programación, desarrollo, identificación, estructuras, desarrolladores, github, demoscopía]
imagefeature: https://scontent.cdninstagram.com/t51.2885-15/e35/16906212_1091622597633834_3812352828949659648_n.jpg
---





<a href="https://www.instagram.com/p/BQw3uZogQek/" title="Iguales pero diferentes"><img src="https://scontent.cdninstagram.com/t51.2885-15/e35/16906212_1091622597633834_3812352828949659648_n.jpg" width="240"  alt="Iguales pero diferentes" style="float:left; margin:5px"></a>
Seguimos con artículos de investigación que nos han llamado la atención. ¿Existe el estilo de programación? ¿Podemos identificar a alguien que desarrolla programas por su código? Parece que no sólo es cierto (siempre que tengamos código para comparar, claro) sino que también sería cierto con los binarios que se generan por el compilador a partir de ese código. Al menos, eso es lo que dicen en [When Coding Style Survives Compilation: De-anonymizing Programmers from Executable Binaries](https://arxiv.org/abs/1512.08546).
La preocupación de los autores se refiere a la privacidad y anonimato de los desarrolladores.

Del resumen, descompilando el código binario observan como algunas particularidades sintácticas se conservan y pueden obtenerse de nuevo: 

> We examine executable binary authorship attribution from the standpoint of machine learning, using a novel set of features that include ones obtained by decompiling the executable binary to source code. We show that many syntactical features present in source code do in fact survive compilation and can be recovered from decompiled executable binary.

La capacidad de atribución alcanzó un 92% de los 100 desarrolladores de una Google Code Jam:

> We demonstrate this improvement on data from the Google Code Jam, obtaining attribution accuracy of up to 92% with 100 candidate programmers

Y parece robusta frente a intentos de ofuscación, intervenciones más agresivas del compilador, ...

Muy interesante.
