---
title: Restaurar los servicios de análisis y compatibilidad con bases de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 490ad0fb-7805-4ebc-9bc5-117d52d7c3a8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da16bde7b69071b71b794c4c46407feab3ef4512
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301996"
---
# <a name="restoring-analysis-services-and-supporting-databases"></a><span data-ttu-id="7043f-102">Restaurar los servicios de análisis y compatibilidad con bases de datos</span><span class="sxs-lookup"><span data-stu-id="7043f-102">Restoring Analysis Services and Supporting Databases</span></span>
<span data-ttu-id="7043f-103">Hay dos [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos de Analysis Services que deben restaurarse en un escenario de recuperación ante desastres:</span><span class="sxs-lookup"><span data-stu-id="7043f-103">There are two [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases that must be restored in a disaster recovery scenario:</span></span>  
  
-   <span data-ttu-id="7043f-104">Análisis de BAM (BAMAnalysis)</span><span class="sxs-lookup"><span data-stu-id="7043f-104">BAM Analysis (BAMAnalysis)</span></span>  
  
-   <span data-ttu-id="7043f-105">Servidor de análisis de seguimiento (BizTalkAnalysisdb)</span><span class="sxs-lookup"><span data-stu-id="7043f-105">Tracking Analysis Server (BizTalkAnalysisdb)</span></span>  
  
 <span data-ttu-id="7043f-106">Implementación de BAM [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] copia bases de datos pueden ser como parte del trabajo de copia de seguridad de BizTalk Server si BAM está habilitada pero no configurado.</span><span class="sxs-lookup"><span data-stu-id="7043f-106">The BAM [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases may be backed up as part of the Backup BizTalk Server job if BAM is enabled but not configured.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7043f-107">La base de datos de importación principal de BAM siempre se copia como parte del trabajo de copia de seguridad de BizTalk Server porque participa en transacciones DTC.</span><span class="sxs-lookup"><span data-stu-id="7043f-107">The BAM Primary Import database is always backed up as part of the Backup BizTalk Server job because it participates in DTC transactions.</span></span>  
  
 <span data-ttu-id="7043f-108">Las siguientes bases de datos BAM va a formar parte del trabajo de copia de seguridad de BizTalk Server si BAM está habilitada pero no configurado:</span><span class="sxs-lookup"><span data-stu-id="7043f-108">The following BAM databases will be part of the Backup BizTalk Server job if BAM is enabled but not configured:</span></span>  
  
-   <span data-ttu-id="7043f-109">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="7043f-109">BAMStarSchema</span></span>  
  
-   <span data-ttu-id="7043f-110">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="7043f-110">BAMArchive</span></span>  
  
 <span data-ttu-id="7043f-111">Siga los pasos de [cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md) restaurar estas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="7043f-111">Follow the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md) to restore these databases.</span></span>  
  
 <span data-ttu-id="7043f-112">**En caso contrario,**</span><span class="sxs-lookup"><span data-stu-id="7043f-112">**Otherwise,**</span></span>  
 <span data-ttu-id="7043f-113">**Si BAM está habilitada y también se configura con BM.exe, el conjunto correcto de las bases de datos BAM debe restaurarse conjuntamente como un conjunto.**</span><span class="sxs-lookup"><span data-stu-id="7043f-113">**if BAM is enabled and is also configured with BM.exe, the correct set of BAM databases must be restored together as a set.**</span></span> <span data-ttu-id="7043f-114">Para asegurarse de que se recuperará un conjunto completo de los datos archivados, la base de datos de archivo de BAM se copia después de la partición se copia en el archivo de BAM, pero antes de que la partición se elimina de la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="7043f-114">To ensure that a complete set of archived data is recovered, the BAM Archive database is backed up after the partition is copied into the BAM Archive, but before the partition is deleted from the BAM Primary Import database.</span></span> <span data-ttu-id="7043f-115">Esto se realiza mediante la modificación del paquete SSIS de mantenimiento de datos para cada actividad insertando un paso para realizar una copia de la base de datos de archivo de BAM antes de que el último paso "Finalizar archivo".</span><span class="sxs-lookup"><span data-stu-id="7043f-115">This is performed by modifying the data maintenance SSIS package for each activity by inserting a step to back up the BAM Archive database before the last step "End Archiving."</span></span>  
  
 <span data-ttu-id="7043f-116">El procedimiento de restauración para las bases de datos BAM es: si se restaura la base de datos de importación principal de BAM con la última fecha de copia de seguridad de x, restaure las copias de las bases de datos de archivo de BAM y esquema de estrella de BAM que corresponden a la fecha más reciente, ¿cuándo fue el paquete SSIS de mantenimiento de datos ejecutar antes de la fecha de x.</span><span class="sxs-lookup"><span data-stu-id="7043f-116">The restore procedure for the BAM databases is: If the BAM Primary Import database is restored with the last backup date of x, restore the copies of the BAM Archive and BAM Star Schema databases that correspond to the latest date when the data maintenance SSIS package was run before the date of x.</span></span>  
  
 <span data-ttu-id="7043f-117">Después de haber identificado el conjunto correcto de las bases de datos BAM, restaurar la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos de Analysis Services mediante procedimientos estándares tal como se describe en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla para restaurar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Bases de datos de analysis Services.</span><span class="sxs-lookup"><span data-stu-id="7043f-117">After the correct set of BAM databases is identified, restore the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases using standard procedures as documented in the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online for restoring [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7043f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7043f-118">See Also</span></span>  
 [<span data-ttu-id="7043f-119">Copia de seguridad el análisis BAM y las bases de datos del servidor de análisis de seguimiento</span><span class="sxs-lookup"><span data-stu-id="7043f-119">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)