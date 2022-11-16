---
layout: post
title: "El uso de identificadores en protocolos, la seguridad y la privacidad"
date: "Tue May 15 16:02:01 +0100 2018"
category: seguridad
tags: [seguridad, identificadores, aleatoriedad, privacidad]
imagefeature: https://c2.staticflickr.com/8/7602/16880496915_0e7618390c_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/16880496915" title="Números"><img src="https://c2.staticflickr.com/8/7602/16880496915_0e7618390c_m.jpg" width="240"  alt="Números" style="float:left; margin:5px"></a>
Ya hace tiempo que no hablamos de aleatoriedad. En este caso vamos un paso más allá y traemos este 'draft' sobre las consecuencias de tener determinados identificadores en algunos protocolos: [Security and Privacy Implications of Numeric Identifiers Employed in Network Protocols](https://tools.ietf.org/html/draft-gont-predictable-numeric-ids-02). 

La mayoría de los problemas han tenido que ver, tradicionalmente, con la predicibilidad tanto en números de secuencia, como en otros identificadores necesarioes en los protocolos.

En este momento va por la versión tercera y se analizan algunos algoritmos frecuentes de generación de estos identificadores (Sección 8), con los problemas de unicidad, predictibilidad. También las vulnerabilidades frecuentes (Sección 9).

Estos identificadores utilizados en protocolos deberían:

* Estar bien identificadas las cuestiones relacionadas con la interoperabilidad.
* Proporcioncionarse un análisis desde el punto de vista de seguridad y privacidad
* Recomendar algoritmos que mitiguen los problemas indentificados.

Un tema que no siempre se tiene presente y que tiene su importancia.
