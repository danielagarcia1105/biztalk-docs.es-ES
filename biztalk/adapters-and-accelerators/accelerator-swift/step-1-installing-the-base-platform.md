---
title: 'Paso 1: Instalar la plataforma Base | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- platforms
- installing, base platform
- base platform
ms.assetid: 27da386f-90c7-414f-a4e3-e909f0c18371
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eaae10965aa240af86ee381a3504a4ec64c8fc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986957"
---
# <a name="step-1-installing-the-base-platform"></a>Paso 1: Instalar la plataforma Base
Para la plataforma base, instale Microsoft [!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] y [!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] Service Pack 2 en cada servidor con las opciones de instalación predeterminadas. Siga estas recomendaciones:  
  
## <a name="pre-installation"></a>Antes de la instalación  
  
- Deshabilitar todos los programas antivirus durante la instalación de software. Algunos programas de software antivirus pueden impedir que los componentes de software requiere instalar correctamente.  
  
- Asegúrese de que escriba la información de licencia adecuada (número máximo de conexiones que han comprado por servidor). Rendimiento de sistema puede verse afectado por el número de conexiones disponibles.  
  
- Asegúrese de que ha instalado todos los requisitos previos de software necesarios para una instalación de BizTalk Server. Para obtener más información, consulte las instrucciones de instalación de BizTalk Server en [ http://go.microsoft.com/fwlink/?LinkId=81041 ](http://go.microsoft.com/fwlink/?LinkId=81041). [Guía de instalación de BizTalk 2013 R2 Accelerator for SWIFT](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1).  
  
- Probar todas las actualizaciones críticas en un entorno sin conexión antes de instalarlas en sus servidores de producción.  
  
- Asegúrese de que instalar todas las revisiones aplicables para todos los productos que se instalación como parte de la implementación. Para obtener más información, consulte los siguientes orígenes:  
  
  - Ayuda en pantalla de Microsoft BizTalk Server  
  
  - Instrucciones de instalación de BizTalk Server en [ http://go.microsoft.com/fwlink/?LinkId=81041 ](http://go.microsoft.com/fwlink/?LinkId=81041).  
  
  - Microsoft [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] sitio Web en [ http://go.microsoft.com/fwlink/?linkid=48685 ](http://go.microsoft.com/fwlink/?linkid=48685).  
  
  - Sitio Web del centro de descarga de Microsoft en [ http://go.microsoft.com/fwlink/?linkid=48686 ](http://go.microsoft.com/fwlink/?linkid=48686).  
  
  - [!INCLUDE[btsWinUpdate](../../includes/btswinupdate-md.md)] Sitio Web en [ http://go.microsoft.com/fwlink/?linkid=48687 ](http://go.microsoft.com/fwlink/?linkid=48687).  
  
- Para evitar los ataques de virus, instalar la plataforma desde un CD y desconecte cada servidor de Internet, desconecte los cables y deshabilitar a los adaptadores de red.  
  
- Dar formato a una partición limpia mediante el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] sistema de archivos NTFS.  
  
## <a name="active-directory"></a>Active Directory  
  
-   Crear un usuario de dominio llamado **Admin** y agréguelo a la variable local **administradores** grupo en todos los equipos de la implementación. Durante la instalación, inicie sesión en los servidores de implementación con esta cuenta de dominio.  
  
-   No configura los adaptadores de red o unir todos los dominios en este momento. Esta guía describe cómo configurar estas opciones más adelante cuando comience el proceso de implementación.  
  
## <a name="internal-web-servers-mrsr-site"></a>Servidores Web internos (sitio MRSR)  
  
-   Asegúrese de que Internet Information Services (IIS) está instalado solo en lo servidores de sitio MRSR.  
  
-   Asegúrese de que Internet Information Services (IIS) no está instalado en el Internet Security and Acceleration (ISA) Server.  
  
-   Asegúrese de que el servicio de Message Queuing (MSMQ) está instalado solo en lo servidores de sitio MRSR. Si los servidores de mensajería de BizTalk también se usará como el sitio MRSR servidores, no instale MSMQ en esos servidores.