---
layout: post
title: "La policía puede limpiar tu sistema"
date: "2025-09-01 15:00:00 +0000"
category: seguridad
tags:
- FBI
- malware
- ataques
- limpieza
imagefeature: "https://live.staticflickr.com/65535/53840983659_1441acebe2_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/53840983659/in/dateposted/" title="Muro, cruz de madera y plantas"><img src="https://live.staticflickr.com/65535/53840983659_1441acebe2_z.jpg" width="427" height="640" alt="Muro, cruz de madera y plantas"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Creo que no es la primera vez que hablamos de esto, pero tampoco estoy seguro. En [FBI Deletes PlugX Malware from 4,250 Hacked Computers in Multi-Month Operation](https://thehackernews.com/2025/01/fbi-deletes-plugx-malware-from-4250.html) nos cuentan como el FBI borró, con autorización judicial, un programa malicioso (*malware*) de más de 4000 sitios.

> The U.S. Department of Justice (DoJ) on Tuesday disclosed that a court-authorized operation allowed the Federal Bureau of Investigation (FBI) to delete PlugX malware from over 4,250 infected computers as part of a "multi-month law enforcement operation."

Si lo pensamos, es bastante interesante como este tipo de acciones puden resonar en el sentido de que nos parezca positivo que las policías se dediquen a protegernos, aunque el tema puede tener sus propias aristas: ¿entrar en mi sistema para arreglarlo? ¿Y si al arreglarlo estropean otra cosa? ¿Es legítimo puesto que por mi inacción se pueden estar produciendo daños a otros?

El trabajo consistión en borrar los ficheros creados por el programa malicioso, borrar las claves de registro del programa que le permitían ejecutarse automáticamente, crear un programa temporal que borraba el programa después de detenerlo, y algunas tareas más de limpieza.

Según el FBI no era peligroso para las máquinas infectadas.

> The FBI said the self-delete command does not affect any legitimate functions or files on the targeted devices located within the U.S. nor transmit any other data from them.

Interesante.
