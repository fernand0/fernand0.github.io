---
layout: post
title: "Sistemas masivos de ficheros y control de versiones"
date: "Mon Feb 05 15:10:01 +0100 2018"
category: sistemas
tags: [gvfs, git, virtual, filesystem, sistema, ficheros, versiones]
imagefeature: https://assets-cdn.github.com/images/modules/logos_page/Octocat.png
---


<a href="https://github.com/logos" title="GitHub logo"><img src="https://assets-cdn.github.com/images/modules/logos_page/Octocat.png" width="240"  alt="GitHub logo" style="float:left; margin:5px"></a>
Cuando uno conoce los sistemas de control de versiones empieza a pensar en casos de uso y la tentación es utilizarlos para todo (¿por ejemplo tener un blog? Ja). No digo que sea el caso, pero me pareció interesante el anuncio [ Announcing GVFS (Git Virtual File System)](https://blogs.msdn.microsoft.com/devops/2017/02/03/announcing-gvfs-git-virtual-file-system/) que nació del paso de Microsoft a utilizar Git como sistema de control de versiones y las dificultades que suponía eso cuando el tamaño del código que manejan es suficientemente grande:

> For example, the Windows codebase has over 3.5 million files and is over 270 GB in size. The Git client was never designed to work with repos with that many files or that much content. You can see that in action when you run “git checkout” and it takes up to 3 hours, or even a simple “git status” takes almost 10 minutes to run. That’s assuming you can get past the “git clone”, which takes 12+ hours.

El código de Windows tiene 3.5 millones de ficheros y ocupa más de 270 GB. Tenemos la tendencia a imaginar que hoy en día la informática puede gestionar casi cualquier cosa, pero la realidad es dura. Buscando la escalabilidad se inventaron el sistema de ficheros virtual basdado en Git (GVFS ,Git Virtual File System) que trata de ofrecer una vista transparente de toda esa información sin necesidad de tenerla descargada.
De paso nos enteramos de algunas cifras que no siempre están claras para el sistema operativo de Microsoft.

Lo dejaron libre en [GVFS](https://github.com/Microsoft/gvfs) y hay más comentarios interesantes en [Scaling Git (and some back story)](https://blogs.msdn.microsoft.com/bharry/2017/02/03/scaling-git-and-some-back-story/).

Las noticias más recientes hablan incluso de [Microsoft and GitHub team up to take Git virtual file system to macOS, Linux](https://arstechnica.com/gadgets/2017/11/microsoft-and-github-team-up-to-take-git-virtual-file-system-to-macos-linux/) que sería una buena noticia para todos. Aunque no parece haber muchas noticias nuevas sobre el tema.
