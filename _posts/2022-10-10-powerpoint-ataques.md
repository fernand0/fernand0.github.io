---
layout: post
title: "Previsualización y ataques"
date: "2022-10-10 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- powerpoint
- ataques
- previsualizacción
imagefeature: 'https://live.staticflickr.com/30/43497843_8a0cc516cb.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/43497843/" title="CEDI. The ideal of Verified Software. "><img src="https://live.staticflickr.com/30/43497843_8a0cc516cb.jpg" alt="CEDI. The ideal of Verified Software. " class="img-responsive img-centered"></a>
Parece que nos cuesta aprender: si hay una característica que permite conectarse a internet en algo que no se ha desarrollado cuidadosamente, alguien la aprovechará para atacarnos.

En este caso hablamos de [Hackers use PowerPoint files for 'mouseover' malware delivery](https://www.bleepingcomputer.com/news/security/hackers-use-powerpoint-files-for-mouseover-malware-delivery/) una característica de las que llamaríamos 'chulas': cuando pasas el ratón por encima de un enlace en un 'PowerPoint' se puede ver una vista previa de la cosa. En este caso se intenta descargar una imagen.

> When opening the lure document in presentation mode and the victim hovers the mouse over a hyperlink, a malicious PowerShell script is activated to download a JPEG file (“DSC0002.jpeg”) from a Microsoft OneDrive account.

Pero la imagen resulta ser una DLL cifrada y se arma el lío.

> The JPEG is an encrypted DLL file (lmapi2.dll), that is decrypted and dropped in the 'C:\ProgramData\' directory, later executed via rundll32.exe. A registry key for persistence is also created for the DLL.
