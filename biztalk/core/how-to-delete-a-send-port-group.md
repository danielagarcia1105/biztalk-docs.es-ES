---
title: Cómo eliminar un grupo de puertos de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send port groups, deleting
- managing [send port groups], deleting
- deleting, send port groups
ms.assetid: 90c01e58-d35c-4cb2-ac6d-92199199fb42
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86ddecbe657b8ea52a47133c5237bbad6a10b2f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248900"
---
# <a name="how-to-delete-a-send-port-group"></a><span data-ttu-id="24746-102">Cómo eliminar un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="24746-102">How to Delete a Send Port Group</span></span>
<span data-ttu-id="24746-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para eliminar un grupo de puertos de envío de una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="24746-103">This topic describes how use the BizTalk Server Administration console to delete a send port group from a BizTalk application.</span></span> <span data-ttu-id="24746-104">Al hacerlo, el grupo de puertos de envío también se eliminará de la base de datos de administración de BizTalk del grupo.</span><span class="sxs-lookup"><span data-stu-id="24746-104">When you do this, the send port group is also deleted from the BizTalk Management database for the group.</span></span> <span data-ttu-id="24746-105">Al eliminar un grupo de puertos de envío no se elimina ninguno de los puertos de envío que contiene.</span><span class="sxs-lookup"><span data-stu-id="24746-105">Deleting a send port group does not delete any send ports that it contains.</span></span>  
  
 <span data-ttu-id="24746-106">Sólo es posible eliminar un grupo de puertos de envío si se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="24746-106">You can delete a send port group only if it meets the following conditions:</span></span>  
  
-   <span data-ttu-id="24746-107">Ninguna orquestación está enlazada con el grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="24746-107">An orchestration is not bound to the send port group.</span></span> <span data-ttu-id="24746-108">Si este es el caso, puede quitar el enlace siguiendo las instrucciones de [cómo separar una orquestación](../core/how-to-unbind-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="24746-108">If this is the case, you can remove the binding by following the instructions in [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="24746-109">Se ha detenido y dado de baja el grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="24746-109">The send port group is both stopped and unenlisted.</span></span> <span data-ttu-id="24746-110">Para obtener instrucciones acerca de detener y dar de baja un puerto de envío, consulte [cómo dar de baja un puerto de envío o grupo de puertos de envío](../core/how-to-unenlist-a-send-port-or-send-port-group.md) y [cómo detener un puerto de envío o un grupo de puertos de envío](../core/how-to-stop-a-send-port-or-send-port-group.md).</span><span class="sxs-lookup"><span data-stu-id="24746-110">For instructions on stopping and unenlisting a send port, see [How to Unenlist a Send Port or Send Port Group](../core/how-to-unenlist-a-send-port-or-send-port-group.md) and [How to Stop a Send Port or Send Port Group](../core/how-to-stop-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="24746-111">Ninguna entidad hace referencia al grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="24746-111">The send port group is not referenced by a party.</span></span> <span data-ttu-id="24746-112">Para obtener instrucciones acerca de cómo quitar una referencia a un grupo de puertos de envío de una entidad, consulte [cómo ver o editar una entidad](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).</span><span class="sxs-lookup"><span data-stu-id="24746-112">For instructions on removing a reference to a send port group from a party, see [How to View or Edit a Party](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="24746-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="24746-113">Prerequisites</span></span>  
 <span data-ttu-id="24746-114">Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="24746-114">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="24746-115">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="24746-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-send-port-group"></a><span data-ttu-id="24746-116">Para eliminar un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="24746-116">To delete a send port group</span></span>  
  
1.  <span data-ttu-id="24746-117">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="24746-117">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="24746-118">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el grupo de puertos de envío que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="24746-118">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the send port group that you want to delete.</span></span>  
  
3.  <span data-ttu-id="24746-119">Haga clic en **grupos de puertos de envío**, haga clic en el grupo de puertos de envío y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="24746-119">Click **Send Port Groups**, right-click the send port group, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24746-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="24746-120">See Also</span></span>  
 [<span data-ttu-id="24746-121">Crear y configurar grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="24746-121">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)