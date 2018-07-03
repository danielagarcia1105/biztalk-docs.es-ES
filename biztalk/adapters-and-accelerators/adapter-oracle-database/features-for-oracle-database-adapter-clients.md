---
title: Características para los clientes del adaptador de base de datos de Oracle | Microsoft Docs
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
ms.openlocfilehash: ce283c3fd63f72d67e31806e86bf9caa08555dd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976181"
---
# <a name="features-for-oracle-database-adapter-clients"></a>Características para los clientes del adaptador de base de datos de Oracle
Además de las características se tratan en los temas de [información general del adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md), el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] también proporciona las siguientes características que son útiles para los clientes del adaptador:  
  
- **Compatibilidad con la configuración de los adaptadores que usan propiedades de enlace**. Pueden configurar los clientes del adaptador el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] especificando ciertas propiedades de enlace. Por ejemplo, los clientes pueden configurar el adaptador para usar la agrupación de conexiones ODP.NET estableciendo el **UseOracleConnectionPool** enlaza la propiedad. Para obtener más información, consulte [configurar las propiedades de enlace para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
- **Compatibilidad con valores null para los parámetros de operación**. Los clientes del adaptador pueden proporcionar valores nulos para parámetros de operación mediante el atributo "nil" en el XML de entrada.  
  
- **Compatibilidad con puertos dinámicos en BizTalk**. A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con un puerto dinámico que permite el enrutamiento dinámico de los mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje. Para obtener más información, consulte [configurar puertos dinámicos](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md).  
  
- **Compatibilidad con contadores de rendimiento**. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con los contadores de rendimiento basados en WCF para su uso por los clientes del adaptador. Para obtener más información sobre los contadores de rendimiento, consulte [los contadores de rendimiento](../../core/performance-counters.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)