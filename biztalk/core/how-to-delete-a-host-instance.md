---
title: Eliminar una instancia de Host | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35a06480-0962-4bdc-add2-56f979a2f1c9
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ecc7999e807b4036f80e8fdd1941d447f7af163
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023586"
---
# <a name="delete-a-host-instance"></a><span data-ttu-id="2e689-102">Eliminar una instancia de Host</span><span class="sxs-lookup"><span data-stu-id="2e689-102">Delete a Host Instance</span></span>

## <a name="overview"></a><span data-ttu-id="2e689-103">Información general</span><span class="sxs-lookup"><span data-stu-id="2e689-103">Overview</span></span>
<span data-ttu-id="2e689-104">El Instrumental de administración de Windows (WMI) o la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se usan para eliminar instancias de host.</span><span class="sxs-lookup"><span data-stu-id="2e689-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or Windows Management Instrumentation (WMI) to delete host instances.</span></span> <span data-ttu-id="2e689-105">Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md).</span><span class="sxs-lookup"><span data-stu-id="2e689-105">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span> <span data-ttu-id="2e689-106">Para obtener información sobre cómo usar WMI para eliminar una instancia de host, consulte **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="2e689-106">For information about using WMI to delete a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="2e689-107">Cuando se elimina una instancia de host, la instancia de tiempo de ejecución de BizTalk Server se elimina del servidor asociado y la base de datos de administración de BizTalk se actualiza para eliminar esa instancia del host.</span><span class="sxs-lookup"><span data-stu-id="2e689-107">When you delete a host instance, the instance of the BizTalk Server runtime is removed from the associated server and the BizTalk Management database is updated to remove that instance from the host.</span></span>  
  
 <span data-ttu-id="2e689-108">Para evitar que se pierdan mensajes cuando se elimina una instancia de host, BizTalk Server completa todo el procesamiento antes de que la instancia se elimine por completo.</span><span class="sxs-lookup"><span data-stu-id="2e689-108">To avoid losing messages when you delete a host instance, BizTalk Server completes all processing before the instance is actually removed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2e689-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2e689-109">Prerequisites</span></span>  
 <span data-ttu-id="2e689-110">Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores y del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2e689-110">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="2e689-111">Además, también es preciso que sea miembro de la función de base de datos de SQL Server db_securityadmin y de la función de SQL Server securityadmin en los servidores en los que se encuentren las siguientes bases de datos:</span><span class="sxs-lookup"><span data-stu-id="2e689-111">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="2e689-112">Importación principal de BAM (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="2e689-112">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="2e689-113">Administración de BizTalk (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="2e689-113">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="2e689-114">Cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) (todo)</span><span class="sxs-lookup"><span data-stu-id="2e689-114">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="2e689-115">Seguimiento de BizTalk (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="2e689-115">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="2e689-116">Motor de reglas (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="2e689-116">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2e689-117">Se recomienda actualizar la información de cuenta de las instancias de host mediante el script de Instrumental de administración de Windows (WMI) o la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2e689-117">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="2e689-118">Con ello, se garantiza que BizTalk Server pueda actualizar la información de cuenta en las bases de datos de BizTalk Server y mantener la configuración de seguridad entre las bases de datos y la instancia de host sincronizada.</span><span class="sxs-lookup"><span data-stu-id="2e689-118">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="2e689-119">Pasos</span><span class="sxs-lookup"><span data-stu-id="2e689-119">Steps</span></span>
  
1. <span data-ttu-id="2e689-120">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2e689-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="2e689-121">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="2e689-121">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3. <span data-ttu-id="2e689-122">En el panel de detalles, haga clic en la instancia de host que desea eliminar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="2e689-122">In the details pane, right-click the host instance you want to delete, and then click **Delete**.</span></span>  
  
4. <span data-ttu-id="2e689-123">En el **Confirmar eliminación de instancia de host** cuadro de diálogo, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2e689-123">In the **Confirm delete host instance** dialog box, click **Yes**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2e689-124">Si BizTalk Server no puede eliminar la instancia de host, aparece un cuadro de diálogo en el que puede forzar la eliminación de la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="2e689-124">If BizTalk Server cannot delete the host instance, a dialog box appears in which you can force the deletion of the host instance.</span></span> <span data-ttu-id="2e689-125">Después de leer la información proporcionada, haga clic en **Sí** para eliminar la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="2e689-125">After reading the information provided, click **Yes** to delete the host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e689-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e689-126">See Also</span></span>  
 <span data-ttu-id="2e689-127">[Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="2e689-127">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="2e689-128">[Cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="2e689-128">[How to Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="2e689-129">[Cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="2e689-129">[How to Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="2e689-130">[Cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="2e689-130">[How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 [<span data-ttu-id="2e689-131">Cómo modificar las propiedades de instancia de Host</span><span class="sxs-lookup"><span data-stu-id="2e689-131">How to Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)