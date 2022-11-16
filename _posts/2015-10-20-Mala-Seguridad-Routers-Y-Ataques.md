---
layout: post
title: "Mala seguridad, routers y ataques"
date: "Tue Oct 20 19:30:01 +0100 2015"
category: seguridad
tags:  [seguridad, wifi, configuración, ataques, routers, hogar, troyanos]
---





<a href="https://www.flickr.com/photos/fernand0/858579159/" title="Antenas"><img src="https://c2.staticflickr.com/2/1393/858579159_7bc0b32de3_m.jpg" width="240"  alt="Antenas" style="float:left; margin:5px"></a>

Otra entrada sobre un ataque (esta vez a gran escala) por malas prácticas de seguridad. En [Lax Security Opens the Door for Mass-Scale Abuse of SOHO Routers](https://www.incapsula.com/blog/ddos-botnet-soho-router.html) nos cuentan algunos erores de seguridad que llevaron a tener conectados a internet en casa de mucha genet routers con configuraciones inseguras. Gracias a eso, fue posible orquestar ataques distribuidos de denegación de servicio (DDOS) con una cierta incidencia.

Se trataba de routers SOHO cuya interfaz de configuración estaba accesible a internet sin problemas, y configurados con claves elegidas por defecto por el proveedor (amiguitos, cambiad la clave de vuestro router. ¡Ya!):

> However, further inspection revealed that all units are remotely accessible via HTTP and SSH on their default ports. On top of that, nearly all are configured with vendor-provided default login credentials.

En este caso estas vulnerabilidades no se utilizaban para atacar a los propios usuarios (aunque seguramente en algunos casos también) sino para infectar los propios routers y lanzar los ataques desde allí. Naturalmente, esto también implicaba la idea de infectar nuevos routers que pudieran estar a su alcance.
