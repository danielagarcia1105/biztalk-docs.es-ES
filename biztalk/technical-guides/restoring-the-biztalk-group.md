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
ms.openlocfilehash: c12a1deff8fea6d769f138aa34bf6dab269a167f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-the-biztalk-group"></a><span data-ttu-id="32118-102">Restaurar el grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="32118-102">Restoring the BizTalk Group</span></span>
<span data-ttu-id="32118-103">El grupo de BizTalk está representado por el conjunto de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las bases de datos de Analysis Services, paquetes SSIS y trabajos del Agente SQL.</span><span class="sxs-lookup"><span data-stu-id="32118-103">The BizTalk group is represented by the set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases, SSIS packages, and SQL Agent Jobs.</span></span> <span data-ttu-id="32118-104">En esta sección se describe el proceso para restaurar el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="32118-104">This section describes the process for restoring the BizTalk group.</span></span>  
  
 <span data-ttu-id="32118-105">En caso de que se requiere un cambio en el sistema de destino (sitio de recuperación ante desastres), deben completar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="32118-105">In the event that a switchover to the destination system (disaster recovery site) is required, the following steps must be completed:</span></span>  
  
1.  <span data-ttu-id="32118-106">Restaurar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y bases de datos de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="32118-106">Restore [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and Analysis Services databases.</span></span>  
  
2.  <span data-ttu-id="32118-107">Restaurar [!INCLUDE[prague](../includes/prague-md.md)] en tiempo de ejecución servidores y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="32118-107">Restore [!INCLUDE[prague](../includes/prague-md.md)] runtime servers and applications.</span></span>  
  
 <span data-ttu-id="32118-108">En la realización de estos pasos, el grupo de BizTalk se ha establecido en el sitio de recuperación ante desastres, el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se pueden configurar servidores de tiempo de ejecución y las aplicaciones pueden implementarse en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="32118-108">Upon completion of these steps, the BizTalk group has been established at the disaster recovery site, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime servers can be configured, and the applications can be deployed into the BizTalk group.</span></span> <span data-ttu-id="32118-109">Los temas de esta sección tratan los detalles de este proceso.</span><span class="sxs-lookup"><span data-stu-id="32118-109">The topics in this section cover the details of this process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32118-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="32118-110">In This Section</span></span>  
  
-   [<span data-ttu-id="32118-111">Detener el proceso en el sistema de origen de la aplicación</span><span class="sxs-lookup"><span data-stu-id="32118-111">Stopping Application Processing on the Source System</span></span>](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [<span data-ttu-id="32118-112">Cómo restaurar las bases de datos en el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="32118-112">How to Restore Databases in the Backup BizTalk Server Job</span></span>](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [<span data-ttu-id="32118-113">Restaurar bases de datos que no se incluye en el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="32118-113">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)