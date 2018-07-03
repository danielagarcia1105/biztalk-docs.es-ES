---
title: Características para los clientes del adaptador de Oracle EBS | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50256fb7-5f0c-4b32-87e6-98f49da0b360
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 974f75eaa2416ae11572a1b29eb682d6bc7c0172
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968885"
---
# <a name="features-for-oracle-ebs-adapter-clients"></a>Características para los clientes del adaptador de Oracle EBS
Además de las características se tratan en los temas de [información general sobre el adaptador de BizTalk para Oracle E-Business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e), el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] también proporciona las siguientes características que son útiles para los clientes del adaptador:  
  
- **Compatibilidad con la configuración de los adaptadores que usan propiedades de enlace**. Pueden configurar los clientes del adaptador el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] especificando ciertas propiedades de enlace. Por ejemplo, los clientes pueden configurar el adaptador para usar la agrupación de conexiones ODP.NET estableciendo el **UseOracleConnectionPool** enlaza la propiedad. Para obtener más información, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
- **Compatibilidad con valores null para los parámetros de operación**. Los clientes del adaptador pueden proporcionar valores nulos para parámetros de operación mediante el atributo "nil" en el XML de entrada.  
  
- **Compatibilidad con puertos dinámicos en BizTalk**. A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con un puerto dinámico que permite el enrutamiento dinámico de los mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje. Para obtener más información, consulte [configurar los puertos dinámicos en el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).  
  
## <a name="see-also"></a>Vea también  
[El adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)