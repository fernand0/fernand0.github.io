---
layout: post
title: "Descubrimiento de secretos a partir de la iluminación de los LED"
date: "2023-08-14 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- LED
- consumo
- criptografía
- criptoanálisis
imagefeature: 'https://live.staticflickr.com/3199/2345848214_8b7d678293.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/2345848214/" title="Luz "><img src="https://live.staticflickr.com/3199/2345848214_8b7d678293.jpg" alt="Luz " class="img-responsive img-centered"></a>

Los ataques que explotan canales secundarios de información suelen tener presencia en este sitio. En este caso se utilizan grabaciones en vídeo de los LED de encendido de algunos dispositivos para obtener claves. Lo cuentan en [Video-based Cryptanalysis BH USA 23 & DEFCON 31 Exploiting a Video Camera's Rolling Shutter to Recover Secret Keys from Devices Using Video Footage of Their Power LED](https://www.nassiben.com/video-based-crypta) y se basa en que los cálculos relacionados con operaciones criptográficas son costosos, lo que provoca un cambio de consumo en los dispositivos y, por lo tanto, un cambio de brillo en los LEDS.

> We show that cryptographic computations performed by the CPU change the power consumption of the device which affects the brightness of the device’s power LED.

Pueden obtener grabaciones en vídeo de las cámaras (modificando la tasa de captura de imágenes) y, a partir de allí extraer secretos criptográficos.

> This is done by obtaining video footage of a device’s power LED (in which the frame is filled with the power LED) and exploiting the video camera’s rolling shutter to increase the sampling rate by three orders of magnitude from the FPS rate (60 measurements per second) to the rolling shutter speed (60K measurements per second in the iPhone 13 Pro Max). The frames of the video footage of the device’s power LED are analyzed in the RGB space, and the associated RGB values are used to recover the secret key by inducing the power consumption of the device from the RGB values.

La intensidad/color del LED se puede utilizar para detectar el inicio de las operaciones criptográficas.

> The intensity/color of the power LEDs can be used to detect the beginning and end of cryptographic operations. 

También se basa en que las bibliotecas criptográficas tienen vulnerabilidades.

> The origin of the vulnerabilities is in the cryptographic libraries. 

Estos fallos están relacionados con algoritmos criptográficos sensibles a operaciones de criptoanálisis a través de canales laterales.

> We show that the combination of vulnerable cryptographic algorithms (i.e., that are vulnerable to cryptanalytic side-channel attacks) 

No tengo claro del todo cómo de fácil/realizable es el ataque, pero las posibilidades son muy interesantes.

En [Cameras Watching a Device's Power LED Prove Enough to Snaffle Cryptographic Secrets](https://www.hackster.io/news/cameras-watching-a-device-s-power-led-prove-enough-to-snaffle-cryptographic-secrets-4daeb5eb06e7) hablan del experimento, con seis dispositivos comerciales (lectores de tarjetas) y un teléfono Samsung S8 y algunas configuraciones sofisticadas.

> To prove the concept, the team took a pair of seemingly-secure and not known to be compromised gadgets — a selection of six commercial smart card readers connected to a laptop and a Samsung Galaxy S8 smartphone — and proceeded to capture their private cryptographic keys, entirely over-the-air. The first attack used a network security camera located more than 50 feet away from the target; the second an iPhone 13 Pro Max, working around the Galaxy S8's lack of power LED by instead watching the LED on a set of USB speakers connected to the same USB hub as the smartphone.
