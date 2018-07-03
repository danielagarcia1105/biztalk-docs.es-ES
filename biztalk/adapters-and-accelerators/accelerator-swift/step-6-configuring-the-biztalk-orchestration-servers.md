---
title: 'Paso 6: Configuración de los servidores de orquestación de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51ca589433d945dfdc5acac0602151b9f7cf6374
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991725"
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a>Paso 6: Configuración de los servidores de orquestación de BizTalk
Esta sección proporciona instrucciones sobre cómo configurar los servidores de orquestación de BizTalk.  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a>Para configurar los servidores de orquestación de BizTalk  
  
1. Habilitar el acceso de coordinador de transacciones distribuidas (DTC) de red seleccionando desde Agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la categoría de servidor de aplicaciones. Se ha habilitado el acceso de cliente de red DTC en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo en el paso anterior. Consulte los siguientes artículos de Knowledge Base en el sitio Web de soporte técnico y Microsoft Help para obtener información acerca de cómo solucionar problemas de DTC:  
  
   - Cómo To Troubleshoot MS DTC Firewall Issues, ubicado en [ http://go.microsoft.com/fwlink/?linkid=48870 ](http://go.microsoft.com/fwlink/?linkid=48870).  
  
   - Cómo utilizar la herramienta DTCTester, ubicado en [ http://go.microsoft.com/fwlink/?linkid=48871 ](http://go.microsoft.com/fwlink/?linkid=48871).  
  
   - Si DTC está detrás de un firewall, consulte Configurar Microsoft distribuidas Coordinador de transacciones (DTC) para el trabajo a través de un Firewall, ubicado en [ http://go.microsoft.com/fwlink/?linkid=48872 ](http://go.microsoft.com/fwlink/?linkid=48872).  
  
2. Instalar requisitos previos de software adicional para BizTalk Server e instalar y configurar BizTalk Server, como se describe en [instalar y configurar BizTalk Server en los servidores de orquestación](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md).  
  
3. Instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como se describe en la instalación y [instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).  
  
   Esta sección contiene:  
  
-   [Instalación y configuración de BizTalk Server en los servidores de orquestación](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [Instalación y configuración del Acelerador de BizTalk para SWIFT en los servidores de orquestación](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)