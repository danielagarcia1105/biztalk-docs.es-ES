---
title: 'Paso 7: Configurar los servidores front-end HTTP de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, HTTP servers
- HTTP server, configuring
ms.assetid: 6b7e0b48-bb20-42f4-84a5-092ff3a02741
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b6429ba6c753bac16874fd6fa81e13e91927b58
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989189"
---
# <a name="step-7-configuring-the-biztalk-http-front-end-servers"></a>Paso 7: Configurar los servidores front-end HTTP de BizTalk
Esta sección proporciona instrucciones sobre cómo configurar los servidores Web de su [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] implementación.  
  
> [!NOTE]
>  En la implementación de equipo único, este equipo es el mismo equipo que el que realiza la mensajería y procesamiento.  
  
### <a name="to-configure-the-biztalk-http-front-end-servers"></a>Para configurar los servidores front-end HTTP de BizTalk  
  
1. Instalar Internet Information Services (IIS) y ASP.NET.  
  
2. Abra el Administrador de IIS y seleccione **extensiones de servicio Web**. Asegúrese de que la versión 1.1 de ASP.NET y ASP.NET 2.0 se establecen en **permitido**.  
  
3. Asegúrese de que el **Message Queue Server** service (MSMQ) con **compatibilidad con enrutamiento** se instala desde Agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la aplicación de servidor/Message Queue Server.  
  
4. Asegúrese de que está habilitado el acceso de red DTC en Agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la categoría de servidor de aplicaciones. Se ha habilitado el acceso de cliente de red DTC en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo en el paso anterior.  
  
5. Implementar el protocolo de capa de Sockets seguros (SSL) en la implementación, como se describe en [compatibilidad con capa de Sockets seguros (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md).  
  
6. Instalar y configurar Windows SharePoint Services 3.0 SP1.  
  
7. Instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como se describe en [instalar y configurar el Acelerador de BizTalk para SWIFT en los servidores front-end HTTP](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md).  
  
   Esta sección contiene:  
  
-   [Admitir la capa de sockets seguros (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)  
  
-   [Instalación y configuración de servidores front-end HTTP de BizTalk](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)  
  
-   [Instalación y configuración del Acelerador de BizTalk para SWIFT en los servidores front-end HTTP](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-http-front-end-servers.md)