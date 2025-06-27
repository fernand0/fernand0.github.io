---
layout: post
title: "En contra del /tmp"
date: "2025-06-27 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- tmp
- historia
- programación
- Unix
imagefeature: "https://live.staticflickr.com/131/320354477_5e3cd0213f_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/320354477/in/photolist-4dC1PZ-4EFC4t-uiUe4-uiUr8-uiUCo-7HwerZ-2pgrgFp" title="El caracol de Juan"><img src="https://live.staticflickr.com/131/320354477_5e3cd0213f_z.jpg" width="640" height="480" alt="El caracol de Juan"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Es sabido que los sistemas de tipo Unix tienen un directorio común (pero un poco especial) que permite a cualquiera escribir para almacenar información de trabajo, ficheros temporales, ...

En [against /tmp](https://dotat.at/@/2024-10-22-tmp.html) comentan sobre el tema. Empiezan hablando de las peculiaridades, como es el *sticky bit* (¿pegajoso?) que es un permiso especial *01000* que se representa con una 't':

    drwxrwxrwt  5 root  wheel  160 Oct 22 10:22 /tmp/

Se inventó en los 70 para indicar que determinados programas debían permanecer en el núcleo porque eran de uso frecuente y así todo iba más fluido.

> Originally in the 1970s the sticky bit was invented to speed up frequently-used programs such as the shell: the sticky bit indicated to the kernel that the executable file should stick in core. This functionality was made obsolete in the 1980s by filesystem page caches.

El bit se utilizó para los directorios con un objetivo diferente, impidiendo el borrado de ficheros aunque estuvieran en un directorio en el que tuviéramos permiso para borrar (el sistema de permisos de Unix siempre ha sido un poco básico).

> To fix this, a file in a sticky directory may only be removed or renamed by a user if the user has write permission for the directory and the user is the owner of the file, the owner of the directory, or the super-user.

Esto es, el fichero en un directorio con el sticky bit solo puede borrarlo el propietario (o el propietario del directorio, o el administrador, claro).

Luego discute sobre las diferentes formas de crear un fichero temporal en Unix, con hasta cinco versiones diferentes:

> bad: mktemp, tempnam, tmpnam
> ok: mkstemp, tmpfile
> new: mkdtemp, mkostemp, mkstemp

Tanto `mkstemp` como `tmpfile` están pensadas para crear ficheros (o directorios temporales) que no puedan colisionar con la actividad de otros programas.

> The purpose of all these functions is to create a temporary file (or directory) that doesn’t collide with other concurrent activity.

El objetivo es evitar, fundamentalmente, condiciones de carrera (alguien consigue que abramos un fichero sobre el que tiene el control); para ello, hay que creaa nombres difíciles de predecir, con las restricciones adecudadas `O_CREAT | O_EXCL`, y hacer reintentos si el fichero ya existe `EEXIST`, para evitar (también) la denegación de servicio.

Luego discute sobre la limpieza (borrar lo que ya no se necesita) porque el `/tmp` tiene tendencia acumular basura y los problemas que puede tener alguien que intenta mantener ese directorio con los borrados.

Lo que debería suceder, afirma, es que debería haber directorios temporales diferenciados para cada usuario.

> If you have per-user $TMPDIR then temporary filenames can safely be created using the simple mechanisms described in the mktemp(1) rationale or used by the old deprecated C functions. There’s no need to defend against an attacker who doesn’t have sufficient access to mount an attack! There’s no need for sticky directories because there aren’t any world-writable directories.

Y la razón de que eso no se hiciera tiene que ver (otra vez) con las prestaciones y los límites de los usuarios: podía ocurrir que el espacio del usuario estuviera montado a través de la red (lentitud), tuvier limitaciones de espacio (cuotas), o en un sistema de ficheros que no permitiera algunas características necesarias (como las *named pipes*).

Interesante. Un poco de historia, un poco de seguridad,...


