---
title: Detener una instancia de Host | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1f2e0c1-a387-4182-82ef-e25f49ac509b
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 837b08c30263b48ad481c7e03820cfba0b6c0ecc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="stop-a-host-instance"></a><span data-ttu-id="578d6-102">Detener una instancia de Host</span><span class="sxs-lookup"><span data-stu-id="578d6-102">Stop a Host Instance</span></span>

## <a name="overview"></a><span data-ttu-id="578d6-103">Información general</span><span class="sxs-lookup"><span data-stu-id="578d6-103">Overview</span></span>
<span data-ttu-id="578d6-104">Puede usar el Instrumental de administración de Windows (WMI) o la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para detener instancias de host.</span><span class="sxs-lookup"><span data-stu-id="578d6-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or Windows Management Instrumentation (WMI) to stop host instances.</span></span> <span data-ttu-id="578d6-105">Es necesario detener las instancias de host antes de eliminarlas, o de quitar BizTalk Server de un equipo.</span><span class="sxs-lookup"><span data-stu-id="578d6-105">You must stop a host instance before you can delete it or remove BizTalk Server from a computer.</span></span> <span data-ttu-id="578d6-106">Es posible detener una instancia de host que esté instalada e iniciada.</span><span class="sxs-lookup"><span data-stu-id="578d6-106">You can stop a host instance that is installed and started.</span></span> <span data-ttu-id="578d6-107">Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md).</span><span class="sxs-lookup"><span data-stu-id="578d6-107">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
 <span data-ttu-id="578d6-108">Para obtener información acerca del uso de WMI para detener una instancia de host, consulte **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="578d6-108">For information about using WMI to stop a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="578d6-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="578d6-109">Prerequisites</span></span>  
 <span data-ttu-id="578d6-110">Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores y del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="578d6-110">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="578d6-111">Además, también es preciso que sea miembro de la función de base de datos de SQL Server db_securityadmin y de la función de SQL Server securityadmin en los servidores en los que se encuentren las siguientes bases de datos:</span><span class="sxs-lookup"><span data-stu-id="578d6-111">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="578d6-112">Importación principal de BAM (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="578d6-112">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="578d6-113">Administración de BizTalk (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="578d6-113">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="578d6-114">Cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) (todo)</span><span class="sxs-lookup"><span data-stu-id="578d6-114">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="578d6-115">Seguimiento de BizTalk (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="578d6-115">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="578d6-116">Motor de reglas (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="578d6-116">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="578d6-117">Se recomienda actualizar la información de cuenta de las instancias de host mediante el script de Instrumental de administración de Windows (WMI) o la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="578d6-117">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="578d6-118">Con ello, se garantiza que BizTalk Server pueda actualizar la información de cuenta en las bases de datos de BizTalk Server y mantener la configuración de seguridad entre las bases de datos y la instancia de host sincronizada.</span><span class="sxs-lookup"><span data-stu-id="578d6-118">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="578d6-119">Pasos</span><span class="sxs-lookup"><span data-stu-id="578d6-119">Steps</span></span>
  
1.  <span data-ttu-id="578d6-120">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="578d6-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="578d6-121">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="578d6-121">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="578d6-122">En el panel de detalles, haga clic en la instancia de host que desea detener y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="578d6-122">In the details pane, right-click the host instance you want to stop, and then click **Stop**.</span></span>  
  
     <span data-ttu-id="578d6-123">El estado de la instancia de host cambia a **detenido**.</span><span class="sxs-lookup"><span data-stu-id="578d6-123">The status of the host instance changes to **Stopped**.</span></span>  
  
 <span data-ttu-id="578d6-124">Una vez detenida la instancia, podrá volver a iniciarla o eliminarla, o bien quitar BizTalk Server del equipo.</span><span class="sxs-lookup"><span data-stu-id="578d6-124">After you stop a host instance, you can start it, delete it, or remove BizTalk Server from the computer.</span></span> <span data-ttu-id="578d6-125">Para obtener información acerca de cómo iniciar una instancia de host, consulte [cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md).</span><span class="sxs-lookup"><span data-stu-id="578d6-125">For information about starting a host instance, see [How to Start a Host Instance](../core/how-to-start-a-host-instance.md).</span></span> <span data-ttu-id="578d6-126">Para obtener información acerca de cómo eliminar una instancia de host, consulte [cómo eliminar una instancia de Host](../core/how-to-delete-a-host-instance.md).</span><span class="sxs-lookup"><span data-stu-id="578d6-126">For information about deleting a host instance, see [How to Delete a Host Instance](../core/how-to-delete-a-host-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="578d6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="578d6-127">See Also</span></span>  
 <span data-ttu-id="578d6-128">[Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="578d6-128">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="578d6-129">[Cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="578d6-129">[How to Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="578d6-130">[Cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="578d6-130">[How to Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="578d6-131">[Cómo eliminar una instancia de Host](../core/how-to-delete-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="578d6-131">[How to Delete a Host Instance](../core/how-to-delete-a-host-instance.md) </span></span>  
 [<span data-ttu-id="578d6-132">Cómo modificar las propiedades de la instancia de Host</span><span class="sxs-lookup"><span data-stu-id="578d6-132">How to Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)