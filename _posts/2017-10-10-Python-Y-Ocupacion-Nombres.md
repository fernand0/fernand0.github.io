---
layout: post
title: "Los nombres y la seguridad. El caso de Python y PyPI"
date: "Tue Oct 10 16:14:01 +0100 2017"
category: seguridad
tags: [seguridad, python, PyPI, nombres, ocupación]
imagefeature: https://c1.staticflickr.com/5/4097/4748574677_5c6d3db6cb_m.jpg
---




<a href="https://www.flickr.com/photos/fernand0/4748574677" title="Libro sobre Python"><img src="https://c1.staticflickr.com/5/4097/4748574677_5c6d3db6cb_m.jpg" width="240"  alt="Libro sobre Python" style="float:left; margin:5px"></a>
Cada vez pasa menos tiempo desde que alguien describe un problema de seguridad hasta que alguien lo aplica de manera (más o menos) efectiva. Hace algún tiempo podíamos leer [Typosquatting programming language package managers](http://incolumitas.com/2016/06/08/typosquatting-package-managers/) donde se hablaba de la posibilidad de utilizar los errores de tecleo de los usuarios para suplantar algunos paquetes bien conocidos de sitio [PyPi](https://pypi.python.org/pypi), que es un repositorio público para alojar paquetes desarrollados en Python que luego pueden instalarse de forma muy sencilla.

En este caso el experimento consistió en crear 200 paquetes y subirlos al repositorio:

> All in all, I created over 200 such packages and equipped them with a small program and uploaded them over the course of several months. The idea is to add some code to the packages that is executed whenever the package is downloaded with the installing user rights.

Estos paquetes contenían un cierto código que 'llamaba a casa' e informaba de su instalación.

El resultado fue interesante puesto que 17289 computadores instalaron estos programas:

> In two empirical phases, exactly 45334 HTTP requests by 17289 unique hosts (distinct IP addresses) were gathered. This means that 17289 distinct hosts executed the program above and sent the data to the webserver which was analyzed in the thesis.

No sólo eso, sino que al menos 43.6% de esas IPs ejecutaron el programa de notificación con privilegios de administrador:

> At least 43.6% of the 17289 unique IP addresses executed the notification program with administrative rights. From the 19603 distinct interactions, 8614 machines used Linux as an operation system, 6174 used Windows and 4758 computers were running OS X. Only 57 hosts (or 0.29%) could not be mapped to one of these three major operating systems.

Cuando lo estuve leyendo me pareció un trabajo muy interesante y supuse que los administradores de PyPI lo tendrían en cuenta y tomarían algún tipo de medida.

La sorpresa ha sido ver que no sólo no se han tomado medidas, sino que parece haber habido un ataque real: [Ten Malicious Libraries Found on PyPI - Python Package Index](https://www.bleepingcomputer.com/news/security/ten-malicious-libraries-found-on-pypi-python-package-index/). Se trataba de utilizar nombres similares e incluir código malicioso en ellos:

> NBU experts say attackers used a technique known as typosquatting to upload Python libraries with names similar to legitimate packages — e.g.: "urlib" instead of "urllib."

Se puede leer el aviso 'oficial' en [http://www.nbu.gov.sk/skcsirt-sa-20170909-pypi/index.html](skcsirt-sa-20170909-pypi). 
Allí también recuerdan la forma de detectar si hemos instalado alguno de estos paquetes:

```bash
pip list --format=legacy | egrep '^(acqusition|apidev-coop|bzip|crypt|django-server|pwd|setup-tools|telnet|urlib3|urllib) '
```

Y luego podríamos utilzar el `pip uninstall <paquete>` si es que tenemos alguno de esos.
