---
title: Conjuntos de copia de seguridad parciales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b9f15c0-4d31-4322-ac0a-8efdeed6f71e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9740cb0f45d6bb46c13a95e50e4717ef142b164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="partial-backup-sets"></a><span data-ttu-id="8079e-102">Conjuntos de copia de seguridad parciales</span><span class="sxs-lookup"><span data-stu-id="8079e-102">Partial Backup Sets</span></span>
<span data-ttu-id="8079e-103">Al hacer una copia de seguridad de las bases de datos en el sistema de origen, pueden producirse problemas que den como resultado un conjunto de copia de seguridad parcial.</span><span class="sxs-lookup"><span data-stu-id="8079e-103">When backing up the databases on the source system, problems may occur that result in a partial backup set.</span></span> <span data-ttu-id="8079e-104">Cuando esto ocurre, la tabla Master.dbo.bts_LogShippingHistory contendrá un 0 en la **SetComplete** columna para todos los registros en el conjunto.</span><span class="sxs-lookup"><span data-stu-id="8079e-104">When this occurs, the Master.dbo.bts_LogShippingHistory table will contain a 0 in the **SetComplete** column for all records in the set.</span></span>  
  
 <span data-ttu-id="8079e-105">No se puede restaurar estos conjuntos.</span><span class="sxs-lookup"><span data-stu-id="8079e-105">These sets cannot be restored.</span></span> <span data-ttu-id="8079e-106">Como resultado, la cadena de copia de seguridad de registros se interrumpe.</span><span class="sxs-lookup"><span data-stu-id="8079e-106">As a result the log backup set chain is broken.</span></span> <span data-ttu-id="8079e-107">Se debe omitir el conjunto, como el registro de todos los conjuntos de copia de seguridad después de él, hasta el siguiente conjunto de copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="8079e-107">The set must be ignored, as well as all log backup sets after it, up to the next full backup set.</span></span> <span data-ttu-id="8079e-108">El trabajo de restauración buscará automáticamente el siguiente conjunto de copia de seguridad completa válido.</span><span class="sxs-lookup"><span data-stu-id="8079e-108">The restore job will automatically look for the next valid full backup set.</span></span> <span data-ttu-id="8079e-109">Si no lo encuentra, se produce un error y restaura establezca para reparar el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="8079e-109">If it does not find one, it fails and restores that set in order to repair the destination environment.</span></span>  
  
 <span data-ttu-id="8079e-110">En la mayoría de los casos el sistema de origen detectará que un conjunto de copia de seguridad parcial se ha producido y generará automáticamente un conjunto de copia de seguridad completa la próxima vez que se ejecuta si se configura para ello.</span><span class="sxs-lookup"><span data-stu-id="8079e-110">In most cases the source system will detect that a partial backup set has occurred and will automatically produce a full backup set the next time it runs if it is configured to do so.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8079e-111">La causa más común de este problema es suficiente espacio en disco para los grupos de archivos del sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="8079e-111">The most common cause of this problem is insufficient disk space for the file groups on the destination system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8079e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8079e-112">See Also</span></span>  
 [<span data-ttu-id="8079e-113">Solución de problemas de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="8079e-113">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)