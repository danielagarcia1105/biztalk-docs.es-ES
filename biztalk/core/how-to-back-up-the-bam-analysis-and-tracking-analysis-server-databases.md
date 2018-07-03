---
title: Cómo realizar copias de seguridad el análisis de BAM y el análisis de seguimiento de las bases de datos del servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, DTS packages
- backing up [BAM], Tracking Analysis Server database
- backing up [BAM], OLAP cubes
- backing up [BAM], DTS packages
- purging, OLAP cubes
- Analysis database [BAM], backing up
- scheduling, BAM backups
- backing up [BAM], Analysis database
- OLAP cubes, purging
- backing up, BAM
- backing up [BAM], database order
- DTS packages, backing up
- backing up [BAM], Star Schema database
- backing up [BAM], scheduling
- Tracking Analysis Server database [BAM], backing up
- Star Schema database [BAM], backing up
ms.assetid: d39e3491-ab54-44f2-990a-7b8ee86f0501
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1b7dca60859d0dcda69d6c9110b4be08d90586b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983381"
---
# <a name="how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases"></a><span data-ttu-id="7490c-102">Cómo realizar una copia de seguridad de las bases de datos de servidor de análisis de seguimiento y de análisis de SAE</span><span class="sxs-lookup"><span data-stu-id="7490c-102">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>
<span data-ttu-id="7490c-103">La base de datos de análisis de Supervisión de la actividad económica (SAE) y la base de datos de servidor de análisis de seguimiento almacenan contenido en los cubos de los servicios de análisis de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7490c-103">The Business Activity Monitoring (BAM) Analysis database and the Tracking Analysis Server database store content in SQL Server Analysis Services cubes.</span></span> <span data-ttu-id="7490c-104">El trabajo de copia de seguridad de BizTalk Server no realiza ninguna copia de seguridad de estas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="7490c-104">The Backup BizTalk Server job does not back up these databases.</span></span> <span data-ttu-id="7490c-105">Para ello, tendrá que utilizar Analysis Manager de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7490c-105">Instead, to backup these databases, you must use SQL Server Analysis Manager.</span></span>  
  
 <span data-ttu-id="7490c-106">Después de realizar una copia de seguridad de estas bases de datos, es posible que desee purgar los cubos OLAP.</span><span class="sxs-lookup"><span data-stu-id="7490c-106">After you back up these databases, you may want to purge the OLAP cubes.</span></span> <span data-ttu-id="7490c-107">Al purgar los cubos OLAP, también debe llevar a cabo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7490c-107">When you purge the OLAP cubes, you must also perform the following steps:</span></span>  
  
1. <span data-ttu-id="7490c-108">Antes de purgar los cubos OLAP, en la base de datos BAMStarSchema, trunque las tablas de hechos del cubo que desee purgar.</span><span class="sxs-lookup"><span data-stu-id="7490c-108">Before you purge the OLAP cubes, in the BAMStarSchema database, truncate the fact table(s) for the cube you want to purge.</span></span> <span data-ttu-id="7490c-109">La convención de nomenclatura de la tabla es "bam_*\<CubeName\>*_Facts".</span><span class="sxs-lookup"><span data-stu-id="7490c-109">The table naming convention is "bam_*\<CubeName\>*_Facts".</span></span>  
  
2. <span data-ttu-id="7490c-110">Tras purgar los cubos OLAP, debe procesar completamente los cubos virtuales, completados y activos.</span><span class="sxs-lookup"><span data-stu-id="7490c-110">After you purge the OLAP cubes, you must fully process active, completed, and virtual cubes.</span></span>  
  
   <span data-ttu-id="7490c-111">Para obtener instrucciones acerca de la copia de seguridad de las bases de datos de análisis, vea la sección que trata acerca del proceso de archivo de una base de datos de servicios de análisis de los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7490c-111">For instructions about backing up the analysis databases, see "Archiving an Analysis Services Database" in SQL Server Books Online.</span></span>  
  
   <span data-ttu-id="7490c-112">**Programar copias de seguridad para las bases de datos BAM**</span><span class="sxs-lookup"><span data-stu-id="7490c-112">**Scheduling backups for the BAM databases**</span></span>  
  
   <span data-ttu-id="7490c-113">Si utiliza SAE, compruebe que los paquetes de Servicios de transformación de datos (DTS) de mantenimiento de datos o procesos de cubo de SAE no estén en ejecución cuando el paquete de copia de seguridad está programado para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="7490c-113">If you are using BAM, verify that neither the BAM cube process nor data maintenance Data Transformation Services (DTS) packages are running when the backup package is scheduled to run.</span></span>  
  
   <span data-ttu-id="7490c-114">Para garantizar la consistencia del esquema en todas las bases de datos de SAE, realice una copia de seguridad de las bases de datos de SAE y de los paquetes DTS siempre vez que implemente una actividad de SAE o anule la implementación de ésta.</span><span class="sxs-lookup"><span data-stu-id="7490c-114">To ensure consistent schema across all BAM databases, back up the BAM databases and DTS packages each time you deploy or undeploy a BAM activity.</span></span>  
  
   <span data-ttu-id="7490c-115">Realice una copia de seguridad de la base de datos de análisis de BAM y de la base de datos BAMStarSchema siempre que implemente una vista de SAE o anule la implementación de ésta.</span><span class="sxs-lookup"><span data-stu-id="7490c-115">Back up the BAM Analysis database and BAMStarSchema database each time you deploy or undeploy a BAM view.</span></span>  
  
   <span data-ttu-id="7490c-116">Realice una copia de seguridad de las bases de datos de SAE de acuerdo con el orden que se especifica a continuación:</span><span class="sxs-lookup"><span data-stu-id="7490c-116">Back up the BAM databases in the following order:</span></span>  
  
3. <span data-ttu-id="7490c-117">Ejecute el trabajo de copia de seguridad de BizTalk Server para realizar una copia de seguridad de la base de datos BAMPrimaryImport y de las otras bases de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7490c-117">Run the Backup BizTalk Server job to back up the BAMPrimaryImport database and your other BizTalk Server databases.</span></span>  
  
4. <span data-ttu-id="7490c-118">Ejecute el paquete DTS de mantenimiento de datos de SAE para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="7490c-118">Run the BAM data maintenance DTS package for all activities.</span></span>  
  
    <span data-ttu-id="7490c-119">Integre estos pasos a un paquete DTS y programe este último para que se ejecute de forma regular.</span><span class="sxs-lookup"><span data-stu-id="7490c-119">Incorporate these steps into a DTS package, and schedule the package to run on a regular basis.</span></span> <span data-ttu-id="7490c-120">Para garantizar la integridad de los datos, asegúrese de que ningún otro paquete DTS de mantenimiento de datos o elaboración de cubos de SAE se ejecuta cuando el paquete de copia de seguridad tenga programada su ejecución.</span><span class="sxs-lookup"><span data-stu-id="7490c-120">To ensure data integrity, make sure no other BAM cubing or data maintenance DTS packages run when this backup package is scheduled to run.</span></span>  
  
    <span data-ttu-id="7490c-121">Para garantizar la posibilidad de recuperación de un conjunto completo de datos archivados en el caso de que se produzca un error de la base de datos BAMArchive, realice una copia de seguridad de esta última tras copiar en ella la partición, pero antes de eliminar la partición de la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="7490c-121">To ensure that you can recover a complete set of archived data if the BAMArchive database fails, back up the BAMArchive database after you copy the partition into the BAMArchive database, but before you delete the partition from the BAMPrimaryImport database.</span></span> <span data-ttu-id="7490c-122">Para ello, modifique el paquete DTS de mantenimiento de datos para cada una de las actividades con el fin de insertar un paso para realizar una copia de seguridad de la base de datos BAMArchive antes del último paso del paquete DTS, "Finalizar archivo".</span><span class="sxs-lookup"><span data-stu-id="7490c-122">To do this, modify the data maintenance DTS package for each activity to insert a step to back up the BAMArchive database before the last step in the DTS package, "End Archiving."</span></span>  
  
5. <span data-ttu-id="7490c-123">Realice una copia de seguridad de la base de datos BAMAnalysis y, a continuación, de la base de datos BAMStarSchema.</span><span class="sxs-lookup"><span data-stu-id="7490c-123">Back up the BAMAnalysis database, and then the BAMStarSchema database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7490c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="7490c-124">See Also</span></span>  
 [<span data-ttu-id="7490c-125">Realizar una copia de seguridad y restaurar las bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7490c-125">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)