---
title: "Cómo resolver instancias de actividad incompletas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- instances, incomplete [BAM]
- restoring, BAM
- Primary Import database [BAM], incomplete instances
- restoring [BAM], Primary Import database
- Primary Import database [BAM], restoring
- BAM, restoring
ms.assetid: 8adbcb66-58ad-42c5-ba16-7dc07572099e
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81df9ee8b004a2dbd4a672eecb4f34894421a432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-incomplete-activity-instances"></a><span data-ttu-id="831a8-102">Cómo resolver instancias de actividad incompletas</span><span class="sxs-lookup"><span data-stu-id="831a8-102">How to Resolve Incomplete Activity Instances</span></span>
<span data-ttu-id="831a8-103">BAM almacena datos de instancias de actividad incompletas en una clase especial *instancias activas* tabla en la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="831a8-103">BAM stores data for incomplete activity instances in a special *active instance* table in the BAMPrimaryImport database.</span></span>  
  
 <span data-ttu-id="831a8-104">Si algunos registros de instancia se inician antes de la última copia de seguridad de la base de datos de importación principal de BAM pero se completan después de realizar esa copia de seguridad, los registros de instancia se conservan en una tabla de instancias activas.</span><span class="sxs-lookup"><span data-stu-id="831a8-104">If some instance records were started before the last backup of the BAMPrimaryImport database but completed after the backup, those instance records remain in an active instance table.</span></span> <span data-ttu-id="831a8-105">Esto ocurre porque, después de restaurar la base de datos BAMPrimaryImport, se pierden los registros de finalización de estas instancias.</span><span class="sxs-lookup"><span data-stu-id="831a8-105">This is because after the BAMPrimaryImport database is restored, the completion records for these instances are lost.</span></span>  
  
 <span data-ttu-id="831a8-106">Aunque los registros de la tabla de instancias activas no impiden que SAE funcione correctamente, se recomienda marcarlos como "completados" y, seguidamente, moverlos a una ubicación externa a la tabla de instancias activas.</span><span class="sxs-lookup"><span data-stu-id="831a8-106">Although the records in the active instance table do not prevent BAM from functioning properly, we recommend that you mark these records as "completed," and then move them out of the active instance table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="831a8-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="831a8-107">Prerequisites</span></span>  
 <span data-ttu-id="831a8-108">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="831a8-108">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-generate-a-list-of-incomplete-activityids-for-an-activity"></a><span data-ttu-id="831a8-109">Para generar una lista de elementos ActivityID incompletos para una actividad</span><span class="sxs-lookup"><span data-stu-id="831a8-109">To generate a list of incomplete ActivityIDs for an activity</span></span>  
  
1.  <span data-ttu-id="831a8-110">Ejecute la consulta siguiente en la base de datos BAMPrimaryImport:</span><span class="sxs-lookup"><span data-stu-id="831a8-110">Run the following query against the BAMPrimaryImport database:</span></span>  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  <span data-ttu-id="831a8-111">Si hay datos de sistemas externos que indican que, efectivamente, la instancia de actividad se ha completado, ejecute la siguiente consulta para completar manualmente la instancia:</span><span class="sxs-lookup"><span data-stu-id="831a8-111">If data from external systems indicates that the activity instance is in fact completed, run the following query to manually complete the instance:</span></span>  
  
    ```  
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="831a8-112">Puede seguir el mismo proceso para completar una actividad de continuación mediante la sustitución de ActivityID con ContinuationID.</span><span class="sxs-lookup"><span data-stu-id="831a8-112">You can follow the same process to complete a continuation activity by replacing ActivityID with ContinuationID.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="831a8-113">Si el seguimiento principal tiene seguimientos de continuación activos, permanece activo hasta que éstos se completen.</span><span class="sxs-lookup"><span data-stu-id="831a8-113">If the main trace has any active continuation traces, it remains active until the continuation traces are completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="831a8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="831a8-114">See Also</span></span>  
 [<span data-ttu-id="831a8-115">Copia de seguridad y restauración de BAM</span><span class="sxs-lookup"><span data-stu-id="831a8-115">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)