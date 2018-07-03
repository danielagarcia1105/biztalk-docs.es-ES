---
title: Restaurar bases de datos no incluidos en el trabajo de copia de seguridad de BizTalk Server | Microsoft Docs
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
ms.openlocfilehash: b24b0815c5948bac86dc3c614d05eb87d0684bdb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999253"
---
# <a name="restoring-databases-not-included-in-the-backup-biztalk-server-job"></a><span data-ttu-id="9bd05-102">Restaurar bases de datos que no se incluye en el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9bd05-102">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>
<span data-ttu-id="9bd05-103">En esta sección se describe cómo restaurar las bases de datos que forman parte de la solución de BizTalk general pero que no estén respaldados por el trabajo de copia de seguridad de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9bd05-103">This section describes how to restore databases that are part of the overall BizTalk solution but are not backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="9bd05-104">Todas las bases de datos que forman parte de una solución de BizTalk se hará copia usando el trabajo de copia de seguridad de BizTalk Server, excepto los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9bd05-104">All databases that are part of a BizTalk solution will be backed up by using the Backup BizTalk Server job except for the following:</span></span>  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]<span data-ttu-id="9bd05-105"> Bases de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9bd05-105"> Analysis Services databases</span></span>  
  
- <span data-ttu-id="9bd05-106">Bases de datos BAM cuando BAM está habilitada y configurada mediante BM.exe</span><span class="sxs-lookup"><span data-stu-id="9bd05-106">BAM databases when BAM is enabled and configured using BM.exe</span></span>  
  
  <span data-ttu-id="9bd05-107">En esta sección también describe cómo actualizar referencias de base de datos después de restaurar las bases de datos enumerados anteriormente y se incluye información acerca de cómo resolver instancias de actividad incompletas de BAM.</span><span class="sxs-lookup"><span data-stu-id="9bd05-107">This section also describes how to update database references after restoring the databases listed above and includes information about resolving incomplete BAM activity instances.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9bd05-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9bd05-108">In This Section</span></span>  
  
-   [<span data-ttu-id="9bd05-109">Restauración de Analysis Services y bases de datos auxiliares</span><span class="sxs-lookup"><span data-stu-id="9bd05-109">Restoring Analysis Services and Supporting Databases</span></span>](../technical-guides/restoring-analysis-services-and-supporting-databases.md)  
  
-   [<span data-ttu-id="9bd05-110">Actualización de referencias de base de datos</span><span class="sxs-lookup"><span data-stu-id="9bd05-110">Updating Database References</span></span>](../technical-guides/updating-database-references.md)  
  
-   [<span data-ttu-id="9bd05-111">Cómo resolver instancias de actividad incompletas de BAM</span><span class="sxs-lookup"><span data-stu-id="9bd05-111">How to Resolve Incomplete BAM Activity Instances</span></span>](../technical-guides/how-to-resolve-incomplete-bam-activity-instances.md)