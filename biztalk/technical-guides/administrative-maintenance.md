---
title: Mantenimiento administrativa | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67cdf9d7-5448-40c5-8c5f-eae0e281d22c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed53236352831d3ae920263d57b89ed4789be0ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="administrative-maintenance"></a><span data-ttu-id="56cf4-102">Mantenimiento administrativo</span><span class="sxs-lookup"><span data-stu-id="56cf4-102">Administrative Maintenance</span></span>
<span data-ttu-id="56cf4-103">Esta sección proporciona información acerca de cómo puede resolver problemas de administración con un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema.</span><span class="sxs-lookup"><span data-stu-id="56cf4-103">This section provides information about how you can resolve administration issues with a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="56cf4-104">Estos problemas pueden ser detectados por las comprobaciones de mantenimiento rutinarias que se realizan en el [listas de comprobación de mantenimiento de rutina](../technical-guides/routine-maintenance-checklists.md) sección.</span><span class="sxs-lookup"><span data-stu-id="56cf4-104">These issues may be discovered by the routine maintenance checks that are performed in the [Routine Maintenance Checklists](../technical-guides/routine-maintenance-checklists.md) section.</span></span>  
  
 <span data-ttu-id="56cf4-105">Además de los temas de esta sección, otros temas en este documento abordan problemas de administración.</span><span class="sxs-lookup"><span data-stu-id="56cf4-105">In addition to the topics in this section, other topics in this document address administration issues.</span></span> <span data-ttu-id="56cf4-106">En estos temas se muestran en las secciones relacionadas a continuación.</span><span class="sxs-lookup"><span data-stu-id="56cf4-106">These topics are listed in Related Sections below.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56cf4-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="56cf4-107">In This Section</span></span>  
  
-   [<span data-ttu-id="56cf4-108">Prácticas recomendadas para el mantenimiento administrativo</span><span class="sxs-lookup"><span data-stu-id="56cf4-108">Best Practices for Administrative Maintenance</span></span>](../technical-guides/best-practices-for-administrative-maintenance.md)  
  
-   [<span data-ttu-id="56cf4-109">Cómo iniciar al Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="56cf4-109">How to Start the SQL Server Agent</span></span>](../technical-guides/how-to-start-the-sql-server-agent.md)  
  
-   [<span data-ttu-id="56cf4-110">Cómo programar un trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="56cf4-110">How to Schedule a Backup BizTalk Server Job</span></span>](../technical-guides/how-to-schedule-a-backup-biztalk-server-job.md)  
  
-   [<span data-ttu-id="56cf4-111">Cómo configurar un trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="56cf4-111">How to Configure a Backup BizTalk Server Job</span></span>](../technical-guides/how-to-configure-a-backup-biztalk-server-job.md)  
  
## <a name="related-sections"></a><span data-ttu-id="56cf4-112">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="56cf4-112">Related Sections</span></span>  
  
-   <span data-ttu-id="56cf4-113">Para obtener información sobre cómo asegurarse de que el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] servicio de agente se ejecuta en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]y asegurarse de que todos los BizTalk relacionadas con trabajos de SQL Server estén funcionando correctamente, consulte [trabajos del agente de supervisión de SQL Server](../technical-guides/monitoring-sql-server-agent-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="56cf4-113">For information about ensuring that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent service is running on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and ensuring that all BizTalk related SQL Server jobs are working properly, see [Monitoring SQL Server Agent Jobs](../technical-guides/monitoring-sql-server-agent-jobs.md).</span></span>  
  
-   <span data-ttu-id="56cf4-114">Para obtener información acerca de cómo quitar una aplicación de BizTalk o un artefacto mediante la herramienta de línea de comandos de BTSTask, vea "Comando RemoveApp" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkID=154687](http://go.microsoft.com/fwlink/?LinkID=154687).</span><span class="sxs-lookup"><span data-stu-id="56cf4-114">For information about removing a BizTalk application or artifact using the BTSTask command-line tool, see "RemoveApp Command" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154687](http://go.microsoft.com/fwlink/?LinkID=154687).</span></span>  
  
-   <span data-ttu-id="56cf4-115">Para obtener información sobre cómo quitar un artefacto de una aplicación mediante la consola de administración de BizTalk Server o la herramienta de línea de comandos de BTSTask, vea "Cómo para quitar un artefacto de una aplicación" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http:// ¿go.Microsoft.com/fwlink/? LinkID = 154688](http://go.microsoft.com/fwlink/?LinkID=154688).</span><span class="sxs-lookup"><span data-stu-id="56cf4-115">For information about removing an artifact from an application using either the BizTalk Server Administration console or the BTSTask command-line tool, see "How to Remove an Artifact from an Application" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154688](http://go.microsoft.com/fwlink/?LinkID=154688).</span></span>  
  
-   <span data-ttu-id="56cf4-116">Para obtener información acerca de cómo comprobar la configuración en la consola de administración de BizTalk, vea "Utilizar la consola de administración de servidor BizTalk" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkID=154689](http://go.microsoft.com/fwlink/?LinkID=154689).</span><span class="sxs-lookup"><span data-stu-id="56cf4-116">For information about verifying the configuration in the BizTalk Administration Console, see "Using the BizTalk Server Administration Console" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154689](http://go.microsoft.com/fwlink/?LinkID=154689).</span></span>  
  
-   <span data-ttu-id="56cf4-117">Para obtener información acerca de cómo comprobar el archivo BTSNTSvc.exe.config, consulte "Archivo BTSNTSvc.exe.config" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkID=154690](http://go.microsoft.com/fwlink/?LinkID=154690).</span><span class="sxs-lookup"><span data-stu-id="56cf4-117">For information about verifying the BTSNTSvc.exe.config file, see "BTSNTSvc.exe.config File" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154690](http://go.microsoft.com/fwlink/?LinkID=154690).</span></span>  
  
-   <span data-ttu-id="56cf4-118">Para obtener información sobre la comprobación de BizTalk claves del registro relacionadas, vea "Windows información del registro para los usuarios avanzados" en el sitio Web de soporte técnico y Microsoft Help en [http://go.microsoft.com/fwlink/?LinkId=155583](http://go.microsoft.com/fwlink/?LinkId=155583).</span><span class="sxs-lookup"><span data-stu-id="56cf4-118">For information about verifying the BizTalk related registry keys, see "Windows registry information for advanced users" in the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=155583](http://go.microsoft.com/fwlink/?LinkId=155583).</span></span>  
  
-   <span data-ttu-id="56cf4-119">Para obtener información acerca de cómo ejecutar el analizador de procedimientos recomendados de BizTalk, vea "BizTalk Server Best Practices Analyzer" en Microsoft Download Center en [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317).</span><span class="sxs-lookup"><span data-stu-id="56cf4-119">For information about running the BizTalk Best Practices Analyzer, see "BizTalk Server Best Practices Analyzer" in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  
  
-   <span data-ttu-id="56cf4-120">Para obtener información acerca del mantenimiento de bases de datos BAM, vea "Administración de bases de datos de BAM" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkId=155584](http://go.microsoft.com/fwlink/?LinkId=155584).</span><span class="sxs-lookup"><span data-stu-id="56cf4-120">For information about maintaining BAM databases, see "Managing BAM Databases" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=155584](http://go.microsoft.com/fwlink/?LinkId=155584).</span></span>  
  
-   <span data-ttu-id="56cf4-121">Para obtener información sobre cómo asegurarse de que están instaladas los últimos service packs y revisiones, consulte el sitio Web de Microsoft Update en [http://go.microsoft.com/fwlink/?LinkID=47813](http://go.microsoft.com/fwlink/?LinkID=47813).</span><span class="sxs-lookup"><span data-stu-id="56cf4-121">For information about ensuring that the latest service packs and hotfixes are installed, see the Microsoft Update Web site at [http://go.microsoft.com/fwlink/?LinkID=47813](http://go.microsoft.com/fwlink/?LinkID=47813).</span></span>