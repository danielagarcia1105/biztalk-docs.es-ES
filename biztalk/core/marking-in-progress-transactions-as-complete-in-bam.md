---
title: Marcar transacciones en progreso como completadas en SAE | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, data recovery
- data recovery, BAM
- BAM, data loss
- data loss, BAM
ms.assetid: 8f734953-483a-481a-9ded-b48923859199
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 508001fcc1023acfd54b7d28bea7f246cb6a1a2d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262372"
---
# <a name="marking-in-progress-transactions-as-complete-in-bam"></a><span data-ttu-id="6019e-102">Marcar transacciones en progreso como completadas en SAE</span><span class="sxs-lookup"><span data-stu-id="6019e-102">Marking In-Progress Transactions as Complete in BAM</span></span>
<span data-ttu-id="6019e-103">Supervisión de la actividad económica (SAE) conserva datos de instancias de seguimiento sin completar en una tabla especial de instancias activas.</span><span class="sxs-lookup"><span data-stu-id="6019e-103">Business Activity Monitoring (BAM) keeps data for incomplete trace instances in a special active instance table.</span></span> <span data-ttu-id="6019e-104">Si algunos registros de instancia se inician antes de la última copia de seguridad pero se completan después de realizar esta última, los registros se conservan en una tabla de instancias activas.</span><span class="sxs-lookup"><span data-stu-id="6019e-104">If some instance records were started before the last backup but completed after the backup, those records will remain in the active instance table.</span></span> <span data-ttu-id="6019e-105">Aunque esto no impide que funcione el sistema, puede marcar estos registros de forma manual como completados para que puedan moverse a una ubicación externa a la tabla de instancias activas.</span><span class="sxs-lookup"><span data-stu-id="6019e-105">Although this does not prevent the system from functioning, you can manually mark these records as completed so that they can be moved out of the active instance table.</span></span>  
  
 <span data-ttu-id="6019e-106">Se puede determinar una lista de elementos ActivityID incompletos para una actividad dada efectuando la siguiente consulta en la base de datos de importación principal de SAE:</span><span class="sxs-lookup"><span data-stu-id="6019e-106">A list of incomplete ActivityIDs for a given activity can be determined by issuing the following query against the BAM Primary Import database:</span></span>  
  
```  
Select ActivityID from bam_<ActivityName> where IsComplete = 0  
```  
  
 <span data-ttu-id="6019e-107">Si hay datos de sistemas externos que indican que la instancia de actividad se ha completado, puede utilizar la siguiente consulta para completar manualmente la instancia:</span><span class="sxs-lookup"><span data-stu-id="6019e-107">If data from external systems indicates that the activity instance is complete, you can use the following query to manually complete the instance:</span></span>  
  
```  
exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
```  
  
## <a name="see-also"></a><span data-ttu-id="6019e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="6019e-108">See Also</span></span>  
 [<span data-ttu-id="6019e-109">Resolver la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="6019e-109">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)