---
title: Cómo eliminar una aplicación de BizTalk del grupo de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undeploying, applications
- applications, deleting
- applications, groups
- undeploying, deleting
- managing [applications], deleting
- deleting, applications
- applications, undeploying
- managing [applications], groups
- groups, applications
ms.assetid: 968a6436-ae1a-4f85-bb44-e704826a0197
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7afb7dc0d92f48d2db0ae0e38fbb86f2504c8168
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989629"
---
# <a name="how-to-delete-a-biztalk-application-from-the-biztalk-group"></a><span data-ttu-id="a5d98-102">Cómo eliminar una aplicación de BizTalk del grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a5d98-102">How to Delete a BizTalk Application from the BizTalk Group</span></span>
<span data-ttu-id="a5d98-103">Puede eliminar una aplicación del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a5d98-103">You can delete an application from the BizTalk group.</span></span> <span data-ttu-id="a5d98-104">Al hacerlo, se quitan todos los datos correspondientes de las bases de datos de BizTalk para el grupo y la administración ya no se muestra más en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a5d98-104">This removes all of its data from the BizTalk databases for the group, and the application no longer displays in the BizTalk Server Administration console.</span></span> <span data-ttu-id="a5d98-105">Esto no desinstala la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5d98-105">It does not uninstall the application.</span></span>  
  
 <span data-ttu-id="a5d98-106">Antes de eliminar una aplicación, tenga en cuenta los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="a5d98-106">Before you delete an application, bear in mind the following points:</span></span>  
  
-   <span data-ttu-id="a5d98-107">Para eliminar la aplicación, debe estar detenida.</span><span class="sxs-lookup"><span data-stu-id="a5d98-107">The application must be stopped before you can delete it.</span></span> <span data-ttu-id="a5d98-108">Debe usar la opción detención completa para detener la aplicación, como se describe en [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="a5d98-108">You should use the Full Stop option for stopping the application, as described in [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="a5d98-109">Solo puede eliminar una aplicación si no hay aplicaciones que contengan referencias a ella.</span><span class="sxs-lookup"><span data-stu-id="a5d98-109">You can delete an application only if no other applications contain references to it.</span></span> <span data-ttu-id="a5d98-110">Si otras aplicaciones contienen referencias a la aplicación que desea quitar, primero debe quitar las referencias de las otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a5d98-110">If other applications contain references to the application you want to remove, you must first remove the references from the other applications.</span></span> <span data-ttu-id="a5d98-111">Para obtener instrucciones, consulte [cómo quitar una referencia a otra aplicación](../core/how-to-remove-a-reference-to-another-application.md).</span><span class="sxs-lookup"><span data-stu-id="a5d98-111">For instructions, see [How to Remove a Reference to Another Application](../core/how-to-remove-a-reference-to-another-application.md).</span></span>  
  
-   <span data-ttu-id="a5d98-112">No puede eliminar una aplicación si contiene un grupo de puertos de envío del que es miembro un puerto de envío de otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5d98-112">You cannot delete an application if it contains a send port group of which a send port in another application is a member.</span></span> <span data-ttu-id="a5d98-113">Debe dar de baja el puerto de envío miembro para poder eliminar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5d98-113">You must unenlist the member send port before you can delete the application.</span></span> <span data-ttu-id="a5d98-114">Para obtener instrucciones, consulte [cómo dar de baja un puerto de envío o grupo de puertos de envío](../core/how-to-unenlist-a-send-port-or-send-port-group.md).</span><span class="sxs-lookup"><span data-stu-id="a5d98-114">For instructions, see [How to Unenlist a Send Port or Send Port Group](../core/how-to-unenlist-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="a5d98-115">No puede eliminar una aplicación si contiene un puerto de envío al que hace referencia una entidad.</span><span class="sxs-lookup"><span data-stu-id="a5d98-115">You cannot delete an application if it contains a send port that is referenced by a party.</span></span> <span data-ttu-id="a5d98-116">Puede eliminar la referencia de la entidad, eliminar el puerto de envío o mover el puerto de envío a una aplicación diferente.</span><span class="sxs-lookup"><span data-stu-id="a5d98-116">You can delete the reference from the party, delete the send port, or move the send port to a different application.</span></span> <span data-ttu-id="a5d98-117">Para obtener instrucciones sobre cómo realizar estas tareas, consulte [cómo ver o editar una entidad](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca), [cómo eliminar un puerto de envío](../core/how-to-delete-a-send-port.md), o [cómo mover un artefacto a una aplicación diferente](../core/how-to-move-an-artifact-to-a-different-application.md).</span><span class="sxs-lookup"><span data-stu-id="a5d98-117">For instructions on performing these tasks, see [How to View or Edit a Party](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca), [How to Delete a Send Port](../core/how-to-delete-a-send-port.md), or [How to Move an Artifact to a Different Application](../core/how-to-move-an-artifact-to-a-different-application.md).</span></span>  
  
-   <span data-ttu-id="a5d98-118">No puede eliminar la aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a5d98-118">You cannot delete the default application.</span></span> <span data-ttu-id="a5d98-119">Si desea eliminarla, primero debe hacer que otra aplicación sea la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a5d98-119">If you want to delete it, you must first make another application the default.</span></span> <span data-ttu-id="a5d98-120">Para obtener instrucciones, consulte [cómo cambiar la aplicación predeterminada](../core/how-to-change-the-default-application.md).</span><span class="sxs-lookup"><span data-stu-id="a5d98-120">For instructions, see [How to Change the Default Application](../core/how-to-change-the-default-application.md).</span></span>  
  
-   <span data-ttu-id="a5d98-121">No puede eliminar una aplicación si una orquestación de la aplicación tiene una instancia suspendida.</span><span class="sxs-lookup"><span data-stu-id="a5d98-121">You cannot delete an application if an orchestration in the application has a suspended instance.</span></span>  
  
-   <span data-ttu-id="a5d98-122">Para anular totalmente la implementación de una aplicación de BizTalk, también debe realizar los pasos descritos en [cómo desinstalar una aplicación de BizTalk](../core/how-to-uninstall-a-biztalk-application.md), y quizás también deba quitar otros archivos y configuraciones, como se describe en [cómo quitar Otros archivos y configuraciones para una aplicación de BizTalk](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="a5d98-122">To completely undeploy a BizTalk application, you must also take the steps described in [How to Uninstall a BizTalk Application](../core/how-to-uninstall-a-biztalk-application.md), and you may also need to remove other files and settings, as described in [How to Remove Other Files and Settings for a BizTalk Application](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a5d98-123">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a5d98-123">Prerequisites</span></span>  
 <span data-ttu-id="a5d98-124">Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a5d98-124">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a5d98-125">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="a5d98-125">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-delete-a-biztalk-application"></a><span data-ttu-id="a5d98-126">Para eliminar una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a5d98-126">To delete a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="a5d98-127">Mediante la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a5d98-127">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="a5d98-128">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a5d98-128">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a5d98-129">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a5d98-129">In the console tree, expand  **BizTalk Server Administration**, expand the BizTalk group, and expand **Applications**.</span></span>  
  
3. <span data-ttu-id="a5d98-130">Haga clic en la carpeta de aplicación y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a5d98-130">Right-click the application folder, and then click **Delete**.</span></span>  
  
4. <span data-ttu-id="a5d98-131">Haga clic en **Sí** para confirmar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="a5d98-131">Click **Yes** to confirm the deletion.</span></span>  
  
    <span data-ttu-id="a5d98-132">BizTalk Server elimina todos los datos de la aplicación de las bases de datos de BizTalk y quita la aplicación de la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a5d98-132">BizTalk Server deletes all of the application data from the BizTalk databases and removes the application from the administration console.</span></span>  
  
    <span data-ttu-id="a5d98-133">Si BizTalk Server no puede eliminar alguno de los artefactos de la aplicación, la operación de eliminación no se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="a5d98-133">If BizTalk Server cannot delete any of the application artifacts, the delete operation fails.</span></span> <span data-ttu-id="a5d98-134">En ese caso, BizTalk Server intenta revertir la operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="a5d98-134">In this case, BizTalk Server attempts to roll back the delete operation.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="a5d98-135">Utilizar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="a5d98-135">Using the command line</span></span>  
  
1. <span data-ttu-id="a5d98-136">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5d98-136">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="a5d98-137">Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:</span><span class="sxs-lookup"><span data-stu-id="a5d98-137">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="a5d98-138">**BTSTask RemoveApp /ApplicationName:** *valor* [**/Server:**<em>valor</em>] [**/Database:**<em>valor</em> ]</span><span class="sxs-lookup"><span data-stu-id="a5d98-138">**BTSTask RemoveApp /ApplicationName:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="a5d98-139">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a5d98-139">Example:</span></span>  
  
    <span data-ttu-id="a5d98-140">**BTSTask RemoveApp /ApplicationName:MyApplication**</span><span class="sxs-lookup"><span data-stu-id="a5d98-140">**BTSTask RemoveApp /ApplicationName:MyApplication**</span></span>  
  
   |<span data-ttu-id="a5d98-141">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a5d98-141">Parameter</span></span>|<span data-ttu-id="a5d98-142">Valor</span><span class="sxs-lookup"><span data-stu-id="a5d98-142">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="a5d98-143">**/ ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="a5d98-143">**/ApplicationName**</span></span>|<span data-ttu-id="a5d98-144">Nombre de la aplicación de BizTalk Server que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="a5d98-144">Name of the BizTalk application to delete.</span></span> <span data-ttu-id="a5d98-145">Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="a5d98-145">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="a5d98-146">**/ Servidor**</span><span class="sxs-lookup"><span data-stu-id="a5d98-146">**/Server**</span></span>|<span data-ttu-id="a5d98-147">Nombre de la instancia de servidor SQL Server que aloja la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a5d98-147">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="a5d98-148">Resulta necesario si se especifica el parámetro de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a5d98-148">Required if you specify the Database parameter.</span></span> <span data-ttu-id="a5d98-149">Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.</span><span class="sxs-lookup"><span data-stu-id="a5d98-149">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
   |<span data-ttu-id="a5d98-150">**/ Base de datos**</span><span class="sxs-lookup"><span data-stu-id="a5d98-150">**/Database**</span></span>|<span data-ttu-id="a5d98-151">Nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a5d98-151">Name of the BizTalk Management database.</span></span> <span data-ttu-id="a5d98-152">Resulta necesario si se especifica el parámetro de servidor.</span><span class="sxs-lookup"><span data-stu-id="a5d98-152">Required if you specify the Server parameter.</span></span> <span data-ttu-id="a5d98-153">Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.</span><span class="sxs-lookup"><span data-stu-id="a5d98-153">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5d98-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5d98-154">See Also</span></span>  
 <span data-ttu-id="a5d98-155">[Anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a5d98-155">[Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="a5d98-156">Implementación de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a5d98-156">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)