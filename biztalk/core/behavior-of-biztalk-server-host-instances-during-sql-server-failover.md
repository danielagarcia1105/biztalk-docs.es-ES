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
# <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a><span data-ttu-id="5a5a3-102">Comportamiento de las instancias de host de BizTalk Server durante la conmutación por error de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a5a3-102">Behavior of BizTalk Server Host Instances during SQL Server Failover</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5a5a3-103">las bases de datos alojadas en una instancia en clúster de Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] están temporalmente no disponibles si la instancia en clúster de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] produce una conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-103"> databases housed on a clustered instance of Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are temporarily unavailable if the clustered instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] experiences a failover.</span></span> <span data-ttu-id="5a5a3-104">Esta sección documentan el comportamiento de las instancias de host asociadas a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cuando el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-104">This section documents the behavior of the host instances associated with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable.</span></span>  
  
## <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a><span data-ttu-id="5a5a3-105">Comportamiento de las instancias de host de tipo En curso durante la conmutación por error de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a5a3-105">Behavior of In-Process Host Instances during SQL Server Failover</span></span>  
 <span data-ttu-id="5a5a3-106">Si las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no están disponibles, se reciclará una instancia de tipo En curso de un host [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hasta que se restaure la conexión con [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a5a3-106">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable, then an in-process instance of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host will be recycled until the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is restored.</span></span> <span data-ttu-id="5a5a3-107">Cuando la conexión con las bases de datos [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se restaura, el procesamiento de documentos se reanuda normalmente.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-107">Once the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases is restored, document processing resumes normally.</span></span>  
  
## <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a><span data-ttu-id="5a5a3-108">Comportamiento de las instancias de host aisladas durante la conmutación por error de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a5a3-108">Behavior of Isolated Host Instances During SQL Server Failover</span></span>  
 <span data-ttu-id="5a5a3-109">Si las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no están disponibles, la instancia aislada de un host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se pausará y se generará un error similar al siguiente en el registro de la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5a5a3-109">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable, then an isolated instance of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host will pause and an error similar to the following will be generated in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log:</span></span>  
  
```  
All receive locations are being temporarily disabled because either   
the MessageBox or Configuration database is not available.   
When these databases become available, the receive locations will be automatically enabled.  
```  
  
 <span data-ttu-id="5a5a3-110">Cuando la conexión con el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se restaura las bases de datos se escribe un mensaje informativo similar al siguiente en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] registro de aplicación y normalmente se reanuda el procesamiento de documentos:</span><span class="sxs-lookup"><span data-stu-id="5a5a3-110">Once the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases is restored an informational message similar to the following is written to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log and document processing resumes normally:</span></span>  
  
```  
All receive locations are being enabled because both the MessageBox and Configuration databases are back online.  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a5a3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a5a3-111">See Also</span></span>  
 [<span data-ttu-id="5a5a3-112">Hosts</span><span class="sxs-lookup"><span data-stu-id="5a5a3-112">Hosts</span></span>](../core/hosts.md)