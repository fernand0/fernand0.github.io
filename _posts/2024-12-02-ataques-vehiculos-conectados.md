---
layout: post
title: "Los vehículos, los nuevos servicios y los mismos fallos de siempre"
date: "2024-12-02 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- fallos
- vulnerabilidades
- coches
- acceso
imagefeature: "https://live.staticflickr.com/5626/30868027816_2f61bb7016_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/30868027816/in/photolist-iWjtSn-iWmaAC-iWmfhb-iWmqZy-iWmHKh-iWnN7J-iWo56C-P2GHf9-PWnmzQ-PWnqp3-QDt6D5-QDt7BY-QEpoei-RdKKpk-T3mgby-2ihYpNm-2jyQKrb-2jyQKwb-2jyV5Yt-2jyV61n-2k6QkPf-2k6UMpV-2k9iNdX-2oq8L6w-2oTPd7e-imqeXw-iWjo3r-7rVm-3DbfSb-46QwzX-4hMRXV-2UX5C-2UXqV-2UXvK-4zdznx-5wmnJT-ya2Zh-DsDom-9bzGSZ-9gHUXi-7BmSr-2iWXAm" title="La gilda del norte"><img src="https://live.staticflickr.com/5626/30868027816_2f61bb7016_z.jpg" width="640" height="427" alt="La gilda del norte"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Creo que venimos hablando de este tema desde las primeras versiones de este sitio, desde varios puntos de vista:

- Las diferentes industrias que se digitalizan cometen los mismos errores que las que lo hicieron anteriormente y no aprovechan lo que se ha aprendido en estos años. No sólo eso, sino que a pesar de desarrollar nuevas plataformas, no lo hacen con los principios adecuados, que garanticen que se hace bien.
- La industria del automóvil ya ha pasado varias veces por estos problemas (diez años va a cumplir, por ejemplo, este: [[PFD]  Remote Exploitation of an Unaltered Passenger Vehicle ](https://ioactive.com/pdfs/IOActive_Remote_Car_Hacking.pdf) a cargo de Charlie Miller (uno de los primeros en ganar notoriedad con estos temas) y Chris Valasek, también curtido en estas batallas.

Em [Hacking Kia: Remotely Controlling Cars With Just a License Plate](https://samcurry.net/hacking-kia) Sam Curry nos hablan del caso del conocido fabricante Kia y una serie de fallos que permitirían a un atacante controlar algunas funciones importantes del vehículo conociendo su matrícula.

> ... a set of vulnerabilities in Kia vehicles that allowed remote control over key functions using only a license plate.

Esto incluía, claro, obtener información personal:

> Additionally, an attacker could silently obtain personal information, including the victim's name, phone number, email address, and physical address.

La cuestión es que con instrucciones y métodos muy sencillos era posible realizar los ataques porque casi todo parece estar mal: un identificador que es fácil de conocer, pero también otros fallos de acceso a los sistemas que realizaban las acciones. En el artículo se detallan las ideas principales.
