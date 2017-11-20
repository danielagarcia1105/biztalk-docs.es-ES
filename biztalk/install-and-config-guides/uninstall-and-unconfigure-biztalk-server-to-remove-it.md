---
title: "Desinstalar y quitar la configuración de BizTalk Server para quitarlo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9ea8757-ca49-421b-bf7b-89344201398a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce643460d7c5256829624de5ba4c32d664c26ac3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="uninstall-and-unconfigure-biztalk-server-to-remove-it"></a><span data-ttu-id="e533a-102">Desinstalar y quitar la configuración de BizTalk Server para quitarlo</span><span class="sxs-lookup"><span data-stu-id="e533a-102">Uninstall and unconfigure BizTalk Server to remove it</span></span>
<span data-ttu-id="e533a-103">Desinstale y quite la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e533a-103">Uninstall and unconfigure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> 
  
##  <span data-ttu-id="e533a-104"><a name="BKMK_BeforeYouBegin"></a> Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e533a-104"><a name="BKMK_BeforeYouBegin"></a> Before You Begin</span></span>  
  
-   <span data-ttu-id="e533a-105">Antes de la desinstalación, debe quitar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e533a-105">Before you uninstall, you must un-configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e533a-106">En este tema se enumeran los diferentes trabajos, paquetes y bases de datos que deben eliminarse.</span><span class="sxs-lookup"><span data-stu-id="e533a-106">This topic lists the different jobs, packages, and databases to be deleted.</span></span> <span data-ttu-id="e533a-107">Los nombres que figuran son los nombres predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e533a-107">The names listed are the default names.</span></span> <span data-ttu-id="e533a-108">Puede que su entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] use nombres no predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e533a-108">Your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment may be using non-default names.</span></span>  
  
-   <span data-ttu-id="e533a-109">Siga los pasos en el orden que se indica.</span><span class="sxs-lookup"><span data-stu-id="e533a-109">Complete the steps in the order listed.</span></span> <span data-ttu-id="e533a-110">De lo contrario, la desinstalación no será completa.</span><span class="sxs-lookup"><span data-stu-id="e533a-110">Otherwise, the uninstall is not complete.</span></span>  
  
##  <span data-ttu-id="e533a-111"><a name="BKMK_Unconfigure"></a> Quitar la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e533a-111"><a name="BKMK_Unconfigure"></a> Un-configure BizTalk Server</span></span>  
  
1.  <span data-ttu-id="e533a-112">Haga clic con el botón derecho en **Configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e533a-112">Right-click **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration**, and select **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="e533a-113">En la configuración, seleccione **Quitar la configuración de características**.</span><span class="sxs-lookup"><span data-stu-id="e533a-113">In the Configuration, select **Unconfigure Features**.</span></span>  
  
3.  <span data-ttu-id="e533a-114">Seleccione las características cuya configuración quiere quitar y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e533a-114">Select the features you want to unconfigure, and select **OK**.</span></span> <span data-ttu-id="e533a-115">Si se le solicita que continúe, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e533a-115">If prompted to proceed, select **Yes**.</span></span> <span data-ttu-id="e533a-116">Para quitarlo todo del equipo, puede seleccionar todas las características.</span><span class="sxs-lookup"><span data-stu-id="e533a-116">To  remove everything from the computer, you can select all the features.</span></span>  
  
4.  <span data-ttu-id="e533a-117">Seleccione **Siguiente** y continúe con el asistente.</span><span class="sxs-lookup"><span data-stu-id="e533a-117">Select **Next**, and continue through the wizard.</span></span>  
  
 <span data-ttu-id="e533a-118">Se genera un archivo de registro en una carpeta temporal, similar a la siguiente: C:\Usuarios\nombreDeUsuario\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log.</span><span class="sxs-lookup"><span data-stu-id="e533a-118">A log file is generated in a temp folder, similar to: C:\Users\username\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log.</span></span>  
  
##  <span data-ttu-id="e533a-119"><a name="BKMK_Uninstall"></a> Desinstalar los componentes en tiempo de ejecución de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e533a-119"><a name="BKMK_Uninstall"></a> Uninstall BizTalk Server Runtime Components</span></span>  
  
1.  <span data-ttu-id="e533a-120">Abra **Programas y características**.</span><span class="sxs-lookup"><span data-stu-id="e533a-120">Open **Programs and Features**.</span></span>  
  
2.  <span data-ttu-id="e533a-121">Seleccione en la lista su versión de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y haga clic en **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="e533a-121">Select  your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] version from the list, and  **Uninstall**.</span></span>  
  
3.  <span data-ttu-id="e533a-122">Seleccione **Quitar** y continúe con el asistente.</span><span class="sxs-lookup"><span data-stu-id="e533a-122">**Remove** it, and continue through the wizard.</span></span>  
  
 <span data-ttu-id="e533a-123">Se genera un archivo de registro en una carpeta temporal, similar a la siguiente: \Usuarios\\*nombreDeUsuario*\AppData\Local\Setup(083016 xxxxxx).htm.</span><span class="sxs-lookup"><span data-stu-id="e533a-123">A log file is generated in a temp folder, similar to: C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span></span>  
  
##  <span data-ttu-id="e533a-124"><a name="BKMK_UninstallSSO"></a> Desinstalar Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="e533a-124"><a name="BKMK_UninstallSSO"></a> Uninstall Enterprise Single Sign-On</span></span>  
  
1.  <span data-ttu-id="e533a-125">Abra **Programas y características**.</span><span class="sxs-lookup"><span data-stu-id="e533a-125">Open **Programs and Features**.</span></span>  
  
2.  <span data-ttu-id="e533a-126">Seleccione **Microsoft Enterprise Single Sign-On** en la lista y haga clic en **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="e533a-126">Select **Microsoft Enterprise Single Sign-On** from the list, and **Uninstall**.</span></span>  
  
3.  <span data-ttu-id="e533a-127">Seleccione **Quitar** y continúe con el asistente.</span><span class="sxs-lookup"><span data-stu-id="e533a-127">**Remove** it, and continue through the wizard.</span></span>  
  
 <span data-ttu-id="e533a-128">Se genera un archivo de registro en una carpeta temporal, similar a la siguiente: \Usuarios\\*nombreDeUsuario*\AppData\Local\Setup(083016 xxxxxx).htm.</span><span class="sxs-lookup"><span data-stu-id="e533a-128">A log file is generated in a temp folder, similar to: C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span></span>  
  
##  <span data-ttu-id="e533a-129"><a name="BKMK_RemoveRemaining"></a> Eliminar trabajos de SQL, bases de datos y paquetes</span><span class="sxs-lookup"><span data-stu-id="e533a-129"><a name="BKMK_RemoveRemaining"></a> Delete SQL jobs, databases, and packages</span></span>  
  
#### <a name="delete-sql-server-agent-jobs"></a><span data-ttu-id="e533a-130">Eliminar trabajos del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="e533a-130">Delete SQL Server agent jobs</span></span>  
  
1.  <span data-ttu-id="e533a-131">Abra **SQL Server Management Studio** como administrador.</span><span class="sxs-lookup"><span data-stu-id="e533a-131">Open **SQL Server Management Studio** as Administrator.</span></span>  
  
2.  <span data-ttu-id="e533a-132">En **SQL Server Management Studio**, conéctese al **Motor de base de datos**, expanda **Agente de SQL Server** y expanda **Trabajos**.</span><span class="sxs-lookup"><span data-stu-id="e533a-132">In **SQL Server Management Studio**, connect to **Database Engine**, expand **SQL Server Agent**, and expand  **Jobs**.</span></span>  
  
3.  <span data-ttu-id="e533a-133">Elimine los trabajos siguientes (haga clic con el botón derecho en el trabajo y seleccione **Eliminar**):</span><span class="sxs-lookup"><span data-stu-id="e533a-133">Delete the following jobs (right-click the job, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="e533a-134">Copia de seguridad de BizTalk Server (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="e533a-134">Backup BizTalk Server (BizTalkMgmtDb)</span></span>  
  
    -   <span data-ttu-id="e533a-135">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="e533a-135">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>  
  
    -   <span data-ttu-id="e533a-136">DTA Purge and Archive (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="e533a-136">DTA Purge and Archive (BizTalkDTADb)</span></span>  
  
    -   <span data-ttu-id="e533a-137">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="e533a-137">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="e533a-138">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="e533a-138">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="e533a-139">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="e533a-139">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="e533a-140">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="e533a-140">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="e533a-141">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="e533a-141">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="e533a-142">Supervisar el servidor BizTalk Server (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="e533a-142">Monitor BizTalk Server (BizTalkMgmtDb)</span></span>  
  
    -   <span data-ttu-id="e533a-143">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="e533a-143">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="e533a-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="e533a-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="e533a-145">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="e533a-145">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>  
  
    -   <span data-ttu-id="e533a-146">TrackedMessages_Copy_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="e533a-146">TrackedMessages_Copy_BizTalkMsgBoxDb</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e533a-147">Si ha implementado BAM, también debe quitar la tabla bam_\<*nombre del cubo*> _\<*nombre de la vista*> trabajos.</span><span class="sxs-lookup"><span data-stu-id="e533a-147">If you deployed BAM, you may also need to remove the bam_\<*Cube Name*>_\<*View Name*> job.</span></span>  
  
#### <a name="delete-biztalk-server-databases"></a><span data-ttu-id="e533a-148">Eliminar bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e533a-148">Delete BizTalk Server databases</span></span>  
  
1.  <span data-ttu-id="e533a-149">En el **Explorador de objetos**, expanda **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="e533a-149">In **Object Explorer**, expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="e533a-150">Elimine las bases de datos siguientes (haga clic con el botón derecho en la base de datos y seleccione **Eliminar**):</span><span class="sxs-lookup"><span data-stu-id="e533a-150">Delete the following databases (right-click the database, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="e533a-151">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="e533a-151">BAMArchive</span></span>  
  
    -   <span data-ttu-id="e533a-152">BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="e533a-152">BAMPrimaryImport</span></span>  
  
    -   <span data-ttu-id="e533a-153">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="e533a-153">BAMStarSchema</span></span>  
  
    -   <span data-ttu-id="e533a-154">BizTalkDTADb</span><span class="sxs-lookup"><span data-stu-id="e533a-154">BizTalkDTADb</span></span>  
  
    -   <span data-ttu-id="e533a-155">BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="e533a-155">BizTalkMgmtDb</span></span>  
  
    -   <span data-ttu-id="e533a-156">BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="e533a-156">BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="e533a-157">BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="e533a-157">BizTalkRuleEngineDb</span></span>  
  
    -   <span data-ttu-id="e533a-158">SSODB</span><span class="sxs-lookup"><span data-stu-id="e533a-158">SSODB</span></span>  
  
#### <a name="remove-sql-server-integration-services-packages"></a><span data-ttu-id="e533a-159">Eliminar paquetes de SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="e533a-159">Remove SQL Server Integration Services packages</span></span>  
  
1.  <span data-ttu-id="e533a-160">En el **Explorador de objetos**, **conéctese** a **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="e533a-160">In **Object Explorer**,  **Connect** to **Integration Services**.</span></span>  
  
2.  <span data-ttu-id="e533a-161">Expanda **Paquetes almacenados** y **MSDB**.</span><span class="sxs-lookup"><span data-stu-id="e533a-161">Expand **Stored Packages**, and expand **MSDB**.</span></span>  
  
3.  <span data-ttu-id="e533a-162">Elimine los paquetes con los prefijos siguientes (haga clic con el botón derecho en el paquete y seleccione **Eliminar**):</span><span class="sxs-lookup"><span data-stu-id="e533a-162">Delete the packages with the following prefixes (right-click the package, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="e533a-163">BAM_AN_\<*nombre del cubo*></span><span class="sxs-lookup"><span data-stu-id="e533a-163">BAM_AN_\<*Cube Name*></span></span>  
  
    -   <span data-ttu-id="e533a-164">BAM_DM_\<*ver nombre*></span><span class="sxs-lookup"><span data-stu-id="e533a-164">BAM_DM_\<*View Name*></span></span>  
  
