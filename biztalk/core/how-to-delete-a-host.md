---
title: Eliminar un Host | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3df8719-27cb-4010-82e3-68226ab74b17
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fd5f54fa84ddb521444cfb3f2351a8062c4de00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="delete-a-host"></a><span data-ttu-id="eb433-102">Eliminar un Host</span><span class="sxs-lookup"><span data-stu-id="eb433-102">Delete a Host</span></span>
<span data-ttu-id="eb433-103">Solo se puede eliminar un host en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="eb433-103">You can delete a host only in the following circumstances:</span></span>  
  
-   <span data-ttu-id="eb433-104">No es el host predeterminado.</span><span class="sxs-lookup"><span data-stu-id="eb433-104">It is not the default host.</span></span>  
  
-   <span data-ttu-id="eb433-105">No es el único host que realiza el seguimiento de host.</span><span class="sxs-lookup"><span data-stu-id="eb433-105">It is not the only host that is performing host tracking.</span></span>  
  
-   <span data-ttu-id="eb433-106">No aloja ningún controlador de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="eb433-106">It is not hosting any adapter handlers.</span></span>  
  
-   <span data-ttu-id="eb433-107">No posee orquestaciones dadas de alta.</span><span class="sxs-lookup"><span data-stu-id="eb433-107">It has no enlisted orchestrations.</span></span>  
  
-   <span data-ttu-id="eb433-108">No hay instancias iniciadas del host.</span><span class="sxs-lookup"><span data-stu-id="eb433-108">There are no started instances of the host.</span></span>  
  
-   <span data-ttu-id="eb433-109">Si el host no está agrupado.</span><span class="sxs-lookup"><span data-stu-id="eb433-109">If the host is not clustered.</span></span>  
  
 <span data-ttu-id="eb433-110">Para obtener más información acerca de los hosts, consulte [Hosts](../core/hosts.md).</span><span class="sxs-lookup"><span data-stu-id="eb433-110">For more information about hosts, see [Hosts](../core/hosts.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eb433-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="eb433-111">Prerequisites</span></span>  
 <span data-ttu-id="eb433-112">Debe disponer de los siguientes derechos de usuario para crear hosts, modificar propiedades de hosts y eliminar hosts:</span><span class="sxs-lookup"><span data-stu-id="eb433-112">You must have the following user rights to create hosts, modify host properties, and delete hosts:</span></span>  
  
-   <span data-ttu-id="eb433-113">Además, debe ser miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="eb433-113">You must be a member of the BizTalk Server Administrators group.</span></span>  
  
-   <span data-ttu-id="eb433-114">Debe disponer de los siguientes derechos en SQL Server:</span><span class="sxs-lookup"><span data-stu-id="eb433-114">You must have the following rights in SQL Server:</span></span>  
  
    -   <span data-ttu-id="eb433-115">Debe ser administrador de SQL Server o miembro de las funciones de base de datos db_owner o db_securityadmin de SQL Server en la base de datos de seguimiento de BizTalk (BizTalk DTADb), bases de datos de cuadro de mensajes (BizTalkMsgBoxDb) y la base de datos de importación principal de BAM (BAMPrimaryImport).</span><span class="sxs-lookup"><span data-stu-id="eb433-115">You must be either a SQL Server administrator, or a member of the db_owner or db_securityadmin SQL Server database roles in the BizTalk Tracking database (BizTalk DTADb), MessageBox databases (BizTalkMsgBoxDb), and the BAM Primary Import database (BAMPrimaryImport).</span></span>  
  
    -   <span data-ttu-id="eb433-116">Debe ser miembro del rol sysadmin de SQL Server en todos los equipos donde haya bases de datos de cuadro de mensajes, o miembro del rol db_owner o db_ddladmin de SQL Server para todas las bases de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="eb433-116">You must be a member of the sysadmin SQL Server role on all the computers where there are MessageBox databases, or a member of the db_owner or db_ddladmin SQL Server role for all the MessageBox databases.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="eb433-117">Pasos</span><span class="sxs-lookup"><span data-stu-id="eb433-117">Steps</span></span> 
  
1.  <span data-ttu-id="eb433-118">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="eb433-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="eb433-119">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **Hosts**.</span><span class="sxs-lookup"><span data-stu-id="eb433-119">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Hosts**.</span></span>  
  
3.  <span data-ttu-id="eb433-120">En el panel de detalles, haga clic en el host que desea eliminar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="eb433-120">In the details pane, right-click the host you want to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="eb433-121">En el **Confirmar eliminación de host** cuadro de diálogo, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="eb433-121">In the **Confirm host delete** dialog box, click **Yes**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb433-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb433-122">See Also</span></span>  
-  [<span data-ttu-id="eb433-123">Administrar hosts de BizTalk e instancias de host</span><span class="sxs-lookup"><span data-stu-id="eb433-123">Managing BizTalk Hosts and Host Instances</span></span>](../core/managing-biztalk-hosts-and-host-instances.md)   
-  [<span data-ttu-id="eb433-124">Cómo crear un nuevo Host</span><span class="sxs-lookup"><span data-stu-id="eb433-124">How to Create a New Host</span></span>](../core/how-to-create-a-new-host.md)   
-  [<span data-ttu-id="eb433-125">Cómo modificar las propiedades de Host</span><span class="sxs-lookup"><span data-stu-id="eb433-125">How to Modify Host Properties</span></span>](../core/how-to-modify-host-properties.md)   
-  <span data-ttu-id="eb433-126">**MSBTS_Host (WMI)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="eb433-126">**MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>