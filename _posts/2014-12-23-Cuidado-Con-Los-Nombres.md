---
layout: post
title: "Cuidado con la gestión de nombres"
date: "Wed Dec 23 23:45:01 +0100 2014"
category: seguridad
tags: seguridad confianza seguridad nombres   
---


Dar un curso de desarrollo seguro (y de seguridad en general) es bastante 'agradecido' desde el punto de vista de encontrar ejemplos, porque la actualidad siempre nos trae sorpresas.

Estábamos hablando en clase sobre los problemas de los nombres y de tomar decisiones sobre ellos y justo aparece el fallo en git: [Vulnerability announced: update your Git clients](https://github.com/blog/1938-vulnerability-announced-update-your-git-clients) 

>The vulnerability concerns Git and Git-compatible clients that access Git repositories in a **case-insensitive or case-normalizing filesystem**. An attacker can craft a malicious Git tree that will cause Git to overwrite its own .git/config file when cloning or checking out a repository, leading to arbitrary command execution in the client machine. Git clients running on OS X (HFS+) or any version of Microsoft Windows (NTFS, FAT) are exploitable through this vulnerability. Linux clients are not affected if they run in a case-sensitive filesystem. 

La negrita la he puesto yo.

Se puede leer también el anuncio en la lista de desarrollo de git, [[ANNOUNCE] Git v2.2.1 (and updates to older maintenance tracks)](http://article.gmane.org/gmane.linux.kernel/1853266) y [Git 1.8.5.6, 1.9.5, 2.0.5, 2.1.4 and 2.2.1 and thanking friends in Mercurial land](http://git-blame.blogspot.com.es/2014/12/git-1856-195-205-214-and-221-and.html).

Si nos interesa ver el código, al menos a una parte, podemos echarle un vistazo a [path: add is_ntfs_dotgit() helper](https://github.com/git/git/commit/1d1d69bc52dcc7def5b2edbd165cc0a4e3911c8e#diff-c36199ef0fc86df61570de73eb0fde65), donde hablan de:  

>On NTFS (and FAT32), there exist so-called "short names" for backwards-compatibility: 8.3 compliant names that refer to the same files as their long names. As ".git" is not an 8.3 compliant name, a short name is generated automatically, typically "git~1" 

Y también a: [read-cache: optionally disallow HFS+ .git variants](https://github.com/git/git/commit/a42643aa8d88a2278acad2da6bc702e426476e9b#diff-e3525ca4a1a338ed0115251c17b21abe) donde se ven las invocaciones a la función añadida y alguna cosa más.

Esta entrada se ha publicado orginalmente en [Cuidado con la gestión de nombres](http://ra-amon.cps.unizar.es/blog/Asignaturas/seguridad/20141223.html).
