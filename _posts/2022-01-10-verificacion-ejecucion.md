---
layout: post
title: "Sobre la verificación en tiempo de ejecución del kernel de Linux"
date: "2022-01-10 15:00:00 +0000"
category: verificación
tags:
- verificación
- linux
- kernel
- trazas
imagefeature: 'https://live.staticflickr.com/1482/25670959150_c33d8462f1.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/25670959150/" title="Vigilantes "><img src="https://live.staticflickr.com/1482/25670959150_c33d8462f1.jpg" alt="Vigilantes " width="240" style="float:left; margin:5px"></a>
En [[RFC PATCH 00/16] The Runtime Verification (RV) interface](https://lore.kernel.org/lkml/cover.1621414942.git.bristot@redhat.com/) un texto sobre la interfaz de verificación en tiempo de ejecución del Kernel de Linux.

Se trata de un método ligero que complementa las técnicas tradicionales de verificación exhaustiva mediante el análisis de la traza de la ejecución del sistema.

> Runtime Verification (RV) is a lightweight (yet rigorous) method that complements classical exhaustive verification techniques (such as model checking and theorem proving) with a more practical approach for complex systems.

> Instead of relying on a fine-grained model of a system (e.g., a re-implementation a instruction level), RV works by analyzing the trace of the system's actual execution, comparing it against a formal specification of the system behavior.

Existe un documento de referencia, que es:

> DE OLIVEIRA, Daniel Bristot; CUCINOTTA, Tommaso; DE OLIVEIRA, Rômulo Silva.  *Efficient formal verification for the Linux kernel.* In: International Conference on Software Engineering and Formal Methods. Springer, Cham, 2019.  p. 315-332.

En el RFC se presenta un sistema basado en monitores que ayudan a observar el uso y cómo se genera código automáticamente. Esto ha venido motivado por el uso de Linux en sistemas críticos.

> In this RFC I am still not proposing any complex model. Instead, I am presenting only simple monitors that help to illustrate the usage of the automatic code generation and the RV interface. This is important to enable other researchers and developers to start using/extending this method.

> It is also worth mentioning that this work has been heavily motivated by the usage of Linux on safety critical systems, mainly by the people involved in the Elisa Project. 
