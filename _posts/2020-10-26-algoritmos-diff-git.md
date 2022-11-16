--- 
layout: post
title: "Algoritmos de diferencias y git"
date: "Mon Oct 26 15:02:01 +0100 2020"
category: desarrollo
tags: [desarrollo, git, diferencias, diff]
imagefeature: http://live.staticflickr.com/8394/10208926684_df47fdd2c0.jpg
---

<a href="https://www.flickr.com/photos/fernand0/10208926684/" title="2013-10-11-facebook "><img src="http://live.staticflickr.com/8394/10208926684_df47fdd2c0.jpg" alt="2013-10-11-facebook " width="240" style="float:left; margin:5px"></a>
Los sistemas de control de versiones se basan en poder calcular de manera eficiente la diferencia entre dos ficheros. En [How different are different diff algorithms in Git?](https://link.springer.com/article/10.1007/s10664-019-09772-z) hablan justamente de eso.

Identifican tres casos de uso de estas diferencias y comparan sus prestanciones.

> From our systematic mapping, we identified three popular applications of diff in recent studies.

Fundamentalmente: recolección de métricas, identificar la introducción de fallos (*bugs*) y obtener parches (*patches*). Con dos algoritmos, Myers e Histogram.

> In our empirical analyses, we conduct three comparisons based on the most popular usages of git diff found in our mapping study: collecting metrics, identifying bug introduction, and getting patches. We investigate the disagreement between two diff algorithms: Myers and Histogram, and take a manual measurement of their quality in generating the diff lists. 

Lectura interesante.

