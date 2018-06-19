---
title: Actualizar referencias al nombre de base de datos de archivo BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eed328e0-2826-4acb-952d-4a3a2844689e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16a04471e9f42744e4247f4202506839d2ade937
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302196"
---
# <a name="update-references-to-the-bam-archive-database-name"></a><span data-ttu-id="3b7fc-102">Actualizar referencias al nombre de base de datos de archivo BAM</span><span class="sxs-lookup"><span data-stu-id="3b7fc-102">Update References to the BAM Archive Database Name</span></span>
<span data-ttu-id="3b7fc-103">Si ha realizado una copia de seguridad de las bases de datos de archivo de BAM, si se produce un error de datos o del sistema podrá restaurar dicha copia a otro equipo, y puede cambiar el nombre de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3b7fc-103">If you backed up your BAM Archive databases, in the event of a system or data failure you can restore that backup to a different computer, and you can rename the backup.</span></span>  
  
 <span data-ttu-id="3b7fc-104">Para restaurar las bases de datos de archivo de BAM, siga los pasos descritos en [cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span><span class="sxs-lookup"><span data-stu-id="3b7fc-104">To restore the BAM Archive databases, perform the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="3b7fc-105">Además, debe actualizar los paquetes SSIS de BAM con el nuevo nombre del servidor y el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3b7fc-105">In addition, you must update the BAM SSIS packages with the new server name and database name.</span></span>  
  
## <a name="how-to-update-references-to-bam-archive-database"></a><span data-ttu-id="3b7fc-106">Cómo actualizar referencias a la base de datos de archivo BAM</span><span class="sxs-lookup"><span data-stu-id="3b7fc-106">How to Update References to BAM Archive Database</span></span>  
 <span data-ttu-id="3b7fc-107">Para obtener instrucciones sobre cómo actualizar referencias a la base de datos de archivo de BAM, consulte [actualizar referencias a la nueva base de datos de archivo de BAM](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch).</span><span class="sxs-lookup"><span data-stu-id="3b7fc-107">For instructions on how to update references to BAM Archive database, see [Updating References to the New BAM Archive Database](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b7fc-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b7fc-108">See Also</span></span>  
 [<span data-ttu-id="3b7fc-109">Copia de seguridad el análisis BAM y las bases de datos del servidor de análisis de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3b7fc-109">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)