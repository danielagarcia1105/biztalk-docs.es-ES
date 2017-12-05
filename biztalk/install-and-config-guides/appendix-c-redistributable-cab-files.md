---
title: "Apéndice C: archivos .cab redistribuibles | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2049d61-e169-4b30-869a-33d5af097941
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1a1f2b6866a2841abaa248479430a7584db3a0b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="appendix-c-redistributable-cab-files"></a>Apéndice C: Archivos .cab redistribuibles
El programa de instalación de BizTalk Server usa estos archivos CAB.

## <a name="biztalk-2016-cab-files"></a>Archivos CAB de BizTalk 2016

|Idioma|Vínculo de descarga|  
|--------------|-------------------|  
|EN|<ul><li>**X64**<br /><br /> <ul><li>Windows Server 2016: [http://go.microsoft.com/fwlink/p/?LinkId=746413](http://go.microsoft.com/fwlink/p/?LinkId=746413)</li><li>Windows Server 2012 R2: [http://go.microsoft.com/fwlink/p/?LinkId=746412](http://go.microsoft.com/fwlink/p/?LinkId=746412)</li><li>Windows 10: [http://go.microsoft.com/fwlink/p/?LinkId=746408](http://go.microsoft.com/fwlink/p/?LinkId=746408)</li><li>Windows 8.1: [http://go.microsoft.com/fwlink/p/?LinkId=746411](http://go.microsoft.com/fwlink/p/?LinkId=746411)</li></ul></li><li>**X32**<br /><br /><ul><li>Windows 10: [http://go.microsoft.com/fwlink/p/?LinkId=746409](http://go.microsoft.com/fwlink/p/?LinkId=746409)</li><li>Windows 8.1: [http://go.microsoft.com/fwlink/p/?LinkId=746410](http://go.microsoft.com/fwlink/p/?LinkId=746410)</li></ul></li></ul>|  

> [!NOTE] 
> Windows 10 y Windows Server 2016 usan los mismos archivos CAB que Windows 8.1 y Windows Server 2012 R2. Como resultado, tienen el mismo nombre de archivo.

## <a name="biztalk-2013-r2-and-2013-cab-files"></a>Archivos CAB de BizTalk 2013 R2 y 2013  
  
|Idioma|Vínculo de descarga|  
|--------------|-------------------|  
|EN|<ul><li>**X64**<br /><br /> <ul><li>Windows Server 2012: [http://go.microsoft.com/fwlink/p/?LinkId=269616](http://go.microsoft.com/fwlink/p/?LinkId=269616)</li><li>Windows Server 2008: [http://go.microsoft.com/fwlink/p/?LinkId=269613](http://go.microsoft.com/fwlink/p/?LinkId=269613)</li><li>Windows 8: [http://go.microsoft.com/fwlink/p/?LinkId=269615](http://go.microsoft.com/fwlink/p/?LinkId=269615)</li><li>Windows 7: [http://go.microsoft.com/fwlink/p/?LinkId=269614](http://go.microsoft.com/fwlink/p/?LinkId=269614)</li></ul></li><li>**X32**<br /><br /> <ul><li>Windows 8: [http://go.microsoft.com/fwlink/p/?LinkId=269612](http://go.microsoft.com/fwlink/p/?LinkId=269612)</li><li>Windows 7: [http://go.microsoft.com/fwlink/p/?LinkId=269611](http://go.microsoft.com/fwlink/p/?LinkId=269611)</li></ul></li></ul>|  
  
## <a name="important-info"></a>Información importante

- SQL XML puede tener sus propios requisitos de software (como `.NET Framework 3.5` y `.NET Framework 2.0`), que no se incluyen en el archivo CAB. Si BizTalk Server tiene acceso a Internet, los requisitos de software de SQL XML podrían instalarse automáticamente. Si BizTalk Server no tiene acceso a Internet, debe instalar manualmente los requisitos de software de SQL XML.

- También se muestran las rutas de acceso de instalación de archivo CAB en el **Setup.xml** archivo en la carpeta de instalación ([!INCLUDE[btsBizTalkServerPathx64_md](../includes/btsbiztalkserverpathx64-md.md)]\<su versión\>).
  
-   Cierto software que necesita [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se instala en el equipo cuando se ejecuta el programa de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   El programa de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ofrece la opción de descargar los requisitos previos de software de la Web o extraerlos de los archivos CAB. Si elige los archivos CAB, debe descargarlos antes de ejecutar el programa de instalación.  
  
-   No puede usar archivos CAB de versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Debe descargar los archivos CAB mediante los vínculos proporcionados en la tabla.  
  
-   No es posible descargar archivos .cab mediante una sesión Telnet.  