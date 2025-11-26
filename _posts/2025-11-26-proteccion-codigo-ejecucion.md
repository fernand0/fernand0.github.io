---
layout: post
title: "Protección de ataques en el hardware: más allá de la aleatorización"
date: "2025-11-26 14:00:00 +0000"
category: seguridad
tags:
- aleatorización
- ASLR
- espacio
- direcciones
imagefeature: "https://live.staticflickr.com/5300/5437829779_a7162c6a69_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/5437829779/" title="Informática dulce en @lajamoneria"><img src="https://live.staticflickr.com/5300/5437829779_a7162c6a69_z.jpg" width="640" height="480" alt="Informática dulce en @lajamoneria"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Una técnica habitual para evitar ataques por desbordamiento de memoria y otros es la aleatorización del espacio de direcciones: si los datos no están almacenados siempre de la misma manera (que es lo que se haría sin aleatorización, más o menos) son más difíciles de encontrar, analizar y, en definitiva, atacar.

En [To keep hardware safe, cut out the code’s clues](https://news.mit.edu/2025/to-keep-hardware-safe-cut-out-codes-clues-0211) hablan de un método para eliminar información sobre el código en ejecución para evitar que los 'malos' puedan utilizar algunos de sus trucos.

Para mejorar la aleatorización en el MIT han prensado una forma de ponerlo más difícil: se trata de eliminar partes aleatorias de las direcciones que llevan a las instrucciones del programa antes de ejecutarse, de forma que serán más difíciles de encontrar por un atacante.

> Their “Oreo” method mitigates hardware attacks by removing randomized bits of addresses that lead to a program’s instructions before they’re translated to a physical location. It scrubs away traces of where code gadgets (or short sequences of instructions for specific tasks) are located before hackers can find them, efficiently enhancing security for operating systems like Linux.

Se trata de añadir lo que llaman un 'espacio enmascarado' entre el espacio de direcciones virtuales y el espacio de direcciones físicas.

> Oreo has three layers, much like its tasty namesake. Between the virtual address space (which is used to reference program instructions) and the physical address space (where the code is located), Oreo adds a new “masked address space.”

Esto reconfigura el espacio de direcciones en tiempo de ejecución antes de ejecutarse, haciendo más difícil conocer las localizaciones originales a través de ataques de hardware.

> This re-maps code from randomized virtual addresses to fixed locations before it is executed within the hardware, making it difficult for hackers to trace the program’s original locations in the virtual address space through hardware attacks.

Una preocupación que podríamos tener es que todo vaya más lento por estos cambios, pero nos dicen que eso no es un problema.

> While Oreo adds an extra step to program execution by scrubbing away revealing bits of data, it doesn’t slow down applications.

Siguen siendo posible otros ataques, como la ejecución especulativa, así que no se puede utilizar este método en solitario.

> To defend against speculative execution attacks, the team emphasizes that Oreo needs to be coupled with other security mechanisms (such as Spectre mitigations).

