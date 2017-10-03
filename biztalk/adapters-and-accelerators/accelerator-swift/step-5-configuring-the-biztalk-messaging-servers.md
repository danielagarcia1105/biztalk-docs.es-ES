---
title: "Paso 5: Configurar lo servidores de mensajería de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, BizTalk Messaging servers
- BizTalk Messaging servers, configuring
ms.assetid: 598d336d-b006-4d02-9249-e9d6d9b6b7b5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e1aea1187417b77071f0821547869a5b84549c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-configuring-the-biztalk-messaging-servers"></a>Paso 5: Configurar lo servidores de mensajería de BizTalk
Esta sección proporciona instrucciones sobre cómo configurar los servidores de mensajería de BizTalk.  
  
### <a name="to-configure-the-biztalk-messaging-servers"></a>Para configurar los servidores de mensajería de BizTalk  
  
1.  Habilitar el acceso de coordinador de transacciones distribuidas (DTC) de red mediante la selección de agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la categoría de servidor de aplicaciones. Acceso de cliente de red DTC se habilitó en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo en un paso anterior. Consulte los siguientes artículos de Knowledge Base en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] sitio Web de ayuda y soporte técnico para obtener información acerca de cómo solucionar problemas de DTC:  
  
    -   Cómo To Troubleshoot MS DTC Firewall Issues, ubicado en [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).  
  
    -   Cómo utilizar la herramienta DTCTester, ubicado en [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).  
  
    -   Si el DTC está detrás de un firewall, vea "configurar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Coordinador de transacciones distribuidas (DTC) to Work Through un Firewall", que se encuentra en [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).  
  
2.  Configurar y comprobar el equilibrio de carga de red en el BizTalk reciben servidores como se describe en [paso 2: configurar NLB en los servidores](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md).  
  
3.  Instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] tal y como se describe en [instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).  
  
 Esta sección contiene:  
  
-   [Instalar y configurar el servidor BizTalk Server en el servidor de mensajería](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-messaging-server.md)  
  
-   [Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)