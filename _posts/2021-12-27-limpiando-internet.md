---
layout: post
title: "El FBI limpiando sistemas infectados, al menos parcialmente."
date: "2021-12-27 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- FBI
- malware
- web shell
- limpieza
- desinfección
imagefeature: 'https://live.staticflickr.com/7/8066571_ec54fcd1ff.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/8066571/" title="Semana Santa. Moto de la policía. "><img src="https://live.staticflickr.com/7/8066571_ec54fcd1ff.jpg" alt="Semana Santa. Moto de la policía. " width="240" style="float:left; margin:5px"></a>
Imaginemos que pasas por delante de una puerta que está abierta y dentro ves la puerta de una habitación y dentro un montón de billetes. Sabemos que no lo robarrías pero.... ¿Volverías la puerta de la habitación o la cerrarías para que alguien que pase no tenga malas tentaciones? Tiene su peligro, porque si alguie te ve entrar y luego faltara dinero, podrían pensar que has sido tú.
Podrías llamar a la policía y que se ocupen ellos, que seguramente nadie les acusaría con la misma facilidad de robar. 
Algo así ha estado pasando con el FBI (aunque sin que nadie les avise). En [FBI cleans web shells from hacked Exchange servers in rare active defense move](https://www.csoonline.com/article/3615691/fbi-cleans-web-shells-from-hacked-exchange-servers-in-rare-active-defense-move.html) nos cuentan como el FBI obtuvo permiso del juez para eliminar puertas traseras de sistemas infectados.

Es un movimiento interesante porque esto supone que detectan un sistema infectado, son capaces de entrar en el mismo (la puerta no está exactamente abierta, hace falta ciertas herramientas y conocimiento para poder acceder), eliminan el problema y se van.

> In a move that has been described as unprecedented, the FBI obtained a court order that allowed it to remove a backdoor program from hundreds of private Microsoft Exchange servers that were hacked through zero-day vulnerabilities earlier this year.

La cosa tiene su miga, porque muchas veces esos servidores están medio abandonados o mal gestionados y pueden ser utilizados para atacar y provocar problemas en otros sistemas. 
En este caso, una `web shell` es un programa que instalan los malos para poder acceder al sistema y  'gestionarlo' desde su navegador.

> A web shell is a type of program that hackers install on hacked web servers to grant them backdoor access and remote command execution capabilities on those servers through a web-based interface.

En la solicitud del FBI explicaban que, a pesar de haber avisado tanto el fabricante, como otras organizaciones y ellos mismos, muchos servidores seguían infectados. Existiendo una solución para remediarlo.

> In its warrant application, dated April 13, the FBI argues that despite the public awareness campaigns by Microsoft, CISA and the FBI itself, many servers remained infected with the web shell ...

No sólo recibieron permiso para entrar en los sistemas con las credenciales que consiguieron para ello, sino que también recibieron autorización para conservar estos programas maliciosos, como evidencias para posibles acciones posteriores.

> The FBI was also allowed to make a copy of the web shells first because they could constitute evidence.

Sin embargo, no recibieron autorización para parchear (esto es, aplicar las soluciones necesarias para proteger los sistemas de ataques posteriores) o para eliminar otros programas maliciosos que pudieran encontrar.

> This means the FBI was not granted permission to patch the vulnerabilities to protect the servers from future exploitation or to remove any additional malware or tools that hackers might have already deployed.

Tiene sentido porque modificar el sistema puede tener consecuencias que serían difíciles de evaluar para un visitante casual, que no conoce toda la configuración y las actividades del sitio en cuestión.

Según la nota, no sería la primera vez que habían obtenido permiso (ellos u otras fuerzas del orden) para enviar instrucciones a programas maliciosos en sistemas infectados.

> This is not the first time when the FBI or law enforcement authorities from other countries have sent commands to malware running on infected computers. 

Nos cuenta el caso de la Gendarmería francesa, que habría sido autorizada para inhabilitar un servidor de 'comando y control' que se utilizaba para desplegar un programa malicioso de minado de criptomonedas, reemplazándolo con un servidor de desinfección.

> In 2019, the French National Gendarmerie, working with antivirus vendor Avast, disabled the command-and-control server used by the Retadup worm that deployed cryptocurrency mining malware and replaced it with a "disinfection server." 

Pero se trataba más bien, nos dicen, de aproximaciones pasivas. Desactivaban el sistema de control de una red de programas amliciosos que contactaban con este sistema para recibir instrucciones.

> Placing a specific command on a seized server knowing that malware programs are programmed to contact that server and execute that command is a somewhat passive approach. 

Elogian también la transparencia del FBI y el Departamento de Justicia, así como la limitación en el ámbito de actividades desarrolladas.

> It seems that the FBI and the DOJ tried to be transparent and were careful to limit the scope of their actions in this case.

Muy interesante.
