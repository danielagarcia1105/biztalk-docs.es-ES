---
title: Resolver instancias de actividad incompletas | Documentos de Microsoft
description: "Instancias de actividad BAM permanecen activas después de la copia de seguridad de la base de datos BAMPrimaryImport en BizTalk Server"
ms.custom: 
ms.date: 01/17/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8adbcb66-58ad-42c5-ba16-7dc07572099e
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 616ba096062da7ede8d78122e5a6faaca2befdc4
ms.sourcegitcommit: 20d33d8b74bf129a8d1a506ac4a1ad960184966d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2018
---
# <a name="resolve-incomplete-bam-activity-instances---biztalk-server"></a><span data-ttu-id="cf5bd-103">Resolver instancias incompletas de actividad BAM - servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="cf5bd-103">Resolve incomplete BAM activity instances - BizTalk Server</span></span>
<span data-ttu-id="cf5bd-104">BAM almacena datos de instancias de actividad incompletas en una clase especial *instancias activas* tabla en la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="cf5bd-104">BAM stores data for incomplete activity instances in a special *active instance* table in the BAMPrimaryImport database.</span></span>  
  
 <span data-ttu-id="cf5bd-105">Si algunos registros de instancia se inician antes de la última copia de seguridad de la base de datos de importación principal de BAM pero se completan después de realizar esa copia de seguridad, los registros de instancia se conservan en una tabla de instancias activas.</span><span class="sxs-lookup"><span data-stu-id="cf5bd-105">If some instance records were started before the last backup of the BAMPrimaryImport database but completed after the backup, those instance records remain in an active instance table.</span></span> <span data-ttu-id="cf5bd-106">Esto ocurre porque, después de restaurar la base de datos BAMPrimaryImport, se pierden los registros de finalización de estas instancias.</span><span class="sxs-lookup"><span data-stu-id="cf5bd-106">This is because after the BAMPrimaryImport database is restored, the completion records for these instances are lost.</span></span>  
  
 <span data-ttu-id="cf5bd-107">Aunque los registros de la tabla de instancias activas no impiden que SAE funcione correctamente, se recomienda marcarlos como "completados" y, seguidamente, moverlos a una ubicación externa a la tabla de instancias activas.</span><span class="sxs-lookup"><span data-stu-id="cf5bd-107">Although the records in the active instance table do not prevent BAM from functioning properly, we recommend that you mark these records as "completed," and then move them out of the active instance table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cf5bd-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cf5bd-108">Prerequisites</span></span>  
<span data-ttu-id="cf5bd-109">Inicie sesión como miembro del grupo Administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="cf5bd-109">Sign in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="create-a-list-of-incomplete-activityids"></a><span data-ttu-id="cf5bd-110">Crear una lista de elementos ActivityID incompletos</span><span class="sxs-lookup"><span data-stu-id="cf5bd-110">Create a list of incomplete ActivityIDs</span></span> 
  
1.  <span data-ttu-id="cf5bd-111">Ejecute la consulta siguiente en la base de datos BAMPrimaryImport:</span><span class="sxs-lookup"><span data-stu-id="cf5bd-111">Run the following query against the BAMPrimaryImport database:</span></span>  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  <span data-ttu-id="cf5bd-112">Si hay datos de sistemas externos que indican que, efectivamente, la instancia de actividad se ha completado, ejecute la siguiente consulta para completar manualmente la instancia:</span><span class="sxs-lookup"><span data-stu-id="cf5bd-112">If data from external systems indicates that the activity instance is in fact completed, run the following query to manually complete the instance:</span></span>  
  
    ```  
    begin transaction
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    commit transaction
    ```  
  
> [!NOTE]
>  <span data-ttu-id="cf5bd-113">Puede seguir el mismo proceso para completar una actividad de continuación si se reemplaza `ActivityID` con `ContinuationID`.</span><span class="sxs-lookup"><span data-stu-id="cf5bd-113">You can follow the same process to complete a continuation activity by replacing `ActivityID` with `ContinuationID`.</span></span>  
> 
>  <span data-ttu-id="cf5bd-114">Si el seguimiento principal tiene seguimientos de continuación activos, permanece activo hasta que éstos se completen.</span><span class="sxs-lookup"><span data-stu-id="cf5bd-114">If the main trace has any active continuation traces, it remains active until the continuation traces are completed.</span></span>  

## <a name="remove-incomplete-instances"></a><span data-ttu-id="cf5bd-115">Quitar instancias incompletas</span><span class="sxs-lookup"><span data-stu-id="cf5bd-115">Remove incomplete instances</span></span>
<span data-ttu-id="cf5bd-116">También puede quitar instancias de actividad incompletas de la base de datos BAMPrimaryImport mediante un script SQL personalizado.</span><span class="sxs-lookup"><span data-stu-id="cf5bd-116">You can also remove incomplete activity instances from the BAMPrimaryImport database using a custom SQL script.</span></span> <span data-ttu-id="cf5bd-117">Vea [quitar instancias de actividad incompletas](how-to-remove-incomplete-activity-instances.md) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cf5bd-117">See [Remove incomplete activity instances](how-to-remove-incomplete-activity-instances.md) for a sample.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf5bd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf5bd-118">See Also</span></span>  
 [<span data-ttu-id="cf5bd-119">Realizar una copia de seguridad y restauración de BAM</span><span class="sxs-lookup"><span data-stu-id="cf5bd-119">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)
