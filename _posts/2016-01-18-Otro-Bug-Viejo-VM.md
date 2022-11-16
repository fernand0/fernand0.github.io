---
layout: post
title: "Un fallo viejo en máquinas virtuales"
date: "Mon Jan 18 19:20:01 +0100 2016"
category: seguridad
tags: [seguridad, bugs, fallos, antiguo, viejo, venom, VM]
---




<a href="https://www.flickr.com/photos/fernand0/5610626593" title="Bicho"><img src="https://c2.staticflickr.com/6/5142/5610626593_9c76765c77_m.jpg" width="240"  alt="Bicho" style="float:left; margin:5px"></a>
Los fallos que viven y sobreviven a múltiples actualizaciones y cambios terminarán teniendo su propia categoría por aquí. No hace mucho leíamos [11-year-old VM escape bug opens host machines to compromise](http://www.net-security.org/secworld.php?id=18384) y lo traemos aquí a título de inventario.

> "The VENOM vulnerability has existed since 2004, when the virtual Floppy Disk Controller was first added to the QEMU codebase," the researchers shared. If you're wondering why it is still added to new virtual machines by default, it's because it's still occasionally used in a number of situations.

No hay mucho más que decir.
Siguiendo la moda, el fallo tiene su propia página web: [VENOM](http://venom.crowdstrike.com/).
