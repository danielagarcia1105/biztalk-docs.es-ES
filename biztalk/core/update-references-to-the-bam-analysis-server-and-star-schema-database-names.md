---
title: Cómo actualizar referencias al servidor de análisis BAM y nombres de base de datos de esquema de estrella | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- restoring [BAM], Analysis database
- Analysis database [BAM], restoring
- restoring, BAM
- restoring [BAM], updating references
- BAM, restoring
- Analysis database [BAM], updating references
ms.assetid: cbe5e500-0a25-427e-bc76-1eae24b3e5f3
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4f98129efd2f7c027ecb6c3e69d494ff2e96e8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287452"
---
# <a name="how-to-update-references-to-the-bam-analysis-server-and-star-schema-database-names"></a><span data-ttu-id="fa5f9-102">Actualización de referencias a los nombres de base de datos de esquema de estrella y servidor de análisis de BAM</span><span class="sxs-lookup"><span data-stu-id="fa5f9-102">How to Update References to the BAM Analysis Server and Star Schema Database Names</span></span>
<span data-ttu-id="fa5f9-103">Si ha realizado copias de seguridad de las bases de datos BAMAnalysis y BAMStarSchema, podrá restaurarlas en un equipo distinto y cambiar el nombre a esas copias de seguridad en el caso de que se produzca un error de datos o del sistema.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-103">If you backed up your BAMAnalysis and BAMStarSchema databases, in the event of a system or data failure you can restore that backup to a different computer and you can rename the backup.</span></span>  
  
 <span data-ttu-id="fa5f9-104">Para restaurar las bases de datos del servidor de análisis de BAM o BAMStarSchema, siga los pasos descritos en [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md).</span><span class="sxs-lookup"><span data-stu-id="fa5f9-104">To restore the BAM Analysis Server or BAMStarSchema databases, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="fa5f9-105">Además, tendrá que actualizar los paquetes de Servicios de transformación de datos (DTS) de BAM con el nuevo nombre de base de datos y de servidor.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-105">In addition, you must update the BAM Data Transformation Services (DTS) packages with the new server name and database name.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fa5f9-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fa5f9-106">Prerequisites</span></span>  
 <span data-ttu-id="fa5f9-107">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa5f9-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-bam-analysis-server-and-bam-star-schema-database-name-sql-server-2008-r2sp1"></a><span data-ttu-id="fa5f9-108">Para actualizar las referencias al nombre de base de datos de servidor de análisis de BAM y de esquema de estrella de BAM (SQL Server 2008 R2 o SP1)</span><span class="sxs-lookup"><span data-stu-id="fa5f9-108">To update references to the BAM Analysis Server and BAM Star Schema database name (SQL Server 2008 R2/SP1)</span></span>  
  
1.  <span data-ttu-id="fa5f9-109">Detenga todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de BAM, o impida su ejecución hasta que se hayan restaurado las bases de datos BAMAnalysis o BAMStarSchema.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-109">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAMAnalysis or BAMStarSchema databases.</span></span>  
  
2.  <span data-ttu-id="fa5f9-110">Detenga el servicio de aplicaciones de BizTalk (que incluye el servicio de bus de sucesos BAM) para que no intente importar más datos en las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-110">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the databases.</span></span>  
  
    1.  <span data-ttu-id="fa5f9-111">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-111">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="fa5f9-112">Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** de servicio y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-112">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Stop**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="fa5f9-113">Otra manera de detener un servicio es usar el **Net Stop** comando.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-113">Another way to stop a service is to use the **Net Stop** command.</span></span> <span data-ttu-id="fa5f9-114">Para detener el servicio de BizTalk con Net Stop, abra un **símbolo** (si usa Windows Server 2008 o Windows Vista, inicie el símbolo mediante **ejecutar como administrador**) y escriba lo siguiente: `Net Stop BTSSvc$BizTalkServerApplication` a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-114">To stop the BizTalk service using Net Stop, open a **Command Prompt** (If using Windows Server 2008 or Windows Vista, start the Command Prompt using **Run As Administrator**) and type the following: `Net Stop BTSSvc$BizTalkServerApplication` then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="fa5f9-115">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-115">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
4.  <span data-ttu-id="fa5f9-116">En SQL Server Business Intelligence Development Studio, cree un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-116">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="fa5f9-117">Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-117">Click **File**, click **New**, and then click **Project**.</span></span>  
  
5.  <span data-ttu-id="fa5f9-118">En el **nuevo proyecto** cuadro de diálogo **plantillas**, haga clic en **proyecto de Integration Services**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-118">In the **New Project** dialog box, in **Templates**, click **Integration Services Project**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="fa5f9-119">En el **proyecto de Integration Services** cuadro de diálogo **el Explorador de soluciones**, haga clic en **paquetes SSIS**y, a continuación, haga clic en **Agregar paquete existente**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-119">In the **Integration Services Project** dialog box, in **Solution Explorer**, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
7.  <span data-ttu-id="fa5f9-120">En el **Agregar copia de paquete existente** cuadro de diálogo, en la **Server** lista desplegable, seleccione el servidor que contiene el paquete BAM_AN.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-120">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN package.</span></span>  
  
8.  <span data-ttu-id="fa5f9-121">En **ruta de acceso del paquete**, haga clic en el botón de puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-121">In **Package Path**, click the ellipses button.</span></span>  
  
9. <span data-ttu-id="fa5f9-122">En el **paquete SSIS** diálogo cuadro, seleccione el paquete BAM_AN, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-122">In the **SSIS Package** dialog box, select the BAM_AN package, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="fa5f9-123">Con ello, el paquete aparecerá en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-123">The package is now listed in Solution Explorer.</span></span>  
  
10. <span data-ttu-id="fa5f9-124">En **el Explorador de soluciones**, haga doble clic en el paquete BAM_AN.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-124">In **Solution Explorer**, double-click the BAM_AN package.</span></span> <span data-ttu-id="fa5f9-125">En **administradores de conexión**, haga doble clic en el número de la base de datos 3 (base de datos MSDB).</span><span class="sxs-lookup"><span data-stu-id="fa5f9-125">In **Connection Managers**, double-click database number 3 (MSDB database).</span></span>  
  
11. <span data-ttu-id="fa5f9-126">En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor MSDB y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-126">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the MSDB server, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="fa5f9-127">Haga clic en el **Explorador de paquetes** ficha, haga doble clic en el **Variables** carpeta y actualice los valores para el nombre del servidor de importación principal de principal y de importación en nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-127">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the primary import server name and primary import database name.</span></span>  
  
13. <span data-ttu-id="fa5f9-128">Haga clic en **archivo**y, a continuación, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-128">Click **File**, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="fa5f9-129">En **Microsoft SQL Server Management Studio**, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-129">In **Microsoft SQL Server Management Studio**, click **Connect**.</span></span>  
  
15. <span data-ttu-id="fa5f9-130">Haga clic en **Integration Services**, haga doble clic en **paquetes almacenados**, haga clic en **MSDB**, haga clic en el paquete BAM_AN y, a continuación, haga clic en **Importar paquete**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-130">Click **Integration Services**, double-click **Stored Packages**, click **MSDB**, right-click the BAM_AN package, and then click **Import Package**.</span></span>  
  
16. <span data-ttu-id="fa5f9-131">En el **Importar paquete** cuadro de diálogo **ubicación del paquete**, seleccione **sistema de archivos**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-131">In the **Import Package** dialog box, in **Package location**, select **File System**.</span></span>  
  
17. <span data-ttu-id="fa5f9-132">En **ruta de acceso del paquete**, navegue al proyecto guardado, seleccione la BAM_AN\*archivo DTSX y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-132">In **Package Path**, navigate to your saved project, select the BAM_AN\*.dtsx file, and then click **Open**.</span></span>  
  
18. <span data-ttu-id="fa5f9-133">Haga clic dentro de la **nombre del paquete** cuadro para rellenar automáticamente el cuadro.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-133">Click inside the **Package Name** box to automatically populate the box.</span></span>  
  
19. <span data-ttu-id="fa5f9-134">Haga clic en **Aceptar**y, a continuación, haga clic en **Sí** para sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-134">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
20. <span data-ttu-id="fa5f9-135">Reinicie el servicio de aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-135">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="fa5f9-136">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-136">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="fa5f9-137">Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** de servicio y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-137">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Start**.</span></span>  
  
21. <span data-ttu-id="fa5f9-138">Habilite todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE.</span><span class="sxs-lookup"><span data-stu-id="fa5f9-138">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa5f9-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa5f9-139">See Also</span></span>  
 [<span data-ttu-id="fa5f9-140">Copia de seguridad y restauración de BAM</span><span class="sxs-lookup"><span data-stu-id="fa5f9-140">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)