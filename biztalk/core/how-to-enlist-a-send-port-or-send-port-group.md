---
title: "Cómo dar de alta un puerto de envío o grupo de puertos de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enlisting, send port groups
- enlisting, send ports
- send port groups, enlisting
- send ports, enlisting
- managing [send ports], enlisting
- managing [send port groups], enlisting
ms.assetid: d4298b8e-7dc7-4382-af86-c4db0982b7e0
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb42a4ceaa88ca3d04b5dfb6d6d3afc11847421a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enlist-a-send-port-or-send-port-group"></a><span data-ttu-id="0ebce-102">Cómo dar de alta un puerto de envío o un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="0ebce-102">How to Enlist a Send Port or Send Port Group</span></span>
<span data-ttu-id="0ebce-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para dar de alta un puerto de envío o un grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="0ebce-103">This topic describes how to use the BizTalk Server Administration console to enlist a send port or send port group.</span></span> <span data-ttu-id="0ebce-104">Al dar de alta un puerto de envío o un grupo de puertos de envío, estos se asocian con un host de BizTalk y se crean las suscripciones para el puerto de envío o para el grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="0ebce-104">Enlisting a send port or send port group associates the send port or send port group with a BizTalk host and creates the subscriptions for the send port or send port group.</span></span> <span data-ttu-id="0ebce-105">Si un grupo de puertos de envío no contiene un puerto de envío, al dar de alta el primero no se crea ninguna suscripción.</span><span class="sxs-lookup"><span data-stu-id="0ebce-105">If a send port group does not contain a send port, enlisting the send port group does not create any subscriptions.</span></span> <span data-ttu-id="0ebce-106">Además, al dar de alta un grupo de puertos de envío, no se cambia el estado los puertos de envío contenidos en aquél.</span><span class="sxs-lookup"><span data-stu-id="0ebce-106">In addition, enlisting a send port group does not change the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ebce-107">Al iniciar un puerto de envío o un grupo de puertos de envío, se dan de alta de forma automática.</span><span class="sxs-lookup"><span data-stu-id="0ebce-107">Starting a send port or send port group also automatically enlists it.</span></span> <span data-ttu-id="0ebce-108">Además, de forma predeterminada, al iniciar una aplicación se dan de alta y se inician todos sus artefactos.</span><span class="sxs-lookup"><span data-stu-id="0ebce-108">In addition, by default starting an application enlists and starts all of its artifacts.</span></span> <span data-ttu-id="0ebce-109">Para obtener más información, consulte [cómo iniciar un puerto de envío o grupo de puertos de envío](../core/how-to-start-a-send-port-or-send-port-group.md).</span><span class="sxs-lookup"><span data-stu-id="0ebce-109">For more information, see [How to Start a Send Port or Send Port Group](../core/how-to-start-a-send-port-or-send-port-group.md).</span></span> <span data-ttu-id="0ebce-110">Consulte también [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="0ebce-110">Also see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0ebce-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0ebce-111">Prerequisites</span></span>  
 <span data-ttu-id="0ebce-112">Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0ebce-112">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="0ebce-113">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="0ebce-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-a-send-port-or-send-port-group"></a><span data-ttu-id="0ebce-114">Para dar de alta un puerto de envío o un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="0ebce-114">To enlist a send port or send port group</span></span>  
  
1.  <span data-ttu-id="0ebce-115">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="0ebce-115">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0ebce-116">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de envío o grupo de puertos de envío que desea dar de alta.</span><span class="sxs-lookup"><span data-stu-id="0ebce-116">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to enlist.</span></span>  
  
3.  <span data-ttu-id="0ebce-117">Haga clic en **puertos de envío** o **grupos de puertos de envío**, haga clic en el puerto de envío o grupo de puertos de envío y, a continuación, haga clic en **dar de alta**.</span><span class="sxs-lookup"><span data-stu-id="0ebce-117">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Enlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebce-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ebce-118">See Also</span></span>  
 [<span data-ttu-id="0ebce-119">Administrar puertos de envío y grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="0ebce-119">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)