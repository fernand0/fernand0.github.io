--- 
layout: post
title: "Estructura interna de Git cuando se usan sus instrucciones"
date: "Fri Apr 03 15:02:01 +0100 2020"
category: desarrollo
tags: [desarrollo, git, grafo, interioridades, hash, estructura]
imagefeature: http://live.staticflickr.com/65535/49683684377_e8f77bf436.jpg
---

<a href="https://www.flickr.com/photos/fernand0/49683684377/in/dateposted/" title="Celosías claustro "><img src="http://live.staticflickr.com/65535/49683684377_e8f77bf436.jpg" alt="Celosías claustro " width="240" style="float:left; margin:5px"></a>
Un artículo sobre las interioridades de git [Git from the inside out](https://codewords.recurse.com/issues/two/git-from-the-inside-out).

Describe fundamentalmente la estructura de grafo que subyace la conocida herramienta Git y las consecuencias que esto tienen en como funciona.

> The essay focuses on the graph structure that underpins Git and the way the properties of this graph dictate Git’s behavior.

Para ello se basa en el funcionamiento de distintas instrucciones, y se apoya en ello para comentar estas interioridades.

> The text is structured as a series of Git commands run on a single project. At intervals, there are observations about the graph data structure that Git is built on. These observations illustrate a property of the graph and the behavior that this property produces.

Para conservar.
