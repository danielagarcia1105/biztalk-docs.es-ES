---
title: Iniciar una instancia de Host | Documentos de Microsoft
description: Use la administración de BizTalk para iniciar una instancia de host de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a96a4362-2147-4b8e-a270-bf9a17477ba3
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd5cccc48b33dda4b6458f8dfa8f56a84ad3cd62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255820"
---
# <a name="start-a-host-instance"></a><span data-ttu-id="56ceb-103">Iniciar una instancia de Host</span><span class="sxs-lookup"><span data-stu-id="56ceb-103">Start a Host Instance</span></span>
<span data-ttu-id="56ceb-104">Puede usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o el Instrumental de administración de Windows (WMI) para iniciar las instancias de host.</span><span class="sxs-lookup"><span data-stu-id="56ceb-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or Windows Management Instrumentation (WMI) to start host instances.</span></span> <span data-ttu-id="56ceb-105">Después de agregar o detener una instancia de host, debe iniciarla para que ejecute y enrute mensajes a las bases de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="56ceb-105">After you add or stop a host instance, you must start it so that it is running and routing messages to the MessageBox databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="56ceb-106">La cuenta de servicio que especificó para la instancia de host debería ser miembro del grupo de Windows para el host asociado.</span><span class="sxs-lookup"><span data-stu-id="56ceb-106">The service account that you specify for a host instance should be a member of the Windows group for the associated host.</span></span> <span data-ttu-id="56ceb-107">De lo contrario, puede que la instancia de host no tenga los permisos necesarios o la autenticación apropiada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="56ceb-107">Otherwise, the host instance may not have the appropriate permissions or authentication at run time.</span></span> <span data-ttu-id="56ceb-108">Asimismo, por razones de seguridad, la cuenta debería tener unos privilegios mínimos porque las orquestaciones alojadas por la instancia de host pueden ejecutar código personalizado potencialmente malintencionado.</span><span class="sxs-lookup"><span data-stu-id="56ceb-108">In addition, for security reasons, the account should have minimum privileges because orchestrations hosted by the host instance might execute potentially malicious custom code.</span></span>  
  
 <span data-ttu-id="56ceb-109">Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md).</span><span class="sxs-lookup"><span data-stu-id="56ceb-109">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span> <span data-ttu-id="56ceb-110">Para obtener información acerca del uso de WMI para iniciar una instancia de host, consulte **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="56ceb-110">For information about using WMI to start a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="56ceb-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="56ceb-111">Prerequisites</span></span>  
 <span data-ttu-id="56ceb-112">Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores y del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="56ceb-112">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="56ceb-113">Además, también es preciso que sea miembro de la función de base de datos de SQL Server db_securityadmin y de la función de SQL Server securityadmin en los servidores en los que se encuentren las siguientes bases de datos:</span><span class="sxs-lookup"><span data-stu-id="56ceb-113">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="56ceb-114">Importación principal de BAM (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="56ceb-114">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="56ceb-115">Administración de BizTalk (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="56ceb-115">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="56ceb-116">Cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) (todo)</span><span class="sxs-lookup"><span data-stu-id="56ceb-116">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="56ceb-117">Seguimiento de BizTalk (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="56ceb-117">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="56ceb-118">Motor de reglas (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="56ceb-118">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="56ceb-119">Se recomienda actualizar la información de cuenta de las instancias de host mediante el script de Instrumental de administración de Windows (WMI) o la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="56ceb-119">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="56ceb-120">Con ello, se garantiza que BizTalk Server pueda actualizar la información de cuenta en las bases de datos de BizTalk Server y mantener la configuración de seguridad entre las bases de datos y la instancia de host sincronizada.</span><span class="sxs-lookup"><span data-stu-id="56ceb-120">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="56ceb-121">Pasos</span><span class="sxs-lookup"><span data-stu-id="56ceb-121">Steps</span></span>
  
1.  <span data-ttu-id="56ceb-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="56ceb-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="56ceb-123">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="56ceb-123">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="56ceb-124">En el panel de detalles, haga clic en la instancia de host que desea iniciar y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="56ceb-124">In the details pane, right-click the host instance you want to start, and then click **Start**.</span></span>  
  
     <span data-ttu-id="56ceb-125">El estado de la instancia de host cambia a **Inicio pendiente**.</span><span class="sxs-lookup"><span data-stu-id="56ceb-125">The status of the host instance changes to **Start pending**.</span></span> <span data-ttu-id="56ceb-126">Una vez que se inicia la instancia de host, el estado cambia a **ejecutando**.</span><span class="sxs-lookup"><span data-stu-id="56ceb-126">After the host instance initiates, the status changes to **Running**.</span></span>  
  
 <span data-ttu-id="56ceb-127">Después de iniciar una instancia de host, puede detenerla para evitar que los mensajes se enruten a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="56ceb-127">After you start a host instance, you can stop it to prevent it from routing messages to the MessageBox database.</span></span> <span data-ttu-id="56ceb-128">Debe detener una instancia de host antes de que pueda quitar BizTalk Server de un equipo dado.</span><span class="sxs-lookup"><span data-stu-id="56ceb-128">You must stop a host instance before you can remove BizTalk Server from a given computer.</span></span> <span data-ttu-id="56ceb-129">Para obtener información acerca de cómo detener una instancia de host, consulte [cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md).</span><span class="sxs-lookup"><span data-stu-id="56ceb-129">For information about stopping a host instance, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56ceb-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="56ceb-130">See Also</span></span>  
 <span data-ttu-id="56ceb-131">[Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="56ceb-131">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="56ceb-132">[Agregar una instancia de Host](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="56ceb-132">[Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="56ceb-133">[Detener una instancia de Host](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="56ceb-133">[Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 <span data-ttu-id="56ceb-134">[Eliminar una instancia de Host](../core/how-to-delete-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="56ceb-134">[Delete a Host Instance](../core/how-to-delete-a-host-instance.md) </span></span>  
 [<span data-ttu-id="56ceb-135">Modificar las propiedades de la instancia de Host</span><span class="sxs-lookup"><span data-stu-id="56ceb-135">Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)