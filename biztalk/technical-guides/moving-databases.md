---
title: Mover bases de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a0d09a1-90a5-4a5d-a783-b979724e101b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15562fc1fb642a4766190dabe912e81b38bb1ea8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972421"
---
# <a name="moving-databases"></a><span data-ttu-id="e4bbf-102">Mover bases de datos</span><span class="sxs-lookup"><span data-stu-id="e4bbf-102">Moving Databases</span></span>
<span data-ttu-id="e4bbf-103">El método recomendado para mover [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos (excepto las bases de datos de supervisión de la actividad económica (BAM)) consiste en configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros como se describe en la sección [recuperación ante desastres](../technical-guides/disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="e4bbf-103">The recommended method for moving [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases (except for the Business Activity Monitoring (BAM) databases) is to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping as described in the section [Disaster Recovery](../technical-guides/disaster-recovery.md).</span></span> <span data-ttu-id="e4bbf-104">A excepción de las bases de datos usa BAM, todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos pueden realizar copias de seguridad utilizando la **Backup BizTalk Server** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="e4bbf-104">With the exception of the databases used by BAM, all of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases can be backed up by using the **Backup BizTalk Server**[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent job.</span></span> <span data-ttu-id="e4bbf-105">Para obtener más información acerca de este trabajo, consulte [cómo programar el trabajo de copia de seguridad de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154674) (<http://go.microsoft.com/fwlink/?LinkId=154674>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="e4bbf-105">For more information about this job, see [How to Schedule the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkId=154674) (<http://go.microsoft.com/fwlink/?LinkId=154674>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="e4bbf-106">Esta sección describe cómo mover las bases de datos relacionadas con BAM y cómo mover los restantes [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos sin configurar primero [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="e4bbf-106">This section describes how to move the BAM-related databases and how to move the remaining [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases without first configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping.</span></span> <span data-ttu-id="e4bbf-107">Este enfoque puede resultar útil cuando se actualiza el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos o en otros escenarios que no están relacionadas con la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="e4bbf-107">This approach may be useful when upgrading the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computers that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases or in other scenarios that are not related to disaster recovery.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4bbf-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e4bbf-108">In This Section</span></span>  
  
-   [<span data-ttu-id="e4bbf-109">Mover bases de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="e4bbf-109">Moving BAM Databases</span></span>](../technical-guides/moving-bam-databases.md)  
  
-   [<span data-ttu-id="e4bbf-110">Mover bases de datos que no son de BAM</span><span class="sxs-lookup"><span data-stu-id="e4bbf-110">Moving Non-BAM Databases</span></span>](../technical-guides/moving-non-bam-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="e4bbf-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4bbf-111">See Also</span></span>  
 [<span data-ttu-id="e4bbf-112">Administración de BizTalk Server2</span><span class="sxs-lookup"><span data-stu-id="e4bbf-112">Managing BizTalk Server2</span></span>](../technical-guides/managing-biztalk-server2.md)