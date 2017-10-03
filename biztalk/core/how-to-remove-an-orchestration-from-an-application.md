---
title: "Cómo quitar una orquestación de una aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, orchestrations
- deleting, orchestrations
- managing [orchestrations], deleting
- orchestrations, applications
- orchestrations, deleting
ms.assetid: e6d635ea-3513-42de-a667-b56c536e5328
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef4909f5430ae2d0435d519823abe9735cbc1cc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-an-orchestration-from-an-application"></a><span data-ttu-id="a6799-102">Cómo quitar una orquestación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="a6799-102">How to Remove an Orchestration from an Application</span></span>
<span data-ttu-id="a6799-103">En este tema se describen cómo utilizar la consola de administración de BizTalk Server o la línea de comandos para quitar una orquestación de una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a6799-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove an orchestration from a BizTalk application.</span></span> <span data-ttu-id="a6799-104">Al quitar una orquestación de una aplicación, también se elimina de la base de datos de administración de BizTalk para el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a6799-104">Removing an orchestration from an application also deletes it from the BizTalk Management database for the BizTalk group.</span></span>  
  
 <span data-ttu-id="a6799-105">Al quitar una orquestación, ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6799-105">When you remove an orchestration, the following occurs:</span></span>  
  
-   <span data-ttu-id="a6799-106">La orquestación se elimina de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a6799-106">The orchestration is deleted from the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="a6799-107">El ensamblado de BizTalk que contiene la orquestación se elimina de la base de datos de administración de BizTalk, aunque no se quita del sistema de archivos local o de la caché de ensamblados global (GAC), si existe en estas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="a6799-107">The BizTalk assembly that contains the orchestration is deleted from the BizTalk Management database, but is not removed from the local file system or the global assembly cache (GAC), if it exists in these locations.</span></span>  
  
-   <span data-ttu-id="a6799-108">Como consecuencia del ensamblado de BizTalk que se va a eliminar, también se eliminan de la base de datos de administración todos los artefactos que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a6799-108">As a consequence of the BizTalk assembly being deleted, all artifacts contained in the assembly are deleted from the BizTalk Management database as well.</span></span>  
  
 <span data-ttu-id="a6799-109">Antes de quitar una orquestación de una aplicación, tenga en cuenta los siguientes puntos relevantes:</span><span class="sxs-lookup"><span data-stu-id="a6799-109">Before removing an orchestration from an application, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="a6799-110">Si hay otros artefactos con dependencias en esta orquestación o los artefactos incluidos en el ensamblado que también se va a quitar, dejarán de funcionar correctamente al quitar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="a6799-110">If other artifacts have dependencies on this orchestration or the artifacts contained in the assembly that will also be removed, they will no longer function correctly when you remove the orchestration.</span></span> <span data-ttu-id="a6799-111">Para obtener información general acerca de las dependencias, consulte [dependencias e implementación de aplicaciones](../core/dependencies-and-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="a6799-111">For background information about dependencies, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
-   <span data-ttu-id="a6799-112">No es posible quitar una orquestación que tenga instancias en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6799-112">You cannot remove an orchestration that has running instances.</span></span> <span data-ttu-id="a6799-113">Es preciso finalizar esas instancias.</span><span class="sxs-lookup"><span data-stu-id="a6799-113">You must terminate any running instances.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a6799-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a6799-114">Prerequisites</span></span>  
 <span data-ttu-id="a6799-115">Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a6799-115">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a6799-116">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="a6799-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-an-orchestration-from-an-application"></a><span data-ttu-id="a6799-117">Para quitar una orquestación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="a6799-117">To remove an orchestration from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="a6799-118">Mediante la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a6799-118">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="a6799-119">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a6799-119">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a6799-120">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="a6799-120">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to remove.</span></span>  
  
3.  <span data-ttu-id="a6799-121">Haga clic en **orquestaciones**, haga clic en la orquestación y, a continuación, haga clic en **dar de baja**.</span><span class="sxs-lookup"><span data-stu-id="a6799-121">Click **Orchestrations**, right-click the orchestration, and then click **Unenlist**.</span></span>  
  
4.  <span data-ttu-id="a6799-122">Seleccione la orquestación, elija **vista**y, a continuación, haga clic en **información de instancia**.</span><span class="sxs-lookup"><span data-stu-id="a6799-122">Select the orchestration, point to **View**, and then click **Instance Information**.</span></span>  
  
5.  <span data-ttu-id="a6799-123">En el panel de resultados de la consulta, haga clic en las instancias de orquestación y, a continuación, haga clic en **Terminate**.</span><span class="sxs-lookup"><span data-stu-id="a6799-123">In the query results pane, right-click the orchestration instances, and then click **Terminate**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6799-124">Puede dar de baja, finalizar instancias en ejecución y detener de todas las orquestaciones en una aplicación a la vez mediante la opción detención completa para la aplicación, como se describe en [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="a6799-124">You can unenlist, terminate running instances, and stop all of the orchestrations in an application at once by using the Full Stop option for the application, as described in [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
6.  <span data-ttu-id="a6799-125">Haga clic en **orquestaciones**, haga clic en la orquestación y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="a6799-125">Click **Orchestrations**, right-click the orchestration, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="a6799-126">Utilizar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="a6799-126">Using the command line</span></span>  
  
1.  <span data-ttu-id="a6799-127">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a6799-127">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="a6799-128">Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:</span><span class="sxs-lookup"><span data-stu-id="a6799-128">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="a6799-129">**BTSTask RemoveResource** [**/ApplicationName:***valor*] **/Luid:***valor* [  **/Server:**  *valor*] [**/Database:***valor*]</span><span class="sxs-lookup"><span data-stu-id="a6799-129">**BTSTask RemoveResource** [**/ApplicationName:***value*] **/Luid:***value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="a6799-130">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a6799-130">Example:</span></span>  
  
     <span data-ttu-id="a6799-131">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, versión = 1.0.0.0, Culture = neutral, PublicKeyToken = 0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="a6799-131">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
    |<span data-ttu-id="a6799-132">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a6799-132">Parameter</span></span>|<span data-ttu-id="a6799-133">Description</span><span class="sxs-lookup"><span data-stu-id="a6799-133">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="a6799-134">**/ ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="a6799-134">**/ApplicationName**</span></span>|<span data-ttu-id="a6799-135">Nombre de la aplicación de BizTalk que contiene la orquestación que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="a6799-135">Name of the BizTalk application containing the orchestration to delete.</span></span> <span data-ttu-id="a6799-136">Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="a6799-136">If the name includes spaces, you must enclose it in double quotation marks (").</span></span> <span data-ttu-id="a6799-137">Si no se especifica este parámetro, se utiliza la aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a6799-137">If this parameter is not specified, the default application is used.</span></span>|  
    |<span data-ttu-id="a6799-138">**/ Luid**</span><span class="sxs-lookup"><span data-stu-id="a6799-138">**/Luid**</span></span>|<span data-ttu-id="a6799-139">Identificador local único (LUID) de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="a6799-139">Locally unique identifier (LUID) of the orchestration.</span></span> <span data-ttu-id="a6799-140">Puede obtener el LUID mediante el [comando ListApp](../core/listapp-command.md).</span><span class="sxs-lookup"><span data-stu-id="a6799-140">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
    |<span data-ttu-id="a6799-141">**/ Servidor**</span><span class="sxs-lookup"><span data-stu-id="a6799-141">**/Server**</span></span>|<span data-ttu-id="a6799-142">Nombre de la instancia de servidor SQL Server que aloja la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a6799-142">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="a6799-143">Resulta necesario si se especifica el parámetro de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a6799-143">Required if you specify the Database parameter.</span></span> <span data-ttu-id="a6799-144">Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.</span><span class="sxs-lookup"><span data-stu-id="a6799-144">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
    |<span data-ttu-id="a6799-145">**/ Base de datos**</span><span class="sxs-lookup"><span data-stu-id="a6799-145">**/Database**</span></span>|<span data-ttu-id="a6799-146">Nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a6799-146">Name of the BizTalk Management database.</span></span> <span data-ttu-id="a6799-147">Resulta necesario si se especifica el parámetro de servidor.</span><span class="sxs-lookup"><span data-stu-id="a6799-147">Required if you specify the Server parameter.</span></span> <span data-ttu-id="a6799-148">Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.</span><span class="sxs-lookup"><span data-stu-id="a6799-148">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6799-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6799-149">See Also</span></span>  
 <span data-ttu-id="a6799-150">[Administrar orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="a6799-150">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="a6799-151">RemoveResource (comando)</span><span class="sxs-lookup"><span data-stu-id="a6799-151">RemoveResource Command</span></span>](../core/removeresource-command.md)