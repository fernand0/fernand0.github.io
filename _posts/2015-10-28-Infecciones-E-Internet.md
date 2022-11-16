---
layout: post
title: "Infecciones e internet"
date: "Thu Oct 28 13:50:01 +0100 2015"
category: seguridad
tags:  [seguridad, botnets, desconexión, internet, troyanos, malware, isp, usuarios]
---





<a href="https://instagram.com/p/7rune8QB3W/" title="Gusano"><img src="https://scontent.cdninstagram.com/hphotos-xaf1/t51.2885-15/s640x640/sh0.08/e35/11934592_905119026244806_184077532_n.jpg" width="240"  alt="Gusano" style="float:left; margin:5px"></a>
Ya hace tiempo hablábamos del tema en [Borrar datos es difícil](https://mbpfernand0.wordpress.com/2011/03/31/borrar-datos-es-dificil/) donde se cuentan algunos detalles sobre lo difícil que puede ser eliminar completamente cualquier rastro de datos de nuestros discos.

Ya hablamos hace tiempo del bloqueo de usuarios infectados por parte de sus proveedores de internet [¿Deberían los proveedores de acceso desconectar a los usuarios infectados?](https://mbpfernand0.wordpress.com/2010/10/14/%C2%BFdeberian-los-proveedores-de-acceso-desconectar-a-los-usuarios-infectados/). La propuesta allí era ponerlos en cuarentena más allá de los avisos que algunos ya mandan: al final, el tráfico pasa a través de sus redes y tienen cierta capacidad de ver cuándo algunas cosas van mal: [It’s time to quarantine infected computers](http://countermeasures.trendmicro.eu/its-time-to-quarantine-infected-computers/)

> ISPs on an on-going basis should take advantage of the threat intelligence feeds of the security industry to identify compromised systems connected to their networks. Those systems should be moved to quarantine, the account owners should be contacted and directed to resources which will enable them to clean up and rectify the situation. Until such time as the infection is remediated the computer should be able to access only limited Internet resources. Don’t care will be made to care.

Esto tiene algunos problemas (inspección del tráfico, pérdida de productividad si nos desconectan...), en algunos casos no triviales.

También habíamos hablado del caso de Australia [¿Tienes malware? ¡Te desconectamos!](https://mbpfernand0.wordpress.com/2009/10/19/%C2%BFtienes-malware-%C2%A1te-desconectamos/) y de algunas empresas [Gusanos: las defensas de IBM y HP ](http://barrapunto.com/~fernand0/journal/14482).

Recientemente hemos conocido alguien que da un paso más allá, [New vigilante malware protects your computer from the bad guys](http://www.dailydot.com/politics/linux-wifatch-hack-vigilante/). Se trata de un troyano llamado Linux.Wifatch que elimina algunas familias conocidas de 'malware' que habitualmente se pueden encontrar en routers caseros. Parece que el propio troyano está protegido contra posibles usos maliciosos:

> As far as the researchers have found after months of investigation, however, Wifatch's creator has yet to do anything malicious. In fact, using cryptographic signatures, the malware's creator has even programmed the virus to guard against other hackers surreptitiously using the same network or backdoors.

Ya sabemos que mantener actualizados determinados dispositivos es difícil, porque los fabricantes y proveedores no nos dan demasiadas facilidades. Y también sabemos que es bastante frecuente encontrarse con casos de ataques como contábamos el otro día en [Mala seguridad, routers y ataques](http://fernand0.github.io/Mala-Seguridad-Routers-Y-Ataques/) pero como también podíamos leer sobre ataques lanzados utilizando cámaras de vigilancia [Attackers hijack CCTV cameras and network-attached storage devices to launch DDoS attacks](http://www.pcworld.com/article/2996137/attackers-hijack-cctv-cameras-and-network-attached-storage-devices-to-launch-ddos-attacks.html) así que uno no sabe si tener miedo de estos 'héroes' que nos protegen o agradecer su trabajo para que las infecciones no se propaguen más.
