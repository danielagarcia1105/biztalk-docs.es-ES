---
title: Administrar bases de datos BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], databases
- databases [BAM], managing
- databases, BAM
ms.assetid: ce3c472e-2da1-4d67-816a-befe4ded20d9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dbe8cdb2c7806ab62b67db80c4741d64560fba9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="managing-bam-databases"></a><span data-ttu-id="c3704-102">Administrar bases de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="c3704-102">Managing BAM Databases</span></span>
<span data-ttu-id="c3704-103">Los administradores se sirven de la utilidad de administración de BAM (bm.exe) para instalar, administrar y actualizar las bases de datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="c3704-103">Administrators use the BAM Management utility (bm.exe) to set up, manage, and update the BAM databases.</span></span> <span data-ttu-id="c3704-104">Esta sección muestra cómo usar la utilidad de administración de BAM para llevar a cabo estas tareas comunes de administración para las bases de datos de BAM, descritas en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c3704-104">This section shows you how to use the BAM Management utility to perform these common administrator tasks for the BAM databases, which are described in the following table.</span></span>  
  
 <span data-ttu-id="c3704-105">Para obtener información acerca de la copia de seguridad y restaurar las bases de datos BAM, consulte [copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md).</span><span class="sxs-lookup"><span data-stu-id="c3704-105">For information about backing up and restoring the BAM databases, see [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
|<span data-ttu-id="c3704-106">Base de datos</span><span class="sxs-lookup"><span data-stu-id="c3704-106">Database</span></span>|<span data-ttu-id="c3704-107">Nombre predeterminado de la base de datos</span><span class="sxs-lookup"><span data-stu-id="c3704-107">Default database name</span></span>|<span data-ttu-id="c3704-108">Description</span><span class="sxs-lookup"><span data-stu-id="c3704-108">Description</span></span>|  
|--------------|---------------------------|-----------------|  
|<span data-ttu-id="c3704-109">Base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="c3704-109">BAM Primary Import database</span></span>|<span data-ttu-id="c3704-110">BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="c3704-110">BAMPrimaryImport</span></span>|<span data-ttu-id="c3704-111">Donde BAM recopila los datos de seguimiento sin procesar.</span><span class="sxs-lookup"><span data-stu-id="c3704-111">Where BAM collects raw tracking data.</span></span>|  
|<span data-ttu-id="c3704-112">Base de datos de la aplicación de servicios de notificación de BAM</span><span class="sxs-lookup"><span data-stu-id="c3704-112">BAM Notification Services Application database</span></span>|<span data-ttu-id="c3704-113">BAMAlertsApplication</span><span class="sxs-lookup"><span data-stu-id="c3704-113">BAMAlertsApplication</span></span>|<span data-ttu-id="c3704-114">Contiene información de alertas para las notificaciones de BAM.</span><span class="sxs-lookup"><span data-stu-id="c3704-114">Contains alert information for BAM notifications.</span></span> <span data-ttu-id="c3704-115">Por ejemplo, al crear una alerta utilizando el portal de BAM, las entradas se insertan en la base de datos especificando las condiciones y eventos a los que pertenece la alerta, así como otros datos complementarios relativos a ésta.</span><span class="sxs-lookup"><span data-stu-id="c3704-115">For example, when you create an alert using the BAM portal, entries are inserted in the database specifying the conditions and events to which the alert pertains, as well as other supporting data items for the alert.</span></span>|  
|<span data-ttu-id="c3704-116">Base de datos de instancia de servicios de notificación de BAM</span><span class="sxs-lookup"><span data-stu-id="c3704-116">BAM Notification Services Instance database</span></span>|<span data-ttu-id="c3704-117">BAMAlertsNSMain</span><span class="sxs-lookup"><span data-stu-id="c3704-117">BAMAlertsNSMain</span></span>|<span data-ttu-id="c3704-118">Contiene información de la instancia que especifica el modo en que los servicios de notificación establecen una conexión con el sistema controlado por BAM.</span><span class="sxs-lookup"><span data-stu-id="c3704-118">Contains instance information specifying how the notification services connect to the system that BAM is monitoring.</span></span>|  
|<span data-ttu-id="c3704-119">Base de datos de esquema de estrella de SAE</span><span class="sxs-lookup"><span data-stu-id="c3704-119">BAM Star Schema database</span></span>|<span data-ttu-id="c3704-120">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="c3704-120">BAMStarSchema</span></span>|<span data-ttu-id="c3704-121">Contiene la tabla provisional y las tablas de dimensiones y medidas.</span><span class="sxs-lookup"><span data-stu-id="c3704-121">Contains the staging table, and the measure and dimension tables.</span></span>|  
|<span data-ttu-id="c3704-122">Base de datos de análisis de BAM</span><span class="sxs-lookup"><span data-stu-id="c3704-122">BAM Analysis database</span></span>|<span data-ttu-id="c3704-123">BAMAnalysis</span><span class="sxs-lookup"><span data-stu-id="c3704-123">BAMAnalysis</span></span>|<span data-ttu-id="c3704-124">Contiene cubos OLAP de BAM para el análisis en línea y sin conexión.</span><span class="sxs-lookup"><span data-stu-id="c3704-124">Contains BAM OLAP cubes for both online and offline analysis.</span></span>|  
|<span data-ttu-id="c3704-125">Base de datos de archivo SAE</span><span class="sxs-lookup"><span data-stu-id="c3704-125">BAM Archive database</span></span>|<span data-ttu-id="c3704-126">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="c3704-126">BAMArchive</span></span>|<span data-ttu-id="c3704-127">Archiva datos antiguos de la actividad de negocio.</span><span class="sxs-lookup"><span data-stu-id="c3704-127">Archives old business activity data.</span></span> <span data-ttu-id="c3704-128">Puede crear una base de datos de archivo de BAM para minimizar la acumulación de datos de la actividad de negocio en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="c3704-128">You can create a BAM Archive database to minimize the accumulation of business activity data in the BAM Primary Import database.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="c3704-129">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c3704-129">In This Section</span></span>  
  
-   [<span data-ttu-id="c3704-130">Archivar los datos de la base de datos de importación principal</span><span class="sxs-lookup"><span data-stu-id="c3704-130">Archiving Primary Import Database Data</span></span>](../core/archiving-primary-import-database-data.md)  
  
-   [<span data-ttu-id="c3704-131">Crear una vista con particiones en la base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="c3704-131">Creating a Partitioned View in the Archiving Database</span></span>](../core/creating-a-partitioned-view-in-the-archiving-database.md)  
  
-   [<span data-ttu-id="c3704-132">Paquetes de programación de SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="c3704-132">Scheduling SQL Server Integration Services Packages</span></span>](../core/scheduling-sql-server-integration-services-packages.md)  
  
-   [<span data-ttu-id="c3704-133">Cómo configurar las bases de datos BAM mediante la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="c3704-133">How to Set Up the BAM Databases Using the BAM Management Utility</span></span>](../core/how-to-set-up-the-bam-databases-using-the-bam-management-utility.md)  
  
-   [<span data-ttu-id="c3704-134">Cómo recuperar el archivo de configuración de BAM mediante la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="c3704-134">How to Retrieve the BAM Configuration File Using the BAM Management Utility</span></span>](../core/how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility.md)  
  
-   [<span data-ttu-id="c3704-135">Cómo actualizar la configuración de BAM mediante la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="c3704-135">How to Update the BAM Configuration Using the BAM Management Utility</span></span>](../core/how-to-update-the-bam-configuration-using-the-bam-management-utility.md)  
  
-   [<span data-ttu-id="c3704-136">Cómo hacer referencia a las bases de datos de importación principal de BAM adicionales</span><span class="sxs-lookup"><span data-stu-id="c3704-136">How to Reference Additional BAM Primary Import Databases</span></span>](../core/how-to-reference-additional-bam-primary-import-databases.md)  
  
-   [<span data-ttu-id="c3704-137">Cómo deshabilitar una referencia de base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="c3704-137">How to Disable a BAM Primary Import Database Reference</span></span>](../core/how-to-disable-a-bam-primary-import-database-reference.md)  
  
-   [<span data-ttu-id="c3704-138">Cómo enumerar todas hace referencia a las bases de datos</span><span class="sxs-lookup"><span data-stu-id="c3704-138">How to List All Referenced Databases</span></span>](../core/how-to-list-all-referenced-databases.md)  
  
-   [<span data-ttu-id="c3704-139">Cómo quitar instancias de actividad incompletas</span><span class="sxs-lookup"><span data-stu-id="c3704-139">How to Remove Incomplete Activity Instances</span></span>](../core/how-to-remove-incomplete-activity-instances.md)  
  
-   [<span data-ttu-id="c3704-140">Cómo actualizar la configuración de utilidad de administración de BAM después de una copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="c3704-140">How to Update the BAM Management Utility Configuration After a Backup and Restore</span></span>](../core/update-the-bam-management-utility-configuration-after-a-backup-and-restore.md)  
  
-   [<span data-ttu-id="c3704-141">Cómo integrar BAM con SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c3704-141">How to Integrate BAM with SQL Server Reporting Services</span></span>](../core/how-to-integrate-bam-with-sql-server-reporting-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="c3704-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3704-142">See Also</span></span>  
 [<span data-ttu-id="c3704-143">Administración de BAM</span><span class="sxs-lookup"><span data-stu-id="c3704-143">Managing BAM</span></span>](../core/managing-bam.md)