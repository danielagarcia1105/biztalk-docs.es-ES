---
title: Cómo eliminar una base de datos de cuadro de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, MessageBox database
- managing [MessageBox database], deleting
- MessageBox database, deleting
ms.assetid: 51f91fcb-8b97-4b00-9056-6d216c8ccb58
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a025ea29e13ef938a39f9555785177f2c64e922
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023602"
---
# <a name="how-to-delete-a-messagebox-database"></a><span data-ttu-id="139bf-102">Cómo eliminar una base de datos de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="139bf-102">How to Delete a MessageBox Database</span></span>
<span data-ttu-id="139bf-103">Utilice la consola de administración de BizTalk o el Instrumental de administración de Windows (WMI) para quitar una base de datos de cuadro de mensajes de un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="139bf-103">You use the BizTalk Administration Console or Windows Management Instrumentation (WMI) to remove a MessageBox database from a BizTalk group.</span></span> <span data-ttu-id="139bf-104">Puede quitar una base de datos de cuadro de mensajes de un grupo de BizTalk o la puede eliminar por completo de su implementación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="139bf-104">You can remove a MessageBox database from a BizTalk group, or you can delete it from your BizTalk Server deployment entirely.</span></span>  
  
 <span data-ttu-id="139bf-105">Por ejemplo, puede eliminar una base de datos de cuadro de mensajes que ya no utilice, como una base de datos para realizar pruebas.</span><span class="sxs-lookup"><span data-stu-id="139bf-105">For example, you can delete a MessageBox database you are no longer using, such as a database used for testing purposes.</span></span>  
  
 <span data-ttu-id="139bf-106">Existen ocho pasos para quitar completamente y de forma definitiva las bases de datos de cuadro de mensajes de su implementación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="139bf-106">There are eight steps to permanently and completely removing MessageBox databases from your BizTalk Server deployment:</span></span>  
  
1.  <span data-ttu-id="139bf-107">Deshabilitar la publicación de nuevos mensajes.</span><span class="sxs-lookup"><span data-stu-id="139bf-107">Disable new message publication.</span></span>  
  
     <span data-ttu-id="139bf-108">Debe deshabilitar la publicación de mensajes nuevos antes de eliminar una base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="139bf-108">You must disable the publication of new messages before you delete a MessageBox database.</span></span> <span data-ttu-id="139bf-109">Para obtener información acerca de cómo deshabilitar la publicación de nuevos mensajes, vea [cómo deshabilitar la publicación de nuevos mensajes](../core/how-to-disable-new-message-publication.md).</span><span class="sxs-lookup"><span data-stu-id="139bf-109">For information about disabling new message publication, see [How to Disable New Message Publication](../core/how-to-disable-new-message-publication.md).</span></span>  
  
2.  <span data-ttu-id="139bf-110">Esperar a que caduque el intervalo de actualización de la caché.</span><span class="sxs-lookup"><span data-stu-id="139bf-110">Wait for the cache refresh interval to expire.</span></span>  
  
     <span data-ttu-id="139bf-111">Después de deshabilitar la publicación de mensajes nuevos, debe esperar para eliminar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="139bf-111">After you disable the publication of new messages, you must wait before you delete the database.</span></span> <span data-ttu-id="139bf-112">El tiempo de espera se define como el doble de la longitud correspondiente a CacheRefreshInterval.</span><span class="sxs-lookup"><span data-stu-id="139bf-112">The wait time is defined as twice the length of the CacheRefreshInterval.</span></span> <span data-ttu-id="139bf-113">El valor predeterminado de CacheRefreshInterval (intervalo de actualización de la caché) es de 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="139bf-113">The default value of CacheRefreshInterval is 60 seconds.</span></span> <span data-ttu-id="139bf-114">Usa el **propiedades del grupo** cuadro de diálogo para cambiar la actualización de la caché.</span><span class="sxs-lookup"><span data-stu-id="139bf-114">You use the **Group Properties** dialog box to change the Cache Refresh.</span></span>  
  
3.  <span data-ttu-id="139bf-115">Quitar la base de datos de cuadro de mensajes del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="139bf-115">Remove the MessageBox database from the BizTalk Group.</span></span>  
  
     <span data-ttu-id="139bf-116">Al quitar la base de datos de cuadro de mensajes del grupo de BizTalk, se quita la referencia de cuadro de mensajes de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="139bf-116">Removing the MessageBox database from the BizTalk Group removes the MessageBox reference from the BizTalk Management database.</span></span>  
  
4.  <span data-ttu-id="139bf-117">Reiniciar instancias de host que contienen conexiones en caché a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="139bf-117">Restart host instances that contain cached connections to the MessageBox database.</span></span>  
  
     <span data-ttu-id="139bf-118">Debe reiniciar la instancia de host antes de eliminar físicamente la base de datos de SQL Server si están presentes las conexiones de base de datos en caché del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="139bf-118">You must restart the host instance before physically deleting the database from SQL Server if cached database connections from the run-time engine are present.</span></span> <span data-ttu-id="139bf-119">Para obtener información acerca de cómo iniciar una instancia de host, consulte [cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md).</span><span class="sxs-lookup"><span data-stu-id="139bf-119">For information about starting a host instance, see [How to Start a Host Instance](../core/how-to-start-a-host-instance.md).</span></span>  
  
5.  <span data-ttu-id="139bf-120">Detener todas las instancias de host en curso que tengan acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="139bf-120">Stop all in-progress host instances that access the database.</span></span> <span data-ttu-id="139bf-121">Para obtener información acerca de cómo detener una instancia de host en curso, vea [cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md).</span><span class="sxs-lookup"><span data-stu-id="139bf-121">For information about stopping an in-progress host instance, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
     <span data-ttu-id="139bf-122">Si quita una base de datos de cuadro de mensajes que no sea principal, antes de detener una instancia de host en curso, debe deshabilitar la publicación de mensajes nuevos en el cuadro de mensajes y asegurarse de que:</span><span class="sxs-lookup"><span data-stu-id="139bf-122">If you are removing a non-primary MessageBox database, before stopping an in-progress host instance, you should first disable publication of new messages to that message box and make sure that:</span></span>  
  
    -   <span data-ttu-id="139bf-123">No quedará ninguna instancia de servicio en ejecución en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="139bf-123">There are no running service instances remaining in the message box.</span></span>  
  
    -   <span data-ttu-id="139bf-124">No quedará ninguna instancia suspendida (ni ninguna otra) en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="139bf-124">There are no suspended (or any other remaining) instances left in the message box.</span></span>  
  
    -   <span data-ttu-id="139bf-125">Los datos de seguimiento de BAM se han movido a la base de datos de seguimiento de BizTalk (BizTalkDTADb) (la tabla TrackingData debe estar vacía).</span><span class="sxs-lookup"><span data-stu-id="139bf-125">BAM tracked data has been moved to the BizTalk Tracking (BizTalkDTADb) database (TrackingData table should be empty).</span></span>  
  
    -   <span data-ttu-id="139bf-126">Los cuerpos de mensaje de los que se ha realizado un seguimiento se han movido a la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="139bf-126">Tracked message bodies have been moved to the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
6.  <span data-ttu-id="139bf-127">Asegurarse de que se termina el trabajo de fondo del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="139bf-127">Ensure that the background SQL Server Agent job is finished.</span></span>  
  
     <span data-ttu-id="139bf-128">Antes de eliminar permanentemente una base de datos de cuadro de mensajes de su implementación de BizTalk Server, primero debería asegurarse de que el trabajo de fondo del Agente SQL Server ha terminado de transferir todos los cuerpos de mensaje de los que se ha efectuado un seguimiento a la tabla TrackingSpool y, entonces, hacer una copia de seguridad de las tablas TrackingSpool.</span><span class="sxs-lookup"><span data-stu-id="139bf-128">Before you permanently delete a MessageBox database from your BizTalk Server deployment, you should first ensure that the background SQL Server Agent job has finished transferring all tracked message bodies to the TrackingSpool table, and then back up the TrackingSpool tables.</span></span> <span data-ttu-id="139bf-129">Para obtener información acerca de cómo comprobar el estado de un trabajo de fondo del Agente SQL Server, vea Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="139bf-129">For information about checking the status of a background SQL Server Agent job, see SQL Server Books Online.</span></span>  
  
7.  <span data-ttu-id="139bf-130">Cree una copia de seguridad de las tablas TrackingSpool.</span><span class="sxs-lookup"><span data-stu-id="139bf-130">Back up the TrackingSpool tables.</span></span>  
  
     <span data-ttu-id="139bf-131">Los cuerpos de mensaje de los que se ha efectuado el seguimiento permanecen en la base de datos de cuadro de mensajes hasta que realice una copia de seguridad manual de las tablas TrackingSpool en un almacenamiento externo.</span><span class="sxs-lookup"><span data-stu-id="139bf-131">Tracked message bodies remain in the MessageBox database until you manually back up the TrackingSpool tables into external storage.</span></span> <span data-ttu-id="139bf-132">Antes de que se cree la copia de seguridad, un trabajo de fondo del Agente SQL Server transfiere los cuerpos de mensaje de la tabla de cola de impresión a la tabla TrackingSpool.</span><span class="sxs-lookup"><span data-stu-id="139bf-132">Before the backup happens, a background SQL Server Agent job transfers the message bodies from the Spool table to the TrackingSpool table.</span></span> <span data-ttu-id="139bf-133">Para obtener información acerca de cómo realizar una copia de seguridad manual de las tablas de SQL Server, vea Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="139bf-133">For information about manually backing up SQL Server tables, see SQL Server Books Online.</span></span>  
  
8.  <span data-ttu-id="139bf-134">Quitar la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="139bf-134">Remove the database from SQL Server.</span></span>  
  
     <span data-ttu-id="139bf-135">La eliminación de una base de datos de cuadro de mensajes de un grupo de BizTalk no implica la eliminación de la base de datos de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="139bf-135">Deleting a MessageBox database from a BizTalk Group does not physically remove the database from Microsoft SQL Server.</span></span> <span data-ttu-id="139bf-136">Para eliminar permanentemente la base de datos de cuadro de mensajes, es preciso quitarla mediante el Administrador corporativo de SQL Server o SQL Server Management Studio después de que se haya quitado del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="139bf-136">To permanently delete the MessageBox database, you must remove it by using SQL Server Enterprise Manager or SQL Server Management Studio after it is removed from the BizTalk Group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="139bf-137">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="139bf-137">Prerequisites</span></span>  
 <span data-ttu-id="139bf-138">Los administradores de las bases de datos de cuadro de mensajes deben tener los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="139bf-138">Administrators who manage MessageBox databases must have the required user rights.</span></span> <span data-ttu-id="139bf-139">Debe tener los siguientes derechos de usuario para administrar las bases de datos de cuadro de mensajes y deshabilitar la publicación de mensajes nuevos:</span><span class="sxs-lookup"><span data-stu-id="139bf-139">You must have the following user rights to manage MessageBox databases and disable new message publication:</span></span>  
  
-   <span data-ttu-id="139bf-140">Debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="139bf-140">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
-   <span data-ttu-id="139bf-141">Debe ser administrador de SQL Server en el equipo donde reside la base de datos.</span><span class="sxs-lookup"><span data-stu-id="139bf-141">You must be a SQL Server Administrator on the computer where the database exists.</span></span>  
  
### <a name="to-delete-a-messagebox-database-from-a-biztalk-group"></a><span data-ttu-id="139bf-142">Para eliminar una base de datos de cuadro de mensajes de un grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="139bf-142">To delete a MessageBox database from a BizTalk Group</span></span>  
  
1. <span data-ttu-id="139bf-143">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="139bf-143">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="139bf-144">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **cuadros de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="139bf-144">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Message Boxes**.</span></span>  
  
3. <span data-ttu-id="139bf-145">En el panel de detalles, haga clic en la base de datos de cuadro de mensaje que desea quitar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="139bf-145">In the details pane, right-click the message box database you want to remove, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="139bf-146">En el **propiedades de cuadro de mensaje** cuadro de diálogo, seleccione el **Deshabilitar publicación de nuevos mensajes** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="139bf-146">In the **Message Box Properties** dialog box, select the **Disable new message publication** check box.</span></span>  
  
5. <span data-ttu-id="139bf-147">Utilice la página Concentrador de grupo de la consola de administración de BizTalk Server para comprobar que no haya instancias de mensaje deshidratadas o suspendidas en la base de datos de cuadro de mensajes que vaya a eliminar.</span><span class="sxs-lookup"><span data-stu-id="139bf-147">Use the Group Hub page in the BizTalk Server Administration Console to verify that no message instances are dehydrated or suspended on the MessageBox database you are deleting.</span></span>  
  
6. <span data-ttu-id="139bf-148">Espere durante un período de tiempo que equivalga al doble de la longitud de CacheRefreshInterval.</span><span class="sxs-lookup"><span data-stu-id="139bf-148">Wait for a period of time twice the length of the CacheRefreshInterval.</span></span> <span data-ttu-id="139bf-149">El valor predeterminado de CacheRefreshInterval (intervalo de actualización de la caché) es de 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="139bf-149">The default value of CacheRefreshInterval is 60 seconds.</span></span>  
  
7. <span data-ttu-id="139bf-150">En el panel de detalles, haga clic en la base de datos de cuadro de mensajes que desea eliminar y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="139bf-150">In the details pane, right-click the MessageBox database that you want to delete, and click **Delete**.</span></span>  
  
8. <span data-ttu-id="139bf-151">Después de leer el mensaje de advertencia, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="139bf-151">After reading the warning message, click **OK**.</span></span>  
  
9. <span data-ttu-id="139bf-152">En el árbol de consola, expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="139bf-152">In the console tree, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
10. <span data-ttu-id="139bf-153">En el panel de detalles, haga clic con el botón secundario en todas las instancias de host en ejecución y detenga y reinicie cada una.</span><span class="sxs-lookup"><span data-stu-id="139bf-153">In the details pane, right-click all running host instances, and stop and restart each one.</span></span>  
  
11. <span data-ttu-id="139bf-154">En el servidor donde reside la base de datos de cuadro de mensajes, abra el Administrador corporativo de SQL Server o SQL Server Management Studio, en función de la versión de SQL Server que utilice; seguidamente, elimine la base de datos.</span><span class="sxs-lookup"><span data-stu-id="139bf-154">On the server where the MessageBox database resides, open SQL Server Enterprise Manager or SQL Server Management Studio, depending on which version of SQL Server you are using, and then delete the database.</span></span>  
  
     <span data-ttu-id="139bf-155">Para obtener información acerca de cómo eliminar una base de datos de SQL Server, vea Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="139bf-155">For information about how to delete a database in SQL Server, see SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="139bf-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="139bf-156">See Also</span></span>  
 <span data-ttu-id="139bf-157">[Administrar bases de datos de cuadro de mensajes](../core/managing-messagebox-databases.md) </span><span class="sxs-lookup"><span data-stu-id="139bf-157">[Managing MessageBox Databases](../core/managing-messagebox-databases.md) </span></span>  
 <span data-ttu-id="139bf-158">[Cómo agregar una nueva base de datos de cuadro de mensajes](../core/how-to-add-a-new-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="139bf-158">[How to Add a New MessageBox Database](../core/how-to-add-a-new-messagebox-database.md) </span></span>  
 <span data-ttu-id="139bf-159">[Cómo deshabilitar la publicación de mensajes nuevos](../core/how-to-disable-new-message-publication.md) </span><span class="sxs-lookup"><span data-stu-id="139bf-159">[How to Disable New Message Publication](../core/how-to-disable-new-message-publication.md) </span></span>  
 [<span data-ttu-id="139bf-160">La base de datos de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="139bf-160">The MessageBox Database</span></span>](../core/the-messagebox-database.md)