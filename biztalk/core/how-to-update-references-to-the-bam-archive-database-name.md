---
title: Cómo actualizar referencias al nombre de base de datos de archivo BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Archive database [BAM], restoring
- restoring, BAM
- restoring [BAM], Archive database
- restoring [BAM], updating references
- Archive database [BAM], updating references
- BAM, restoring
ms.assetid: a0b8543e-6fc1-412e-b74e-683352d9c49e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0df87a548c2a6a5a207673d96a984e16287f04a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256420"
---
# <a name="how-to-update-references-to-the-bam-archive-database-name"></a><span data-ttu-id="27fde-102">Cómo actualizar referencias al nombre de base de datos de archivo de SAE</span><span class="sxs-lookup"><span data-stu-id="27fde-102">How to Update References to the BAM Archive Database Name</span></span>
<span data-ttu-id="27fde-103">Si realizó una copia de seguridad de las bases de datos BAMArchive, podrá restaurar la copia de seguridad y cambiarle el nombre en el caso de que se produzca un error de datos o del sistema.</span><span class="sxs-lookup"><span data-stu-id="27fde-103">If you backed up your BAMArchive databases, in the event of a system or data failure you can restore that backup and rename it.</span></span>  
  
 <span data-ttu-id="27fde-104">Para restaurar las bases de datos BAMArchive, siga los pasos descritos en [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md).</span><span class="sxs-lookup"><span data-stu-id="27fde-104">To restore the BAMArchive databases, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="27fde-105">Además, tendrá que realizar estos pasos generales, a los que sigue un procedimiento que describe los pasos de forma detallada:</span><span class="sxs-lookup"><span data-stu-id="27fde-105">In addition, you must perform these general steps, which are followed by a procedure that describes the steps in detail:</span></span>  
  
-   <span data-ttu-id="27fde-106">Actualice los paquetes DTS de SAE con el nuevo nombre de servidor y el de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="27fde-106">Update the BAM DTS packages with the new server name and database name.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="27fde-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="27fde-107">Prerequisites</span></span>  
 <span data-ttu-id="27fde-108">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27fde-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-bam-archive-database-name-sql-server-2008-r2sp1"></a><span data-ttu-id="27fde-109">Para actualizar referencias al nombre de base de datos de archivo de BAM (SQL Server 2008 R2 o SP1)</span><span class="sxs-lookup"><span data-stu-id="27fde-109">To update references to the BAM Archive database name (SQL Server 2008 R2/SP1)</span></span>  
  
1.  <span data-ttu-id="27fde-110">Detenga todos los paquetes DTS de mantenimiento de datos y de actualización de cubos de BAM, o impida su ejecución hasta que se haya restaurado la base de datos BAMArchive.</span><span class="sxs-lookup"><span data-stu-id="27fde-110">Stop any BAM cube update and data maintenance DTS packages, or prevent them from running until you have restored the BAMArchive database.</span></span>  
  
2.  <span data-ttu-id="27fde-111">Detenga el servicio de aplicaciones de BizTalk (que incluye el servicio de bus de eventos de SAE) para que no intente importar más datos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="27fde-111">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the database.</span></span>  
  
    1.  <span data-ttu-id="27fde-112">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="27fde-112">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="27fde-113">Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** de servicio y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="27fde-113">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="27fde-114">Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="27fde-114">Click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
4.  <span data-ttu-id="27fde-115">En SQL Server Business Intelligence Development Studio, cree un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="27fde-115">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="27fde-116">Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="27fde-116">Click **File**, click **New**, and then click **Project**.</span></span>  
  
5.  <span data-ttu-id="27fde-117">En el **nuevo proyecto** cuadro de diálogo **plantillas**, haga clic en **proyecto de Integration Services**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27fde-117">In the **New Project** dialog box, in **Templates**, click **Integration Services Project**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="27fde-118">En el **proyecto de Integration Services** cuadro de diálogo **el Explorador de soluciones**, haga clic en **paquetes SSIS**y, a continuación, haga clic en **Agregar paquete existente**.</span><span class="sxs-lookup"><span data-stu-id="27fde-118">In the **Integration Services Project** dialog box, in **Solution Explorer**, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
7.  <span data-ttu-id="27fde-119">En el **Agregar copia de paquete existente** cuadro de diálogo, en la **Server** lista desplegable, seleccione el servidor que contiene el paquete BAM_DM.</span><span class="sxs-lookup"><span data-stu-id="27fde-119">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_DM package.</span></span>  
  
8.  <span data-ttu-id="27fde-120">En **ruta de acceso del paquete**, haga clic en el botón de puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="27fde-120">In **Package Path**, click the ellipses button.</span></span>  
  
9. <span data-ttu-id="27fde-121">En el **paquete SSIS** diálogo cuadro, seleccione el paquete BAM_DM, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27fde-121">In the **SSIS Package** dialog box, select the BAM_DM package, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="27fde-122">Con ello, el paquete aparecerá en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="27fde-122">The package is now listed in Solution Explorer.</span></span>  
  
10. <span data-ttu-id="27fde-123">En **el Explorador de soluciones**, haga doble clic en el paquete BAM_DM.</span><span class="sxs-lookup"><span data-stu-id="27fde-123">In **Solution Explorer**, double-click the BAM_DM package.</span></span> <span data-ttu-id="27fde-124">En **administradores de conexión**, haga doble clic en el número de la base de datos 3 (base de datos MSDB).</span><span class="sxs-lookup"><span data-stu-id="27fde-124">In **Connection Managers**, double-click database number 3 (MSDB database).</span></span>  
  
11. <span data-ttu-id="27fde-125">En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor MSDB y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27fde-125">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the MSDB server, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="27fde-126">Haga clic en el **Explorador de paquetes** ficha, haga doble clic en el **Variables** carpeta y actualice los valores para el nombre del servidor de importación principal de principal y de importación en nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="27fde-126">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the primary import server name and primary import database name.</span></span>  
  
13. <span data-ttu-id="27fde-127">Haga clic en **archivo**y, a continuación, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="27fde-127">Click **File**, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="27fde-128">En **Microsoft SQL Server Management Studio**, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="27fde-128">In **Microsoft SQL Server Management Studio**, click **Connect**.</span></span>  
  
15. <span data-ttu-id="27fde-129">Haga clic en **Integration Services**, haga doble clic en **paquetes almacenados**, haga clic en **MSDB**, haga clic en el paquete BAM_DM y, a continuación, haga clic en **Importar paquete**.</span><span class="sxs-lookup"><span data-stu-id="27fde-129">Click **Integration Services**, double-click **Stored Packages**, click **MSDB**, right-click the BAM_DM package, and then click **Import Package**.</span></span>  
  
16. <span data-ttu-id="27fde-130">En el **Importar paquete** cuadro de diálogo **ubicación del paquete**, seleccione **sistema de archivos**.</span><span class="sxs-lookup"><span data-stu-id="27fde-130">In the **Import Package** dialog box, in **Package location**, select **File System**.</span></span>  
  
17. <span data-ttu-id="27fde-131">En **ruta de acceso del paquete**, navegue al proyecto guardado, seleccione la BAM_DM\*archivo DTSX y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="27fde-131">In **Package Path**, navigate to your saved project, select the BAM_DM\*.dtsx file, and then click **Open**.</span></span>  
  
18. <span data-ttu-id="27fde-132">Haga clic dentro de la **nombre del paquete** cuadro para rellenar automáticamente el cuadro.</span><span class="sxs-lookup"><span data-stu-id="27fde-132">Click inside the **Package Name** box to automatically populate the box.</span></span>  
  
19. <span data-ttu-id="27fde-133">Haga clic en **Aceptar**y, a continuación, haga clic en **Sí** para sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="27fde-133">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
20. <span data-ttu-id="27fde-134">Reinicie el servicio de aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="27fde-134">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="27fde-135">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="27fde-135">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="27fde-136">Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** de servicio y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="27fde-136">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Start**.</span></span>  
  
21. <span data-ttu-id="27fde-137">Habilite todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE.</span><span class="sxs-lookup"><span data-stu-id="27fde-137">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27fde-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="27fde-138">See Also</span></span>  
 [<span data-ttu-id="27fde-139">Copia de seguridad y restauración de BAM</span><span class="sxs-lookup"><span data-stu-id="27fde-139">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)