---
title: Componentes del adaptador de MQSeries | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, BizTalk component
- MQSeries adapters, components
- MQSeries components, MQSeries adapters
- BizTalk components
- MQSeries adapters, MQSeries component
ms.assetid: 923974cb-371d-47dc-99a7-2f7b93f60ada
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58726b6528af55da6554ff740208b3e03bdc806e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="components-of-the-mqseries-adapter"></a>Componentes del adaptador de MQSeries
El adaptador de MQSeries utiliza dos componentes para facilitar la transferencia de documentos entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y MQSeries Server para Windows.  
  
-   **Componente de BizTalk.** Instale este componente en el mismo equipo que Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Este componente se comunica con BizTalk Server.  
  
-   **Componente de MQSeries.** Instale este componente en MQSeries Server para Windows. MQSeries Server para Windows se ejecuta en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]. Este componente (conocido como MQSAgent) se comunica con IBM MQSeries Server.  
  
    > [!NOTE]
    >  El componente MQSAgent del adaptador de MQSeries es compatible si se ejecuta con MQSeries Server 5.3, CSD10 o posterior, y WebSphere MQSeries Server 6.0 en Windows.  
  
 La siguiente ilustración muestra un uso típico del adaptador.  
  
 ![Documentar el flujo entre MQSeries Server y BizTalk](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")  
  
 El adaptador de MQSeries es una solución de conectividad que permite usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una empresa con MQSeries como estándar de mensajería. El desarrollo de esta solución estuvo motivado en parte por los siguientes aspectos:  
  
-   Clientes que solicitaban una instalación y una configuración sencillas, y una solución de conectividad de MQSeries  
  
-   Admitir tamaños de mensaje de hasta 100 MB  
  
-   Proporcionar compatibilidad con MQSeries  
  
-   Proporcionar una solución de conectividad Plug and Play para mensajes de MQSeries a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
 El adaptador de MQSeries es una adición clave al conjunto de servicios de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que proporcionan una serie de agentes de escucha para varios estándares de protocolo de comunicaciones. Los agentes de escucha adjuntan un protocolo, por ejemplo HTTP, FTP o MQSeries, a una relación comercial de integración de aplicaciones empresariales (EAI), de negocio a negocio o de aplicación a aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de MQSeries](../core/mqseries-adapter-architecture.md)   
 [¿Qué es el adaptador de MQSeries?](../core/what-is-the-mqseries-adapter.md)