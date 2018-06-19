---
title: Características para los clientes de adaptador de base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data streaming, support for
- binding properties
- adapter, features
- adapters, configuring
- message versioning, support for
- XML data streaming
- performance counters, support for
- dynamic ports in BizTalk, support for
- data streaming
ms.assetid: 63b52573-80a5-4206-95c3-478b86718fee
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b120c948ef3d9821af0a79e91fd718e3a1f33137
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214324"
---
# <a name="features-for-oracle-database-adapter-clients"></a>Características para los clientes de adaptador de base de datos de Oracle
Además de las características tratadas en todos los temas de [información general del adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md), el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] también proporciona las siguientes características que son útiles para los clientes de adaptador:  
  
-   **Compatibilidad para la configuración de adaptadores que usan propiedades de enlace**. Pueden configurar los clientes de adaptador el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] especificando ciertas propiedades de enlace. Por ejemplo, los clientes pueden configurar el adaptador para usar la agrupación de conexiones ODP.NET estableciendo la **UseOracleConnectionPool** propiedad de enlace. Para obtener más información, consulte [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
-   **Compatibilidad con valores null para los parámetros de operación**. Los clientes de adaptador pueden proporcionar valores null para los parámetros de operación mediante el atributo "nil" en el XML de entrada.  
  
-   **Compatibilidad con puertos dinámicos en BizTalk**. A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite un puerto dinámico que habilita el enrutamiento dinámico de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje. Para obtener más información, consulte [configurar puertos dinámicos](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md).  
  
-   **Compatibilidad con contadores de rendimiento**. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con los contadores de rendimiento basados en WCF para los clientes de adaptador. Para obtener más información sobre los contadores de rendimiento, consulte [contadores de rendimiento](../../core/performance-counters.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)