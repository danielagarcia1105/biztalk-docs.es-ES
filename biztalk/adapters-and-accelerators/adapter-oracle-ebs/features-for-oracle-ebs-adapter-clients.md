---
title: "Características para los clientes de adaptador de Oracle EBS | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50256fb7-5f0c-4b32-87e6-98f49da0b360
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2da086390fe049a5333dda40a35e19f46298dda1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="features-for-oracle-ebs-adapter-clients"></a>Características para los clientes de adaptador de Oracle EBS
Además de las características tratadas en todos los temas de [información general sobre el adaptador de BizTalk para Oracle E-Business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e), el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] también proporciona las siguientes características que son útiles para los clientes de adaptador:  
  
-   **Compatibilidad para la configuración de adaptadores que usan propiedades de enlace**. Pueden configurar los clientes de adaptador el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] especificando ciertas propiedades de enlace. Por ejemplo, los clientes pueden configurar el adaptador para usar la agrupación de conexiones ODP.NET estableciendo la **UseOracleConnectionPool** propiedad de enlace. Para obtener más información, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
-   **Compatibilidad con valores null para los parámetros de operación**. Los clientes de adaptador pueden proporcionar valores null para los parámetros de operación mediante el atributo "nil" en el XML de entrada.  
  
-   **Compatibilidad con puertos dinámicos en BizTalk**. A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite un puerto dinámico que habilita el enrutamiento dinámico de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje. Para obtener más información, consulte [configurar los puertos dinámicos en el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).  
  
## <a name="see-also"></a>Vea también  
[Comprender el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)