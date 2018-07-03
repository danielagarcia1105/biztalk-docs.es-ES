---
title: Características para los clientes del adaptador SQL | Microsoft Docs
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
ms.openlocfilehash: e2bcf55950995d5d9b64f0c0e1cca55ad628f4e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977101"
---
# <a name="features-for-sql-adapter-clients"></a>Características para los clientes del adaptador SQL
Además de las características se tratan en los temas de [información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md), el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] también proporciona las siguientes características que son útiles para los clientes del adaptador:  
  
- **Compatibilidad con la configuración de los adaptadores que usan propiedades de enlace**. Pueden configurar los clientes del adaptador el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] especificando ciertas propiedades de enlace. Por ejemplo, los clientes pueden especificar el número máximo de conexiones permitido en un grupo de conexiones para una cadena de conexión concreto estableciendo la **MaxConnectionPoolSize** enlaza la propiedad. Para obtener más información, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
- **Compatibilidad con valores null para los parámetros de operación**. Los clientes del adaptador pueden proporcionar valores nulos para parámetros de operación mediante el atributo "nillable" XSD.  
  
- **Compatibilidad con puertos dinámicos en BizTalk**. A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es compatible con un puerto dinámico que permite el enrutamiento dinámico de los mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje. Para obtener más información, consulte [configurar puertos dinámicos](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).  
  
- **Compatibilidad con contadores de rendimiento**. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es compatible con los contadores de rendimiento basados en WCF para su uso por los clientes del adaptador. Para obtener más información sobre los contadores de rendimiento, consulte [usar contadores de rendimiento con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)