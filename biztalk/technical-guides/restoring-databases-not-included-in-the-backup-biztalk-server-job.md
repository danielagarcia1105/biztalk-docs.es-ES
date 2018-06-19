---
title: Restaurar bases de datos no incluidos en el trabajo de copia de seguridad de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7141980-d4a6-4409-be9b-c94a7f733376
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3277886207e04a30fec8bb61f29b5fe8c5ec3545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302124"
---
# <a name="restoring-databases-not-included-in-the-backup-biztalk-server-job"></a><span data-ttu-id="8768d-102">Restaurar bases de datos que no se incluye en el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8768d-102">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>
<span data-ttu-id="8768d-103">En esta sección se describe cómo restaurar las bases de datos que forman parte de la solución general de BizTalk, pero no están respaldados por el trabajo de copia de seguridad de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8768d-103">This section describes how to restore databases that are part of the overall BizTalk solution but are not backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="8768d-104">Se copiarán todas las bases de datos que forman parte de una solución de BizTalk con el trabajo de copia de seguridad de BizTalk Server excepto los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8768d-104">All databases that are part of a BizTalk solution will be backed up by using the Backup BizTalk Server job except for the following:</span></span>  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]<span data-ttu-id="8768d-105">Bases de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8768d-105"> Analysis Services databases</span></span>  
  
-   <span data-ttu-id="8768d-106">Bases de datos BAM cuando BAM está habilitada y configurada mediante BM.exe</span><span class="sxs-lookup"><span data-stu-id="8768d-106">BAM databases when BAM is enabled and configured using BM.exe</span></span>  
  
 <span data-ttu-id="8768d-107">Esta sección también describe cómo actualizar referencias de base de datos después de restaurar las bases de datos enumerados anteriormente e incluye información acerca de cómo resolver instancias incompletas de actividad BAM.</span><span class="sxs-lookup"><span data-stu-id="8768d-107">This section also describes how to update database references after restoring the databases listed above and includes information about resolving incomplete BAM activity instances.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8768d-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8768d-108">In This Section</span></span>  
  
-   [<span data-ttu-id="8768d-109">Restaurar los servicios de análisis y compatibilidad con bases de datos</span><span class="sxs-lookup"><span data-stu-id="8768d-109">Restoring Analysis Services and Supporting Databases</span></span>](../technical-guides/restoring-analysis-services-and-supporting-databases.md)  
  
-   [<span data-ttu-id="8768d-110">Actualizar referencias de base de datos</span><span class="sxs-lookup"><span data-stu-id="8768d-110">Updating Database References</span></span>](../technical-guides/updating-database-references.md)  
  
-   [<span data-ttu-id="8768d-111">Cómo resolver instancias de actividad BAM incompleta</span><span class="sxs-lookup"><span data-stu-id="8768d-111">How to Resolve Incomplete BAM Activity Instances</span></span>](../technical-guides/how-to-resolve-incomplete-bam-activity-instances.md)