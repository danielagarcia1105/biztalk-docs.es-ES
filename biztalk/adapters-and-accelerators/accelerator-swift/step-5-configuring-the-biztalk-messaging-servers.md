---
title: 'Paso 5: Configurar lo servidores de mensajería de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, BizTalk Messaging servers
- BizTalk Messaging servers, configuring
ms.assetid: 598d336d-b006-4d02-9249-e9d6d9b6b7b5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9baea2c567148ead98abf6b3aca3f5cad8258e60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980005"
---
# <a name="step-5-configuring-the-biztalk-messaging-servers"></a>Paso 5: Configurar lo servidores de mensajería de BizTalk
Esta sección proporciona instrucciones sobre cómo configurar los servidores de mensajería de BizTalk.  
  
### <a name="to-configure-the-biztalk-messaging-servers"></a>Para configurar los servidores de mensajería de BizTalk  
  
1. Habilitar el acceso de coordinador de transacciones distribuidas (DTC) de red seleccionando desde Agregar o quitar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componentes en la categoría de servidor de aplicaciones. Se ha habilitado el acceso de cliente de red DTC en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo en el paso anterior. Consulte los siguientes artículos de Knowledge Base en el sitio Web de soporte técnico y Microsoft Help para obtener información acerca de cómo solucionar problemas de DTC:  
  
   - Cómo To Troubleshoot MS DTC Firewall Issues, ubicado en [ http://go.microsoft.com/fwlink/?linkid=48870 ](http://go.microsoft.com/fwlink/?linkid=48870).  
  
   - Cómo utilizar la herramienta DTCTester, ubicado en [ http://go.microsoft.com/fwlink/?linkid=48871 ](http://go.microsoft.com/fwlink/?linkid=48871).  
  
   - Si el DTC está detrás de un firewall, consulte "Configuración de Microsoft distribuidas transacción coordinador (DTC) to trabajo Through a Firewall", ubicado en [ http://go.microsoft.com/fwlink/?linkid=48872 ](http://go.microsoft.com/fwlink/?linkid=48872).  
  
2. Configurar y comprobar el equilibrio de carga de red en el BizTalk reciben servidores como se describe en [paso 2: configurar NLB en los servidores](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md).  
  
3. Instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como se describe en [instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).  
  
   Esta sección contiene:  
  
-   [Instalación y configuración de BizTalk Server en el servidor de mensajería](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-messaging-server.md)  
  
-   [Instalación y configuración del Acelerador de BizTalk para SWIFT en servidores de mensajería](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)