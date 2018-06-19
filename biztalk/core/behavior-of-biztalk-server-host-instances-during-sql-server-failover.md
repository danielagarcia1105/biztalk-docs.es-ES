---
title: Comportamiento de las instancias de Host de BizTalk Server durante la conmutación por error SQL Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5642417-d27f-4539-a369-5fa11bec4a4f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f244ce0fe00fe05f73db5f43ec867254b7a61fb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231252"
---
# <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de host de BizTalk Server durante la conmutación por error de SQL Server
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]las bases de datos alojadas en una instancia en clúster de Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] están temporalmente no disponibles si la instancia en clúster de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] produce una conmutación por error. Esta sección documentan el comportamiento de las instancias de host asociadas a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cuando el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos no están disponibles.  
  
## <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de host de tipo En curso durante la conmutación por error de SQL Server  
 Si las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no están disponibles, se reciclará una instancia de tipo En curso de un host [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hasta que se restaure la conexión con [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Cuando la conexión con las bases de datos [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se restaura, el procesamiento de documentos se reanuda normalmente.  
  
## <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de host aisladas durante la conmutación por error de SQL Server  
 Si las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no están disponibles, la instancia aislada de un host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se pausará y se generará un error similar al siguiente en el registro de la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
```  
All receive locations are being temporarily disabled because either   
the MessageBox or Configuration database is not available.   
When these databases become available, the receive locations will be automatically enabled.  
```  
  
 Cuando la conexión con el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se restaura las bases de datos se escribe un mensaje informativo similar al siguiente en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] registro de aplicación y normalmente se reanuda el procesamiento de documentos:  
  
```  
All receive locations are being enabled because both the MessageBox and Configuration databases are back online.  
```  
  
## <a name="see-also"></a>Vea también  
 [Hosts](../core/hosts.md)