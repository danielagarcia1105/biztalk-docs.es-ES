---
title: "Cómo purgar datos manualmente desde la base de datos de seguimiento de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging, manually
- purging, warnings
ms.assetid: f350d850-5034-4166-940c-8d10b7b445fb
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75cc2fa6a7e4f6318818534f6b3f99323f1d8ddf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manually-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="d22f9-102">Cómo purgar datos manualmente desde la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d22f9-102">How to Manually Purge Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="d22f9-103">El trabajo DTA Archive and Purge SQL Server Agent reduce la necesidad de purgar manualmente los datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb) debido a la continua purga de la base de datos y a la compactación de los datos de seguimiento almacenados.</span><span class="sxs-lookup"><span data-stu-id="d22f9-103">The DTA Archive and Purge SQL Server Agent job reduces the need to manually purge data from the BizTalk Tracking (BizTalkDTADb) database due to continuous purging of the database and compaction of stored tracking data.</span></span> <span data-ttu-id="d22f9-104">Es posible que tenga que efectuar una purga manual cuando la base de datos de seguimiento de BizTalk (BizTalkDTADb) haya crecido tanto como para ocasionar una pérdida continua de rendimiento y el trabajo DTA Archive and Purge no pueda hacer frente al crecimiento de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d22f9-104">You might need to manually purge data if your BizTalk Tracking (BizTalkDTADb) database has grown so much that sustained performance degradation is occurring and the DTA Archive and Purge job is unable to keep up with the database growth.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d22f9-105">Este procedimiento elimina todos los datos de seguimiento de las instancias finalizadas de la base de datos de seguimiento de BizTalk (BizTalkDTADb), independientemente de la hora de finalización.</span><span class="sxs-lookup"><span data-stu-id="d22f9-105">Performing this procedure deletes all tracking data for completed instances from the BizTalk Tracking (BizTalkDTADb) database regardless of completion time.</span></span> <span data-ttu-id="d22f9-106">Antes de llevar a cabo este procedimiento, es conveniente que archive la base de datos de seguimiento de BizTalk (BizTalkDTADb) separada del resto de bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d22f9-106">Before performing this procedure, you should archive the BizTalk Tracking (BizTalkDTADb) database separately from the other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d22f9-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d22f9-107">Prerequisites</span></span>  
 <span data-ttu-id="d22f9-108">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d22f9-108">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-manually-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="d22f9-109">Procedimiento para purgar datos desde la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d22f9-109">To manually purge data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="d22f9-110">Haga una copia de seguridad de las bases de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d22f9-110">Backup your BizTalk Server databases.</span></span>  
  
2.  <span data-ttu-id="d22f9-111">Archive la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="d22f9-111">Archive the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
3.  <span data-ttu-id="d22f9-112">Abra la Consola de servicios.</span><span class="sxs-lookup"><span data-stu-id="d22f9-112">Open the Services console.</span></span> <span data-ttu-id="d22f9-113">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-113">Click **Start**, click **Run**, and then type **services.msc**.</span></span> <span data-ttu-id="d22f9-114">Si un **User Account Control** se muestra el cuadro de diálogo, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-114">If a **User Account Control** dialog is displayed, click **Continue**.</span></span>  
  
4.  <span data-ttu-id="d22f9-115">Cuando aparezca la Consola de servicios, busque y detenga cada uno de los siguientes servicios.</span><span class="sxs-lookup"><span data-stu-id="d22f9-115">When the Services console appears, locate and then stop each of the following services.</span></span> <span data-ttu-id="d22f9-116">Para detener un servicio, haga clic en la fila de servicio en la **servicios** panel y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-116">To stop a service, right-click the service row in the **Services** pane, and then click **Stop**.</span></span>  
  
    -   <span data-ttu-id="d22f9-117">BizTalkServiceBizTalkGroup: BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="d22f9-117">BizTalkServiceBizTalkGroup : BizTalkServerApplication</span></span>  
  
    -   <span data-ttu-id="d22f9-118">Servicio de inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="d22f9-118">Enterprise Single Sign-On Service</span></span>  
  
         <span data-ttu-id="d22f9-119">Si el BizTalkServiceBizTalkGroup: servicio BizTalkServerApplication está en ejecución al intentar apagar el único inicio de sesión de servicio empresarial, un **detener otros servicios** se mostrará el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d22f9-119">If the BizTalkServiceBizTalkGroup : BizTalkServerApplication service is running when you try to shut down the Enterprise Singe Sign-On Service, a **Stop Other Services** dialog will be displayed.</span></span> <span data-ttu-id="d22f9-120">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-120">Click **Yes**.</span></span>  
  
    -   <span data-ttu-id="d22f9-121">Servicio de actualización de motor de reglas</span><span class="sxs-lookup"><span data-stu-id="d22f9-121">Rule Engine Update Service</span></span>  
  
5.  <span data-ttu-id="d22f9-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span> <span data-ttu-id="d22f9-123">Si un **User Account Control** se muestra el cuadro de diálogo, compruebe que la acción descrita es la esperada y, a continuación, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-123">If a **User Account Control** dialog is displayed, verify that the action described is what you want, and then click **Continue**.</span></span>  
  
6.  <span data-ttu-id="d22f9-124">En el **consola de administración de BizTalk Server** en el panel Explorador del lado izquierdo de la ventana, haga doble clic en **grupo de BizTalk** para expandir la lista por debajo de él, a continuación, haga doble clic en **plataforma Configuración de**y, a continuación, haga clic en **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-124">In the **BizTalk Server Administration Console** in the explorer pane on the left side of the window, double-click **BizTalk Group** to expand the list below it, then double-click **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="d22f9-125">Esto mostrará una lista de instancias de host (el **instancias de Host** panel) y propiedades relacionadas, en el lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="d22f9-125">This will display a list of host instances (the **Host Instances** pane) and related properties, on the right side of the screen.</span></span>  
  
7.  <span data-ttu-id="d22f9-126">En el **instancias de Host** panel, haga clic en cada instancia de host y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-126">In the **Host Instances** pane, right-click each running host instance, and then click **Stop**.</span></span>  
  
8.  <span data-ttu-id="d22f9-127">Haga clic en **iniciar**, vaya a **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-127">Click **Start**, go to **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="d22f9-128">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="d22f9-128">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="d22f9-129">**net stop iisadmin /y**</span><span class="sxs-lookup"><span data-stu-id="d22f9-129">**net stop iisadmin /y**</span></span>  
  
     <span data-ttu-id="d22f9-130">Esto detiene el servicio IIS Admin y todos los servicios dependientes uno a uno y evita que los datos nuevos se escriban en BizTalkDTADb, mientras que los datos se están purgando.</span><span class="sxs-lookup"><span data-stu-id="d22f9-130">This stops the IIS Admin Service and all dependent services, one-by-one and prevents new data from being written to the BizTalkDTADb while data is being purged.</span></span> <span data-ttu-id="d22f9-131">Anote la lista de servicios a medida que se van deteniendo.</span><span class="sxs-lookup"><span data-stu-id="d22f9-131">Write down the list of services as each one is stopped.</span></span> <span data-ttu-id="d22f9-132">Necesitará utilizar esta lista de servicios más adelante para reiniciar IIS.</span><span class="sxs-lookup"><span data-stu-id="d22f9-132">You will need to use this list of services later when you restart IIS.</span></span>  
  
     <span data-ttu-id="d22f9-133">A continuación se ofrece un ejemplo de la salida obtenida tras ejecutar este comando (la lista de servicios dependientes puede variar):</span><span class="sxs-lookup"><span data-stu-id="d22f9-133">Below is an example of the output you will see after issuing this command (the dependent services listed on your computer may vary):</span></span>  
  
    ```  
    The following services are dependent on the IIS Admin Service service. Stopping the IIS Admin Service service will also stop these services.  
    World Wide Web Publishing Service  
    HTTP SSL  
    ```  
  
10. <span data-ttu-id="d22f9-134">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-134">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
11. <span data-ttu-id="d22f9-135">En el **conectar al servidor** cuadro de diálogo, especifique el nombre del servidor SQL donde reside la base de datos de seguimiento de BizTalk (BizTalkDTADb) y el tipo de autenticación adecuado y, a continuación, haga clic en **conectar** a conectar con el servidor SQL Server apropiado.</span><span class="sxs-lookup"><span data-stu-id="d22f9-135">In the **Connect to Server** dialog box, specify the name of the SQL Server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
12. <span data-ttu-id="d22f9-136">En **Microsoft SQL Server Management Studio**, haga doble clic en **bases de datos**, haga doble clic en el **BizTalkDTADb** base de datos, haga doble clic en  **Programación**y, a continuación, haga clic en **procedimientos almacenados**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-136">In **Microsoft SQL Server Management Studio**, double-click **Databases**, double-click the **BizTalkDTADb** database, double-click **Programmability**, and then click **Stored Procedures**.</span></span>  
  
13. <span data-ttu-id="d22f9-137">En el **detalles del explorador de objetos** panel, haga clic en **dtasp_PurgeAllCompletedTrackingData**y, a continuación, haga clic en **Ejecutar procedimiento almacenado**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-137">In the **Object Explorer Details** pane, right-click **dtasp_PurgeAllCompletedTrackingData**, and then click **Execute Stored Procedure**.</span></span>  
  
14. <span data-ttu-id="d22f9-138">En el **Ejecutar procedimiento** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-138">In the **Execute Procedure** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="d22f9-139">Este procedimiento almacenado elimina todos los datos de seguimiento relativos a las instancias finalizadas, independientemente de su hora de finalización.</span><span class="sxs-lookup"><span data-stu-id="d22f9-139">This stored procedure deletes all tracking data associated with completed instances regardless of their completion time.</span></span>  
  
15. <span data-ttu-id="d22f9-140">Abra Servicios.</span><span class="sxs-lookup"><span data-stu-id="d22f9-140">Open Services.</span></span> <span data-ttu-id="d22f9-141">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-141">Click **Start**, click **Run**, and then type **services.msc**.</span></span> <span data-ttu-id="d22f9-142">Si un **User Account Control** se muestra el cuadro de diálogo, compruebe que la acción descrita es la esperada y, a continuación, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-142">If a **User Account Control** dialog is displayed, verify that the action described is what you want, and then click **Continue**.</span></span>  
  
16. <span data-ttu-id="d22f9-143">Haga clic en cada uno de los servicios siguientes y, a continuación, haga clic en **iniciar**:</span><span class="sxs-lookup"><span data-stu-id="d22f9-143">Right-click each of the following services, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="d22f9-144">BizTalkServiceBizTalkGroup: BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="d22f9-144">BizTalkServiceBizTalkGroup : BizTalkServerApplication</span></span>  
  
    -   <span data-ttu-id="d22f9-145">Servicio de inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="d22f9-145">Enterprise Single Sign-On Service</span></span>  
  
    -   <span data-ttu-id="d22f9-146">Servicio de actualización de motor de reglas</span><span class="sxs-lookup"><span data-stu-id="d22f9-146">Rule Engine Update Service</span></span>  
  
17. <span data-ttu-id="d22f9-147">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-147">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
18. <span data-ttu-id="d22f9-148">En el **consola de administración de BizTalk Server**, haga doble clic en el **grupo de BizTalk**, haga doble clic en **configuración de plataforma**y, a continuación, haga clic en **Host Instancias**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-148">In the **BizTalk Server Administration Console**, double-click the **BizTalk Group**, double-click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
19. <span data-ttu-id="d22f9-149">En el **detalles del explorador de objetos** panel, haga clic en cada instancia de host detenida y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="d22f9-149">In the **Object Explorer Details** pane, right-click each stopped host instance, and then click **Start**.</span></span>  
  
20. <span data-ttu-id="d22f9-150">Inicie un símbolo del sistema, como se describe en el paso 8 anterior.</span><span class="sxs-lookup"><span data-stu-id="d22f9-150">Start a command prompt, as described in step 8 above.</span></span>  
  
21. <span data-ttu-id="d22f9-151">En el símbolo del sistema, reinicie cada uno de los servicios IIS que detuvo en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="d22f9-151">At the command prompt, restart each of the IIS services that you stopped in step 4.</span></span> <span data-ttu-id="d22f9-152">Tipo:</span><span class="sxs-lookup"><span data-stu-id="d22f9-152">Type:</span></span>  
  
     <span data-ttu-id="d22f9-153">**Net start**  *\<IISserviceName >*</span><span class="sxs-lookup"><span data-stu-id="d22f9-153">**net start** *\<IISserviceName>*</span></span>  
  
     <span data-ttu-id="d22f9-154">Donde  *\<IISserviceName >* es el nombre del servicio IIS que desea reiniciar.</span><span class="sxs-lookup"><span data-stu-id="d22f9-154">Where *\<IISserviceName>* is the name of the IIS service you want to restart.</span></span> <span data-ttu-id="d22f9-155">Deberá repetir este comando para cada uno de los servicios IIS.</span><span class="sxs-lookup"><span data-stu-id="d22f9-155">You must repeat this command for each of the IIS services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d22f9-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="d22f9-156">See Also</span></span>  
 <span data-ttu-id="d22f9-157">[Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="d22f9-157">[Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span></span>  
 <span data-ttu-id="d22f9-158">[Copia de seguridad y restaurar bases de datos de servidor BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="d22f9-158">[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="d22f9-159">Cómo iniciar, detener, pausar, reanudar o reiniciar servicios de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d22f9-159">How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services</span></span>](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)