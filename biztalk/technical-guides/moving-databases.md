---
title: Mover bases de datos | Documentos de Microsoft
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
ms.openlocfilehash: f5dd25f898890225300f8962e581a38912f36351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299036"
---
# <a name="moving-databases"></a><span data-ttu-id="8dfec-102">Mover bases de datos</span><span class="sxs-lookup"><span data-stu-id="8dfec-102">Moving Databases</span></span>
<span data-ttu-id="8dfec-103">El método recomendado para mover [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos (excepto las bases de datos de supervisión de la actividad económica (BAM)) consiste en configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros como se describe en la sección [recuperación ante desastres](../technical-guides/disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="8dfec-103">The recommended method for moving [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases (except for the Business Activity Monitoring (BAM) databases) is to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping as described in the section [Disaster Recovery](../technical-guides/disaster-recovery.md).</span></span> <span data-ttu-id="8dfec-104">Con la excepción de las bases de datos usa BAM, todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos pueden realizar copias de seguridad utilizando la **copia de seguridad de BizTalk Server** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="8dfec-104">With the exception of the databases used by BAM, all of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases can be backed up by using the **Backup BizTalk Server**[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent job.</span></span> <span data-ttu-id="8dfec-105">Para obtener más información acerca de este trabajo, consulte [cómo programar el trabajo de copia de seguridad de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154674) (http://go.microsoft.com/fwlink/?LinkId=154674) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="8dfec-105">For more information about this job, see [How to Schedule the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkId=154674) (http://go.microsoft.com/fwlink/?LinkId=154674) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="8dfec-106">Esta sección describe cómo mover las bases de datos relacionadas con BAM y cómo mover los restantes [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos sin configurar primero [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="8dfec-106">This section describes how to move the BAM-related databases and how to move the remaining [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases without first configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping.</span></span> <span data-ttu-id="8dfec-107">Este enfoque puede resultar útil cuando se actualiza el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos o en otros escenarios que no están relacionadas con la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="8dfec-107">This approach may be useful when upgrading the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computers that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases or in other scenarios that are not related to disaster recovery.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8dfec-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8dfec-108">In This Section</span></span>  
  
-   [<span data-ttu-id="8dfec-109">Mover bases de datos BAM</span><span class="sxs-lookup"><span data-stu-id="8dfec-109">Moving BAM Databases</span></span>](../technical-guides/moving-bam-databases.md)  
  
-   [<span data-ttu-id="8dfec-110">Mover bases de datos de BAM no</span><span class="sxs-lookup"><span data-stu-id="8dfec-110">Moving Non-BAM Databases</span></span>](../technical-guides/moving-non-bam-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="8dfec-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dfec-111">See Also</span></span>  
 [<span data-ttu-id="8dfec-112">Administración de BizTalk Server2</span><span class="sxs-lookup"><span data-stu-id="8dfec-112">Managing BizTalk Server2</span></span>](../technical-guides/managing-biztalk-server2.md)