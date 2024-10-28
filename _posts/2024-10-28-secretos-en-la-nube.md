---
layout: post
title: "Cuidado con los secretos divulgados en las nubes"
date: "2024-10-28 15:00:00 +0000"
category: seguridad
tags:
- secretos
- credenciales
- nubes
- seguridad
imagefeature: "https://live.staticflickr.com/65535/49001819652_aa6f039a3c_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/49001819652/in/photolist-QZx5a7-QZx6ko-RahWCq-2gbbsPU-2gtfXB8-2gyJLNz-2hE88Mw-2i4DCEC-2i7VsWw-2ikEXFT-2ir92Zg-2iu4T78-2k2jnoV-2k2k47D-2kMYWXj-2msehPX-2muELi7-2mwX6ep-2mZUYtU-2nMTcQW-2oZtXmJ-2p4LKbV-2porLVP-2qoT32P-2qoU7Sq-uzFJg7-uzQL3z-uzRyz2-uYupKk-vf6RA7-vf7y65-vfeixT-vw9myu-vwFZSZ-FJzgsB-FPeZty-H1UzxH-JwKUEN-Nu2fPh-NxdAvv-NAk8Em-NCSSF6-NCSUNn-NEbGS7-NHphds-NHpiqs-NHpv7o-NLEVLe-NLF1EH-Qf3E19" title="Callejeando"><img src="https://live.staticflickr.com/65535/49001819652_aa6f039a3c_z.jpg" width="427" height="640" alt="Callejeando"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Un experimento curioso: se dejan credenciales de la API de AWS en diversos sitios y se espera a ver qué sucede, monitorizando la actividad.

> In this research, I used AWS API credentials as canary tokens, strategically placing them in publicly accessible locations on the internet.

Los lugares elegidos fueron:

* Servidores públicos de código (GitHub, Gitlab, itBucket, DockerHub)
* Servicios públicos manejados por el atuor: servidores de FTP, web, blog
* Servicios Saas: Pastebin, JSFiddle
* Gestores de paquetes de código: NPMJS, PyPi
* Almacenes de datos en la nube (*Cloud Storage Buckets*): AWS S3, GCP Google Cloud Storage

Los resultados dicen que los intentos más rápidos de ataque viniveron desde las credenciales depositadas en npmJs (menos de 60 segundos), Pypi (119 segundos) y GitHub (127 segundos). En Pastebin tardaron 50 minutos y en otros ya pasamos a más de un día.

> Grab Quickness – I find it pretty amazing that some tokens were grabbed and used after a few seconds. The NPMJS token was grabbed in less than a minute which includes the overhead time of logging and detecting the access attempt. GitHub and Pypi were close behind with about 2 minutes until the access attempt.

La otra sorpresa es que no hubo ningún acceso en los servicios BitBucket y GitLab.

> No access attempts on BitBucket and GitLab. Going into this I was sure the tokens on these services will be grabbed pretty quickly, probably not as fast as on GitHub, but still, I didn’t’ expect 0 hits. I’m still not sure the reason for this, perhaps it’s due to them being less popular or maybe it is harder to scrape them automatically.

Espeluznante.
