---
layout: post
title: "Los dominios, la identidad y lo que puede pasar cuando no se tiene cuidado"
date: "2022-04-18 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- dominios
- identidad
- npm
imagefeature: 'https://live.staticflickr.com/39/78845245_77bbdb9660.jpg'
---
<a href="https://flickr.com/photos/fernand0/78845245/" title="Regalos: ¡dos paquetes! "><img src="https://live.staticflickr.com/39/78845245_77bbdb9660.jpg" alt="Regalos: ¡dos paquetes! " width="240" style="float:left; margin:5px"></a>
A veces recomendamos demasiado alegremente que la gente registre un dominio para gestionar su 'marca' (personal o de empresa) y nos olvidamos de las consecuencias negativas que esto puede tener si no se tiene un poco de cuidado.
**Actualización (2022-11-19):** casualmente veo este artículo argumentando a favor del uso de un dominio, [Why everyone should register a domain name](https://www.theguardian.com/commentisfree/2013/mar/28/why-everyone-should-register-domain-name). Es de hace tiempo, pero muestra la idea.

Vale: utilizar una dirección de correo electrónico genérico puede parecer poco profesional, pero todavía es peor si no mantenemos el compromiso con el dominio que elijamos.

En [Thousands of npm accounts use email addresses with expired domains](https://therecord.media/thousands-of-npm-accounts-use-email-addresses-with-expired-domains/) nos cuentan el caso de un análisis de los paquetes npm y han descubierto que hay miles de desarrolladores de JavaScript que han utilizado dominios de correo que después han caducado para registrar sus cuentas en npm (Node Package Manager):

> An academic research project found that thousands of JavaScript developers are
using an email address with an expired domain for their npm accounts, leaving
their projects exposed to easy hijacks.

De hecho, algunos de estos dominios estarían a la venta en algunos sitios.

>  Researchers said they found that 2,818 project maintainers were still using an email address for their accounts that had an expired domain, some of which they found on sale on sites like GoDaddy.

Esto es un problema porque alguien que lo descubra podría intentar hacerse pasar por el desarrollador en cuestión y, tal vez, conseguir algún objetivo peligroso. 

> The team argued that attackers could buy these domains, re-register the maintainer's address on their own email servers, and then reset the maintainer's account password and take over his npm packages.

Algunos paquetes, al instalarse, ejecutan *scripts*, muchos paquetes tienen un número importante de personas manteniéndolos y algunos lo que tienen son contribuidores. Sin olvidar las dependencias que existen entre unos paquetes y otros.

> 2.2% (33,249) of packages used install scripts, which could be abused to run malicious commands and is against npm best security practices;

> The Top 1% packages (14,941) had an average of 32.4 maintainers per package, opening the door for attacks via the accounts of inactive or inattentive developers;

> 389 packages had 40 contributors for every maintainer, opening the door for the accidental insertion of security flaws or flooding a project with contributions to sneak in malicious code;

> The top 1% maintainers own an average number of 180.3 packages with direct dependents of 4,010 average packages, meaning some developers could be overworked or not have time to thoroughly maintain or review package changes.

Al final, el problema se debe a una identificación débil de las personas: una dirección de correo. Pero mientras las cosas estén así debemos tener cuidado con los dominios y lo que hacemos con ellos, porque nos podemos llevar un disgusto. Con cualquiera de los activos digitales que hayamos registrado usando estos dominios.
