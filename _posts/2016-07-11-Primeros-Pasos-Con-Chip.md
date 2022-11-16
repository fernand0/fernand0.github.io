---
layout: post
title: "Primeros pasos con el C.H.I.P."
date: "Mon Jul 11 16:30:01 +0100 2016"
category: making
imagefeature: https://scontent.cdninstagram.com/t51.2885-15/e35/13597694_308352186166055_1513547827_n.jpg
tags: [making, C.H.I.P., soc, ordenador, pruebas, compras]
---





<a href="https://www.instagram.com/p/BHjol17hGVx/" title="C.H.I.P."><img src="https://scontent.cdninstagram.com/t51.2885-15/e35/13597694_308352186166055_1513547827_n.jpg" width="240"  alt="C.H.I.P." style="float:left; margin:5px"></a>
Durante el último año he apoyado algunos proyectos en Kickstarter. Por ser más concreto, el [MeARm](https://www.kickstarter.com/projects/phenoptix/mearm-pocket-sized-industrial-robotics-for-everybo) que lo tengo en dique seco, [PiJuice](https://www.kickstarter.com/projects/pijuice/pijuice-a-portable-project-platform-for-every-rasp) que sigue sufriendo retrasos, [Pine64](https://www.kickstarter.com/projects/pine64/pine-a64-first-15-64-bit-single-board-super-comput), que llegó hace algunas semanas pero todavía no he podido ponerlo a funcionar (comentaré, supongo, sobre ello más adelante). Además compré un par de [C.H.I.P.](https://getchip.com/) que no era en Kickstarter pero si ha seguido el modelo de compra anticipada y ya lo recibirás.
Entre los inconvenientes de este modelo de compra es que el momento en que decides apostar por un proyecto no tiene nada que ver con el momento en el que recibes el resultado.

El C.H.I.P. llegó la semana pasada y me encanta: buena [documentación](http://docs.getchip.com/chip.html), todo bien pensado para trabajar rápido y unas prestaciones adecuadas (que nadie espere supercomputación, claro).

Frente a otras placas y sistemas que nos hacen esforzarnos un poco al principio, este aparatito de 9 dólares está muy bien pensado: lo conectamos a nuestro ordenador, arranca y abre un puerto serie a través del que podemos empezar a trabajar (para los que lo prefieran, también se puede conectar a una pantalla o a la televisión para configurarlo):

> If everything went OK, you can now power up your CHIP again and connect via serial as a USB gadget:

```bash
  screen /dev/ttyACM0 115200
```

Ya imagino que esto puede ser un freno para muchos así que tranquilos, que también se puede usar con la tele o con una pantalla y usar el ratón:

<div align="center">
<a href="https://www.instagram.com/p/BHosUwahC0X/" title="C.H.I.P. on TV"><img src="https://scontent.cdninstagram.com/t51.2885-15/e35/13597543_1770971849782604_173704173_n.jpg" width="240"  alt="C.H.I.P. on TV" style="float:center"></a>
</div>

Y desde allí configurar la red (sin más cables que un USB), el ssh, el usuario de trabajo y ponerse a funcionar la próxima vez que arranque. También tiene (por si fuera necesario) un gestor de conexiones basado en texto (nmcli) y sólo si queremos redes más complicadas (de tipo empresarial) necesitaremos trabajar un poco más. Aunque gracias a eso he 'descubierto' las ventajas de copiar y pegar las configuraciones entre sistemas (con cuidado) e incluso se me ha ocurrido un posible proyecto: [Sharing WiFi configuration files over diffferent computers](http://askubuntu.com/questions/796972/sharing-wifi-configuration-files-over-diffferent-computers). También que, aparentemente, es un tema que ya está bien resuelto en Windows 10 y en Mac OS. Tenemos que espabilar.  

El escritorio:

<div align="center">
<a href="https://www.instagram.com/p/BHosfjSBN9e/" title="C.H.I.P. Desktop"><img src="https://scontent.cdninstagram.com/t51.2885-15/e35/13584130_1750517428559546_1192437614_n.jpg" width="240"  alt="C.H.I.P. Desktop" style="float:center"></a>
</div>


No he tenido tiempo de mucho más (instalar el Python, el [pyenv](https://github.com/yyuu/pyenv-installer) y fantasear sobre hacer algunas pruebas con el MeArm (ahora sí).

En el apartado negativo: C.H.I.P. es un mal nombre. Buscar en internet algo que se llama chip es perder el tiempo y la paciencia (no ayuda tampoco, claro, que es un proyecto relativamente nuevo y con poca difusión). Otra pequeña pega es que cuando añades un disco USB no lo monta automáticamente (con el esritorio sí, pero no quiero usarlo con una pantalla).

Entre sus características (copiadas y traducidas de [The PocketC.H.I.P. Is the Handheld Linux Machine I've Been Looking For)[http://lifehacker.com/the-pocketc-h-i-p-is-the-handheld-linux-machine-ive-be-1783247338])

* Procesador Cortex A8 R8 a 1Ghz con una GPU Mail-400
* 512 Mb de RAM
* 4 Gb de memoria flash
* Wifi 802.11 b/g/n  y Bluetooth 4.0
* Salida de vídeo con conector de 3.5mm para vídeo compuesto y audio.
* Puerto USB y puerto micro USB OTG (se usa para alimentación)

Interesante
