---
title: Cómo restaurar las bases de datos en el trabajo de copia de seguridad de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9bcac40f-ef0b-4ff0-8743-cf1614e14422
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb7c52b810343c1807e982e637372c74baeb84fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298564"
---
# <a name="how-to-restore-databases-in-the-backup-biztalk-server-job"></a><span data-ttu-id="f5d71-102">Cómo restaurar las bases de datos en el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f5d71-102">How to Restore Databases in the Backup BizTalk Server Job</span></span>
<span data-ttu-id="f5d71-103">En esta sección se describe los pasos para poner en línea las bases de datos en el grupo de BizTalk que estén respaldados por el trabajo de copia de seguridad de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f5d71-103">This section covers the steps to bring online the databases in the BizTalk group that are backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="f5d71-104">De forma predeterminada, se copian todas las bases de datos con el trabajo de copia de seguridad de BizTalk Server excepto las bases de datos BAM.</span><span class="sxs-lookup"><span data-stu-id="f5d71-104">By default, all databases are backed up by using the Backup BizTalk Server job except for the BAM databases.</span></span> <span data-ttu-id="f5d71-105">Vea [restaurar Analysis Services y compatibilidad con bases de datos](../technical-guides/restoring-analysis-services-and-supporting-databases.md) para obtener más información sobre la copia de seguridad y restauración de las bases de datos BAM.</span><span class="sxs-lookup"><span data-stu-id="f5d71-105">See [Restoring Analysis Services and Supporting Databases](../technical-guides/restoring-analysis-services-and-supporting-databases.md) for more information about backup and restore of the BAM databases.</span></span> <span data-ttu-id="f5d71-106">Es preciso efectuar una restauración de todas las bases de datos en la misma marca para garantizar que el estado transaccional sea coherente en todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="f5d71-106">You must restore all databases to the same mark to ensure a consistent transactional state among the databases.</span></span> <span data-ttu-id="f5d71-107">Para obtener más información, consulte [transacciones marcadas y copias de seguridad completas, copias de seguridad del registro](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565).</span><span class="sxs-lookup"><span data-stu-id="f5d71-107">For more information, see [Marked Transactions, Full Backups, and Log Backups](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565).</span></span>  
  
 <span data-ttu-id="f5d71-108">Para obtener más información e instrucciones acerca de cómo restaurar bases de datos para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [cómo restaurar las bases de datos](http://go.microsoft.com/fwlink/?LinkId=151406) (http://go.microsoft.com/fwlink/?LinkId=151406).</span><span class="sxs-lookup"><span data-stu-id="f5d71-108">For more information and instructions about restoring databases for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [How to Restore Your Databases](http://go.microsoft.com/fwlink/?LinkId=151406) (http://go.microsoft.com/fwlink/?LinkId=151406).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5d71-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5d71-109">See Also</span></span>  
 [<span data-ttu-id="f5d71-110">Restaurar bases de datos que no se incluye en el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f5d71-110">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)