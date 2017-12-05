---
title: Restaurar el grupo de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14a9af44-d6de-49c7-9600-21ece389727f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e8d1741d89e8326cc68906644cf34e71bfcc8e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="restoring-the-biztalk-group"></a><span data-ttu-id="86c8c-102">Restaurar el grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="86c8c-102">Restoring the BizTalk Group</span></span>
<span data-ttu-id="86c8c-103">El grupo de BizTalk está representado por el conjunto de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las bases de datos de Analysis Services, paquetes SSIS y trabajos del Agente SQL.</span><span class="sxs-lookup"><span data-stu-id="86c8c-103">The BizTalk group is represented by the set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases, SSIS packages, and SQL Agent Jobs.</span></span> <span data-ttu-id="86c8c-104">En esta sección se describe el proceso para restaurar el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="86c8c-104">This section describes the process for restoring the BizTalk group.</span></span>  
  
 <span data-ttu-id="86c8c-105">En caso de que se requiere un cambio en el sistema de destino (sitio de recuperación ante desastres), deben completar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="86c8c-105">In the event that a switchover to the destination system (disaster recovery site) is required, the following steps must be completed:</span></span>  
  
1.  <span data-ttu-id="86c8c-106">Restaurar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y bases de datos de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="86c8c-106">Restore [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and Analysis Services databases.</span></span>  
  
2.  <span data-ttu-id="86c8c-107">Restaurar las aplicaciones y servidores de BizTalk Server en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="86c8c-107">Restore BizTalk Server runtime servers and applications.</span></span>  
  
 <span data-ttu-id="86c8c-108">En la realización de estos pasos, el grupo de BizTalk se ha establecido en el sitio de recuperación ante desastres, el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se pueden configurar servidores de tiempo de ejecución y las aplicaciones pueden implementarse en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="86c8c-108">Upon completion of these steps, the BizTalk group has been established at the disaster recovery site, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime servers can be configured, and the applications can be deployed into the BizTalk group.</span></span> <span data-ttu-id="86c8c-109">Los temas de esta sección tratan los detalles de este proceso.</span><span class="sxs-lookup"><span data-stu-id="86c8c-109">The topics in this section cover the details of this process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="86c8c-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="86c8c-110">In This Section</span></span>  
  
-   [<span data-ttu-id="86c8c-111">Detener el procesamiento de aplicaciones en el sistema de origen</span><span class="sxs-lookup"><span data-stu-id="86c8c-111">Stopping Application Processing on the Source System</span></span>](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [<span data-ttu-id="86c8c-112">Cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="86c8c-112">How to Restore Databases in the Backup BizTalk Server Job</span></span>](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [<span data-ttu-id="86c8c-113">Restauración de bases de datos que no se incluyen en el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="86c8c-113">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)