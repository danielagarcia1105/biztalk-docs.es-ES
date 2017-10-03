---
title: 'Paso 7: Configurar los servidores front-end HTTP de BizTalk | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, HTTP servers
- HTTP server, configuring
ms.assetid: 6b7e0b48-bb20-42f4-84a5-092ff3a02741
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5840099816149265711744373e08d3a9a9d91cd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-configuring-the-biztalk-http-front-end-servers"></a>Paso 7: Configurar los servidores front-end HTTP de BizTalk
Esta sección proporciona instrucciones sobre cómo configurar los servidores Web de su [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] implementación.  
  
> [!NOTE]
>  En la implementación de equipo único, este equipo es el mismo equipo que el que realiza la mensajería y procesamiento.  
  
### <a name="to-configure-the-biztalk-http-front-end-servers"></a>Para configurar los servidores front-end HTTP de BizTalk  
  
1.  Instale Internet Information Services (IIS) y ASP.NET.  
  
2.  Abra el Administrador de IIS y seleccione **extensiones de servicio Web**. Asegúrese de que ASP.NET versión 1.1 y versión 2.0 ASP.NET se establecen en **permitido**.  
  
3.  Asegúrese de que el **Message Queue Server** service (MSMQ) con **compatibilidad con enrutamiento** se instala desde Agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes de aplicación de servidor/Message Queue Server.  
  
4.  Asegúrese de que está habilitado el acceso de red DTC en Agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la categoría de servidor de aplicaciones. Acceso de cliente de red DTC se habilitó en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo en un paso anterior.  
  
5.  Implementar el protocolo de capa de Sockets seguros (SSL) en la implementación, como se describe en [compatibilidad con capa de Sockets seguros (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md).  
  
6.  Instalar y configurar Windows SharePoint Services 3.0 SP1.  
  
7.  Instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] tal y como se describe en [instalar y configurar el Acelerador de BizTalk para SWIFT en los servidores front-end HTTP](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md).  
  
 Esta sección contiene:  
  
-   [Compatibilidad con capa de Sockets seguros (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)  
  
-   [Instalar y configurar servidores front-end HTTP de BizTalk](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)  
  
-   [Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores front-end HTTP](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-http-front-end-servers.md)