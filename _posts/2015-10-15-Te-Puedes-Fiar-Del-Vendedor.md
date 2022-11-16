---
layout: post
title: "¿Te puedes fiar del vendedor de tu ordenador?"
date: "Wed Oct 15 13:45:01 +0100 2015"
category: seguridad
tags:  [seguridad, confianza, trust, superfish, toshiba, ssl]
---





<a href="https://www.flickr.com/photos/fernand0/11389057736/" title="Web"><img src="https://c2.staticflickr.com/4/3830/11389057736_106a029794_m.jpg" width="240"  alt="Web" style="float:left; margin:5px"></a>

Si has estado atento a las noticias de informática en los últimos meses seguramente has oído/leído algo sobre [Superfish](https://support.lenovo.com/us/en/product_security/superfish). Con la intención de ofrecer productos similares a los que los usuarios supuestamente podrían estar interesados Lenovo introdujo una herramienta para interceptar el tráfico web (y, en particular, el tráfico cifrado). 

Traigo aquí un resumen en [A third-party, man-in-the-middle proxy used by Superfish is also used in other apps](http://www.computerworld.com/article/2887079/superfish-security-flaw-exists-in-other-apps-non-lenovo-systems.html) donde nos alertaban. No solo de lo mala que era la idea en sí sino también, claro, de las consecuencias laterales (y no previstas): que otras aplicaciones traten de sacar partido de este 'truquillo'.

La explicación del modo de funcionamiento, un proxy que se colocaba entre nuestra conexión y los sitios que queríamos visitar: 

>  Superfish uses a man-in-the-middle proxy component to interfere with encrypted HTTPS connections, undermining the trust between users and websites. It does this by installing its own root certificate in Windows and uses that certificate to re-sign SSL certificates presented by legitimate websites.

La utilización de un certificado común para todos los sistemas:

> Security researchers found two major issues with this implementation. First, the software used the same root certificate on all systems and second, the private key corresponding to that certificate was embedded in the program and was easy to extract.

Y, finalmente, la utilización de componentes de terceras partes para toda esta maniobra, lo que haría posible su utilización por parte de otros programas

> But it gets worse. It turns out Superfish relied on a third-party component for the HTTPS interception functionality: an SDK (software development kit) called the SSL Decoder/Digestor made by an Israeli company called Komodia.

Para eliminarlo hay instrucciones en [Superfish, Komodia, PrivDog vulnerability test (updated again!)](https://filippo.io/Badfish/) y también la propia Lenovo proporciona herramientas: [SuperFish Uninstall Instructions](https://support.lenovo.com/us/en/product_security/superfish_uninstall).

A lo mejor lo más directo sería borrar el sistema e instalar uno limpio (con la ventaja de que, seguramente, quitaríamos otras cosas que no sean tan peligrosas, pero puedan ser molestas o poco convenientes).

Ya hemos hablado algunas veces de [confianza](http://fernand0.github.io/tags/confianza/) por aquí y siempre conviene recordar el clásico [Reflections on trusting trust](http://dl.acm.org/citation.cfm?id=358210) y uno más reciente del que hablábamos en [La confianza](https://mbpfernand0.wordpress.com/2011/12/21/la-confianza/).
