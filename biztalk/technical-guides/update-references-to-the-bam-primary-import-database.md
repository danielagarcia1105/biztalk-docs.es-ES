---
title: "Actualizar las referencias a la base de datos de importación principal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3da3b545-0d81-491b-bc37-0a980a7814b6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ba37a32c82967e84b61bb46c58c62af9bf23b1b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="update-references-to-the-bam-primary-import-database"></a><span data-ttu-id="ca127-102">Actualizar las referencias a la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="ca127-102">Update References to the BAM Primary Import Database</span></span>
<span data-ttu-id="ca127-103">Si ha realizado una copia de seguridad de la base de datos de importación principal de SAE, en el caso de que se produzca un error de datos o del sistema podrá restaurar la copia de seguridad en un equipo distinto y cambiar el nombre a esa copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ca127-103">If you backed up your BAM Primary Import database in the event of a system or data failure, you can restore that backup to a different computer and rename the backup.</span></span>  
  
 <span data-ttu-id="ca127-104">El servicio de bus de sucesos SAE mueve los datos de sucesos desde la base de datos de cuadro de mensajes a la base de datos de importación principal de SAE.</span><span class="sxs-lookup"><span data-stu-id="ca127-104">The BAM Event Bus service moves event data from the MessageBox database to the BAM Primary Import database.</span></span> <span data-ttu-id="ca127-105">El servicio de bus de eventos de SAE incluye una lógica de tolerancia a errores que le permite recuperarse y reiniciarse a partir de un error inesperado sin pérdida alguna de datos.</span><span class="sxs-lookup"><span data-stu-id="ca127-105">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span> <span data-ttu-id="ca127-106">Para obtener más información sobre el servicio de Bus de sucesos SAE, vea el tema [administrar el servicio de Bus de eventos BAM](http://go.microsoft.com/fwlink/?LinkID=154194) (http://go.microsoft.com/fwlink/?LinkID=154194).</span><span class="sxs-lookup"><span data-stu-id="ca127-106">For more information about the BAM Event Bus service, see the topic [Managing the BAM Event Bus Service](http://go.microsoft.com/fwlink/?LinkID=154194) (http://go.microsoft.com/fwlink/?LinkID=154194).</span></span>  
  
 <span data-ttu-id="ca127-107">Para restaurar la base de datos de importación principal de BAM, siga los pasos descritos en [cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span><span class="sxs-lookup"><span data-stu-id="ca127-107">To restore the BAM Primary Import database, perform the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="ca127-108">Además, debe actualizar los paquetes SSIS de BAM con el nuevo nombre del servidor y el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ca127-108">In addition, you must update the BAM SSIS packages with the new server name and database name.</span></span>  
  
## <a name="how-to-update-references-to-bam-primary-import-database"></a><span data-ttu-id="ca127-109">Cómo actualizar referencias a la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="ca127-109">How to Update References to BAM Primary Import Database</span></span>  
 <span data-ttu-id="ca127-110">Para obtener instrucciones sobre cómo actualizar referencias a la base de datos de importación principal de BAM, [actualizar referencias a la base de importación principal de BAM nueva](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef).</span><span class="sxs-lookup"><span data-stu-id="ca127-110">For instructions on how to update references to BAM Primary Import database, [Updating References to the New BAM Primary Import Database](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca127-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca127-111">See Also</span></span>  
 [<span data-ttu-id="ca127-112">Copia de seguridad el análisis BAM y las bases de datos del servidor de análisis de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ca127-112">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)