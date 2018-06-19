---
title: Características para los clientes de adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic ports
- adapters, features
- XML data streaming
- performance counters
- adapters, support for dynamic ports in BizTalk Server
- adapters, support for message versioning
- adapters, support for XML data streaming
- adapters, support for performance counters
- adapters, support for configuring adapters using binding properties
ms.assetid: 9003c2c1-931d-405e-9a58-660032195af7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6516ff99f599d02cdf27aa7c0c07752747749021
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217116"
---
# <a name="features-for-sap-adapter-clients"></a>Características para los clientes de adaptador SAP
Además de las características tratadas en todos los temas de [Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md), el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también proporciona las siguientes características que son útiles para los clientes de adaptador.  
  
-   **Compatibilidad para la configuración de adaptadores que usan propiedades de enlace**. Pueden configurar los clientes de adaptador el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] especificando ciertas propiedades de enlace. Por ejemplo, los clientes pueden configurar el adaptador para especificar el número máximo de conexiones de grupo de conexiones del adaptador especificando un valor para el **MaxConnectionsPerSystem** propiedad de enlace. Para obtener más información, consulte [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
-   **Compatibilidad con puertos dinámicos en BizTalk Server**. A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite un puerto dinámico que habilita el enrutamiento dinámico de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje. Para obtener más información, consulte [configurar puertos dinámicos](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md).
  
-   **Compatibilidad con versiones de mensaje**. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite mensajes de control de versiones para habilitar la compatibilidad con esquemas de mensaje diferente en versiones futuras de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [compatibilidad de versiones de mensaje](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md).  
  
    > [!NOTE]
    >  Esta característica no proporciona compatibilidad con versiones anteriores con las versiones anteriores del adaptador.  
  
-   **Compatibilidad con contadores de rendimiento**. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con los contadores de rendimiento basados en WCF para los clientes de adaptador. Para obtener más información sobre los contadores de rendimiento, consulte [utilizar contadores de rendimiento con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)