---
layout: post
title: "Recuperar información sobre un binario en ejecución (bash)"
date: "2021-09-06 15:00:00 +0000"
category: hacking
tags:
- binario
- ejecución
- historia
- gdb
- procesos
imagefeature: 'http://live.staticflickr.com/7888/46487127005_0460d48e17.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/46487127005/" title="Conchas "><img src="https://live.staticflickr.com/7888/46487127005_0460d48e17.jpg" alt="Conchas " width="240" style="float:left; margin:5px"></a>
En [What am I running inside my bash?](https://www.thanassis.space/bashheimer.html) una entrada bastante técnica (con código y todo) sobre la accidentada recuperación de una línea que el autor escribió en su línea de órdenes hace unos meses.

> I desperately needed to extract the complete (and very lengthy) command line I had written 6 months ago in a bash shell - which was still running under screen. Read on to see how I eventually made it... 

Se trata, ni más ni menos de recuperar una línea de código ejecutada en una instancia que sigue en ejecución:

> You download the bash source code, untar, and hoping you can somehow recover the history information kept inside the running instance of bash, ...

Lanzamos el gdb para que se asocie al proceso en cuestión y podemos empezar a buscar.

> Spawn GDB - and activate God mode! That is, attach to the running bash, and call write_history on our own - it conveniently takes the filename to save in as an argument!

La cosa se complica un poco más porque en la máquina remota había algunas actualizaciones posteriores (el binario ya no era el mismo).

Curioso.
