---
layout: post
title: "Escribiendo programas maliciosos en el registro del sistema"
date: "2022-07-21 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- registro
- malware
- ataques
- Windows
imagefeature: 'https://live.staticflickr.com/3272/2852272703_eeaac9b023.jpg'
---
<a href="https://flickr.com/photos/fernand0/2852272703/" title="Expo. Máscara "><img src="https://live.staticflickr.com/3272/2852272703_eeaac9b023.jpg" alt="Expo. Máscara " class="img-responsive img-centered"></a>
Cualquier cosa que pueda ser escrita o leída por un programa será utilizada para intentar atacarnos. Un ejemplo curioso es [Hackers are now hiding malware in Windows Event Logs](https://www.bleepingcomputer.com/news/security/hackers-are-now-hiding-malware-in-windows-event-logs/) donde nos cuentan como algunos atacantes están usando el registro de actividad de Windows para esconder programas maliciosos que después serán activados y utilizados para infectar nuestro sistema.

Se trataría de una campaña dirigida, con un grado alto de personalización, pero también uso de herramientas disponibles por ahí.

> The investigation revealed that the malware was part of a "very targeted" campaign and relied on a large set of tools, both custom and commercially available.

En particular, la inserción de programas maliciosos para la shell en los registros de actividad de los servicios de gestión de claves.

> One of the most interesting parts of the attack is injecting shellcode payloads into Windows event logs for the Key Management Services (KMS), an action completed by a custom malware dropper.

El ataque se basaría en utilizar una DLL (*Dynamic Link Library*) que permitiría escribir en el registro el código malicioso.

> The dropper copies the legitimate OS error handling file WerFault.exe to ' _C:\\\Windows\\\Tasks_ ' and then drops an encrypted binary resource to the ' _wer.dll_ ' (Windows Error Reporting) in the same location, for DLL search order hijacking to load malicious code.  

Una vez instalado, busca si encuentra alguna señal de que ya se ha realizado la infección. Si no es así, comienza a escribir el código malicioso en bloques de 8Kb, que después serán combinados para formar el código para la siguiente fase del ataque.

> Legezo says that the dropper's purpose is to loader on the disk for the side- loading process and to look for particular records in the event logs (category 0x4142 - 'AB' in ASCII. If no such record is found, it writes 8KB chunks of encrypted shellcode, which are later combined to form the code for the next stager 

Interesante.
