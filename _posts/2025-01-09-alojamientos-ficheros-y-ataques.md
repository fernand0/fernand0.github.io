---
layout: post
title: "Confundiendo a los usuarios usando sitios habituales de alojamiento de información"
date: "2025-01-09 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- phishing
- servicios
- nube
- alojamientos
imagefeature: "https://live.staticflickr.com/65535/48222510601_9cd6c8fe2c_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/48222510601/in/photolist-SUv93m-24rd3T6-24rd49g-2e7RF8G-2f3D3T4-2gtfYmz-2gyJfDL-2hfQ4cw-2hxQfGx-2idYLKA-2jaqkz3-2kx71fT-2kFMYS4-2kMYwwu-2kMYX5U-2kUTtTy-2kWjdDB-2mdfYKq-2mdfYLN-2nffsJm-2prRLHM-2pEwCSo-2pEwCU2-2pK3CZt-2pMN8kU-s2ioZC-s2rqsc-BFN6y9-CA8oFN-Ev3AE3-EYwm9m-FgzRAP-FqF26E-G3FS1y-G5ZudM-PRRmtw-PUBziP-QbmpPJ-Qe9Vc6-QEpmoz-RpkB9A-RsTxQi-RBPJCT-RRmD2H-RVQmnq-SEtYKH-T2HibJ-T6mt6a-24h9dgM-e5L8WT" title="Puerta del Perdón"><img src="https://live.staticflickr.com/65535/48222510601_9cd6c8fe2c_z.jpg" width="427" height="640" alt="Puerta del Perdón"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

En [File hosting services misused for identity phishing](https://www.microsoft.com/en-us/security/blog/2024/10/08/file-hosting-services-misused-for-identity-phishing/) hablan del uso de los sitios de alojamiento de ficheros para realizar ataques: se comprometen las credenciales (o algún sistema de acceso) de un usuario, se sube un fichero al servicio y se comparte con la organización objetivo del ataque. El ataque tiene éxito porque la gente confía en estos servicios de alojamiento (estamos acostumbrados a usarlos, recibir compartidos, ...)

> The attack typically begins with the compromise of a user within a trusted vendor. After compromising the trusted vendor, the threat actor hosts a file on the vendor’s file hosting service, which is then shared with a target organization. This misuse of legitimate file hosting services is particularly effective because recipients are more likely to trust emails from known vendors, allowing threat actors to bypass security measures and compromise identities

Una vez que se ha compartido el fichero el servicio enviará un enlace a las víctimas. No es un mensaje falso, sino uno de los que generan este tipo de servicios habitualemente.

> Once the threat actor shares the files on the file hosting service with the intended users, the file hosting service sends the target user an automated email notification with a link to access the file securely.

Cuando el usuario accede al enlace se le pide que se identifique (con posible uso de medidas adicionales de seguridad del servicio)

> When the targeted user accesses the shared file, the user is prompted to verify their identity by providing their email address:

Finalmente, el usuario puede ver el documento que, típicamente, invita a pinchar en algún enlace (ahora ya sí, malicioso)

> the user is successfully authorized and can view a document, often masquerading as a preview, with a malicious link, which is another lure to make the targeted user click the “View my message” access link.

Ahora este enlace redirige al usuario a una página de phishing que emula el procedimiento de acceso habitual y allí ya le roban sus credenciales.

> This link redirects the user to an adversary-in-the-middle (AiTM) phishing page, where the user is prompted to provide the password and complete multifactor authentication (MFA). The compromised token can then be leveraged by the threat actor to perform the second stage BEC attack and continue the campaign.

Estamos tan acostumbrados a identificarnos, reidentificarnos y volvernos a identificar en estas plataformas con este tipo de flujos de trabajo que, aparentemente, los usuarios caen sin darle muchas vueltas.

Atención.
