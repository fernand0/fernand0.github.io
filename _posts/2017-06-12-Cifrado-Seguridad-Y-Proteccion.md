---
layout: post
title: "Cifrado, seguridad y protección de la informacón: FBI contra Apple"
date: "Mon Jun 12 16:45:01 +0100 2017"
category: seguridad
tags: [seguridad, criptografía, cifrado, FBI, apple]
imagefeature: https://scontent.cdninstagram.com/t51.2885-15/e35/13736867_876647612440788_744421225_n.jpg
---




La criptografía casi nunca es la parte débil de un sistema (lo que no nos impide recordar que inventar criptografía es difícil y que es mejor no hacer experimentos con eso). Ya hace unos meses hubo un caso en el que el FBI solicitó a Apple que aligerara los medios de protección del iPhone de un terrorista, tratando de obtener la posible información que pudiera haber en su teléfono. Apple se negó y aquello hizo bastante ruido, que llegó incluso a los noticieros 'normales'.

<a href="https://www.instagram.com/p/BH742_VBtWA/" title="Enigma"><img src="https://scontent.cdninstagram.com/t51.2885-15/e35/13736867_876647612440788_744421225_n.jpg" width="240"  alt="Enigma" style="float:left; margin:5px"></a>

Me gustó ver [Encryption isn’t at stake, the FBI knows Apple already has the desired key](https://arstechnica.com/apple/2016/02/encryption-isnt-at-stake-the-fbi-knows-apple-already-has-the-desired-key/) donde se comenta sobre el tema, y las ténicas que se utilizan para proteger la información del iPhone.

En primer lugar, para evitar los ataques de fuerza bruta contra el PIN, retrasan los intentos a partir del cuarto (cada vez cuesta más seguir probando), el teléfono se puede configurar para que se borre después del décimo intento fallido y finalmente, la forma de conseguir la clave de descifrado a partir del PIN también es lenta:

> PINs, especially four-digit PINs, are highly susceptible to brute-force attacks. With four digits and hence only 10,000 possible combinations, it's straightforward to simply try every number in sequence until you hit the right one. To combat this, the iPhone uses three specific techniques.

> The first is that the iPhone imposes delays between PIN attempts. While the first four attempts can be entered back-to-back, the iPhone will force you to wait one minute before the fifth attempt, five minutes before the sixth, 15 minutes before the seventh and eighth, and a full hour before the ninth.

> The second technique is that the iPhone can be configured to wipe the device after ten failed PIN attempts. When this option is turned on, the phone will discard its file system key after 10 bad PINs, rendering all the file system metadata (including the per-file keys) permanently inaccessible.

> The third and final technique is that the computation used to derive the PIN key from the PIN itself is slow, taking approximately 80 milliseconds.

Por lo tanto, lo que el FBI trataba de conseguir era aligerar esas restricciones para lanzar sus propios ataques de fuerza bruta con ciertas garantías.

> The FBI is asking for Apple to create a custom iPhone firmware that removes the escalating delays and omits the device wipe.

En definitiva, están reconociendo que el cifrado es bueno, y sólo tratarían de saltarse una de las barreras alrededor de ese cifrado.

> Overall, the FBI's request could be seen as a testament to just how good encryption is. The FBI can't attack the iPhone's encryption directly, and it can't bypass the firmware signature mechanism. There's no existing backdoor to the crypto.

Intersante
