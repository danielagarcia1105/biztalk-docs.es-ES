---
title: "Paso 6: Configurar los servidores de orquestación de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acf5cb36908031f9256f25dd68435003b74d2633
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a>Paso 6: Configurar los servidores de orquestación de BizTalk Server
Esta sección proporciona instrucciones sobre cómo configurar los servidores de orquestación de BizTalk.  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a>Para configurar los servidores de orquestación de BizTalk  
  
1.  Habilitar el acceso de coordinador de transacciones distribuidas (DTC) de red mediante la selección de agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la categoría de servidor de aplicaciones. Acceso de cliente de red DTC se habilitó en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo en un paso anterior. Consulte los siguientes artículos de Knowledge Base en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] sitio Web de ayuda y soporte técnico para obtener información acerca de cómo solucionar problemas de DTC:  
  
    -   Cómo To Troubleshoot MS DTC Firewall Issues, ubicado en [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).  
  
    -   Cómo utilizar la herramienta DTCTester, ubicado en [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).  
  
    -   Si el DTC está detrás de un firewall, vea Configurar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Coordinador de transacciones distribuidas (DTC) para el trabajo a través de un Firewall, ubicado en [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).  
  
2.  Instalar requisitos previos de software adicional para el servidor BizTalk Server e instalar y configurar [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], tal y como se describe en [instalar y configurar BizTalk Server en los servidores de orquestación](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md).  
  
3.  Instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] tal y como se describe en instalar y [instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).  
  
 Esta sección contiene:  
  
-   [Instalar y configurar el servidor BizTalk Server en los servidores de orquestación](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de orquestación](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)