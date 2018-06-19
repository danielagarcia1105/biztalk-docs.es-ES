---
title: Características para los clientes de adaptador SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f638154b-0a09-4f89-9c52-2a62fafec7dc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0d1df3a7d5c5748db4b0d3f365d80d84ff1f670
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222716"
---
# <a name="features-for-sql-adapter-clients"></a>Características para los clientes de adaptador SQL
Además de las características tratadas en todos los temas de [información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md), el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] también proporciona las siguientes características que son útiles para los clientes de adaptador:  
  
-   **Compatibilidad para la configuración de adaptadores que usan propiedades de enlace**. Pueden configurar los clientes de adaptador el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] especificando ciertas propiedades de enlace. Por ejemplo, los clientes pueden especificar el número máximo de conexiones permitido en un grupo de conexiones para una cadena de conexión concreto estableciendo la **MaxConnectionPoolSize** propiedad de enlace. Para obtener más información, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
-   **Compatibilidad con valores null para los parámetros de operación**. Los clientes de adaptador pueden proporcionar valores null para los parámetros de operación mediante el atributo "nillable" XSD.  
  
-   **Compatibilidad con puertos dinámicos en BizTalk**. A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite un puerto dinámico que habilita el enrutamiento dinámico de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje. Para obtener más información, consulte [configurar puertos dinámicos](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).  
  
-   **Compatibilidad con contadores de rendimiento**. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es compatible con los contadores de rendimiento basados en WCF para los clientes de adaptador. Para obtener más información sobre los contadores de rendimiento, consulte [utilizar contadores de rendimiento con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)