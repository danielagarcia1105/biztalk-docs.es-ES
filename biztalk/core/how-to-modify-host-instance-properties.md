---
title: Cambiar las propiedades de la instancia de Host | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a35ca0c8-89b3-483a-b2fc-c8f43a8864d1
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53a64257f752e161963539256dcaca3f7f8f1077
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003349"
---
# <a name="update-host-instance-properties"></a><span data-ttu-id="6593a-102">Actualizar las propiedades de la instancia de Host</span><span class="sxs-lookup"><span data-stu-id="6593a-102">Update Host Instance Properties</span></span>

## <a name="overview"></a><span data-ttu-id="6593a-103">Información general</span><span class="sxs-lookup"><span data-stu-id="6593a-103">Overview</span></span>
<span data-ttu-id="6593a-104">Puede usar la consola de administración de BizTalk Server o el Instrumental de administración de Windows (WMI) para modificar las instancias de host.</span><span class="sxs-lookup"><span data-stu-id="6593a-104">You can use the BizTalk Server Administration Console or Windows Management Instrumentation (WMI) to modify host instances.</span></span> <span data-ttu-id="6593a-105">Es posible modificar la cuenta de servicio que ejecuta una instancia de host.</span><span class="sxs-lookup"><span data-stu-id="6593a-105">You can modify the service account running a host instance.</span></span> <span data-ttu-id="6593a-106">También se puede deshabilitar una instancia de host.</span><span class="sxs-lookup"><span data-stu-id="6593a-106">You can also disable a host instance.</span></span> <span data-ttu-id="6593a-107">Por ejemplo, si desea conservar la configuración de una instancia de host, pero no desea iniciarla, puede deshabilitarla.</span><span class="sxs-lookup"><span data-stu-id="6593a-107">For example, if you want to preserve the settings for a host instance and you do not want it to start, you can disable it.</span></span> <span data-ttu-id="6593a-108">Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md).</span><span class="sxs-lookup"><span data-stu-id="6593a-108">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
 <span data-ttu-id="6593a-109">Las instancias de host de hosts de confianza y las instancias de host de hosts que no son de confianza no pueden utilizar las mismas cuentas de servicio.</span><span class="sxs-lookup"><span data-stu-id="6593a-109">Host instances of trusted hosts and host instances of non-trusted hosts cannot use the same service accounts.</span></span> <span data-ttu-id="6593a-110">Si desea cambiar la configuración de confianza de una instancia de host y dicha instancia utiliza una cuenta de servicio empleada por otras instancias de host, puede llevar a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="6593a-110">If you want to change the trust setting of a host instance and the host instance uses a service account that other host instances use, you can do one of the following:</span></span>  
  
-   <span data-ttu-id="6593a-111">Puede cambiar la cuenta de servicio de la instancia de host para la que desea cambiar la configuración de confianza a una cuenta de servicio nueva.</span><span class="sxs-lookup"><span data-stu-id="6593a-111">You can change the service account of the host instance for which you want to change the trust settings to a new service account.</span></span>  
  
-   <span data-ttu-id="6593a-112">Puede cambiar la cuenta de servicio de la instancia de host a una cuenta de servicio existente ya utilizada por otras instancias de host con la misma configuración de confianza.</span><span class="sxs-lookup"><span data-stu-id="6593a-112">You can change the service account of the host instance to an existing service account that other host instances with the same trust setting use.</span></span>  
  
-   <span data-ttu-id="6593a-113">Puede eliminar la instancia de host y volver a crearla con una configuración de confianza y una cuenta de servicio diferentes.</span><span class="sxs-lookup"><span data-stu-id="6593a-113">You can delete the host instance, and re-create it with a different trust setting and service account.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6593a-114">Ha de cambiar las credenciales de una instancia de host mediante la actualización de las propiedades de dicha instancia.</span><span class="sxs-lookup"><span data-stu-id="6593a-114">You must change the credentials for a host instance by updating the properties of the host instance.</span></span> <span data-ttu-id="6593a-115">Si cambia las credenciales del servicio correspondiente, la cuenta de servicio especificada para la instancia de host debe ser miembro del grupo del host.</span><span class="sxs-lookup"><span data-stu-id="6593a-115">If you change the credentials of the corresponding service, the service account you specify for the host instance must be a member of the group on the host.</span></span> <span data-ttu-id="6593a-116">No utilice el complemento Servicios o la consola de administración del equipo para cambiar las credenciales de la instancia de host; de lo contrario, puede que la instancia de host no funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="6593a-116">Do not use the Services snap-in or the Computer Management console to change the credentials of host instance, otherwise the host instance may not function properly.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6593a-117">Si cambia las credenciales de una instancia de host, ha de cambiar también las credenciales correspondientes del servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6593a-117">If you change the credentials of a host instance, you must also change the corresponding SQL Server credentials.</span></span> <span data-ttu-id="6593a-118">Si no actualiza las credenciales del servidor SQL Server, la instancia de host no funcionará correctamente.</span><span class="sxs-lookup"><span data-stu-id="6593a-118">If you do not update the SQL Server credentials, the host instance will not function properly.</span></span>  
  
 <span data-ttu-id="6593a-119">Para obtener información sobre cómo usar WMI para modificar una instancia de host, consulte **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="6593a-119">For information about using WMI to modify a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="6593a-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6593a-120">Prerequisites</span></span>  
 <span data-ttu-id="6593a-121">Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores y del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6593a-121">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="6593a-122">Además, también es preciso que sea miembro de la función de base de datos de SQL Server db_securityadmin y de la función de SQL Server securityadmin en los servidores en los que se encuentren las siguientes bases de datos:</span><span class="sxs-lookup"><span data-stu-id="6593a-122">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="6593a-123">Importación principal de BAM (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="6593a-123">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="6593a-124">Administración de BizTalk (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="6593a-124">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="6593a-125">Cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) (todo)</span><span class="sxs-lookup"><span data-stu-id="6593a-125">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="6593a-126">Seguimiento de BizTalk (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="6593a-126">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="6593a-127">Motor de reglas (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="6593a-127">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6593a-128">Se recomienda actualizar la información de cuenta de las instancias de host mediante el script de Instrumental de administración de Windows (WMI) o la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6593a-128">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="6593a-129">Con ello, se garantiza que BizTalk Server pueda actualizar la información de cuenta en las bases de datos de BizTalk Server y mantener la configuración de seguridad entre las bases de datos y la instancia de host sincronizada.</span><span class="sxs-lookup"><span data-stu-id="6593a-129">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="6593a-130">Pasos</span><span class="sxs-lookup"><span data-stu-id="6593a-130">Steps</span></span>
  
1. <span data-ttu-id="6593a-131">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="6593a-131">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="6593a-132">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="6593a-132">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3. <span data-ttu-id="6593a-133">En el panel de detalles, haga clic en la instancia de host que desea modificar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6593a-133">In the details pane, right-click the host instance you want to modify, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="6593a-134">En el **propiedades de la instancia de Host** cuadro de diálogo, haga clic en **configurar** para modificar la información de cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="6593a-134">In the **Host Instance Properties** dialog box, click **Configure** to modify the service account information.</span></span>  
  
5. <span data-ttu-id="6593a-135">En el **las credenciales de inicio de sesión** diálogo cuadro, escriba el nombre de cuenta y la contraseña de la cuenta bajo la que ejecutará la instancia de host y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6593a-135">In the **Logon Credentials** dialog box, enter the account name and password of the account under which the host instance will run, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="6593a-136">En el **propiedades de la instancia de Host** cuadro de diálogo, haga lo siguiente y, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="6593a-136">In the **Host Instance Properties** dialog box, do the following, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="6593a-137">Use</span><span class="sxs-lookup"><span data-stu-id="6593a-137">Use this</span></span>|<span data-ttu-id="6593a-138">Para</span><span class="sxs-lookup"><span data-stu-id="6593a-138">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="6593a-139">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="6593a-139">**Host name**</span></span>|<span data-ttu-id="6593a-140">Ver el nombre del host asociado con el servidor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6593a-140">Displays the name of the host associated with the selected server.</span></span>|  
   |<span data-ttu-id="6593a-141">**Server**</span><span class="sxs-lookup"><span data-stu-id="6593a-141">**Server**</span></span>|<span data-ttu-id="6593a-142">Ver el servidor asociado con el host seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6593a-142">Displays the server associated with the selected host.</span></span>|  
   |<span data-ttu-id="6593a-143">**Si está habilitada la limitación, a continuación, se convertirá en su entorno de BizTalk más allá de MST de inserción para que a su vez podría detectar qué el true MST es casi imposible.**</span><span class="sxs-lookup"><span data-stu-id="6593a-143">**Logon**</span></span>|<span data-ttu-id="6593a-144">Ver el nombre de cuenta de la cuenta de servicio nueva en la que se ejecutará la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="6593a-144">Displays the account name of the new service account under which the host instance will run.</span></span>|  
   |<span data-ttu-id="6593a-145">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="6593a-145">**Configure**</span></span>|<span data-ttu-id="6593a-146">Haga clic para mostrar el **las credenciales de inicio de sesión** cuadro de diálogo donde puede escribir el nombre de cuenta y la contraseña de la cuenta bajo la que se ejecutará la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="6593a-146">Click to display the **Logon Credentials** dialog box, where you can enter the account name and password of the account under which the host instance will run.</span></span>|  
   |<span data-ttu-id="6593a-147">**Deshabilitar inicio de instancia de host**</span><span class="sxs-lookup"><span data-stu-id="6593a-147">**Disable host instance from starting**</span></span>|<span data-ttu-id="6593a-148">Active esta casilla para cambiar el estado del host seleccionado de habilitado a deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="6593a-148">Select this check box to change the status of the selected host from enabled to disabled.</span></span> <span data-ttu-id="6593a-149">Deshabilitar una instancia de host es útil si no desea que se inicie la instancia de host pero sí quiere conservar su configuración.</span><span class="sxs-lookup"><span data-stu-id="6593a-149">Disabling a host instance is useful if you do not want the host instance to start, but you do want to preserve its settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6593a-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="6593a-150">See Also</span></span>  
 <span data-ttu-id="6593a-151">[Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="6593a-151">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="6593a-152">[Agregar una instancia de Host](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="6593a-152">[Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="6593a-153">[Iniciar una instancia de Host](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="6593a-153">[Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="6593a-154">[Detener una instancia de Host](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="6593a-154">[Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 [<span data-ttu-id="6593a-155">Eliminar una instancia de host</span><span class="sxs-lookup"><span data-stu-id="6593a-155">Delete a Host Instance</span></span>](../core/how-to-delete-a-host-instance.md)