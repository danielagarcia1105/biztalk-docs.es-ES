---
title: Cómo eliminar un puerto de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], deleting
- deleting, receive ports
- receive ports, deleting
ms.assetid: 69cd86f7-e3cc-4a50-8d15-5f978c94a6be
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65f72ad5bfef99bca7474ea01f3d07ecbe9ef2b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975157"
---
# <a name="how-to-delete-a-receive-port"></a><span data-ttu-id="9add5-102">Cómo eliminar un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="9add5-102">How to Delete a Receive Port</span></span>
<span data-ttu-id="9add5-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para eliminar un puerto de recepción de una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9add5-103">This topic describes how to use the BizTalk Server Administration console to delete a receive port from a BizTalk application.</span></span> <span data-ttu-id="9add5-104">Al hacer esto, el puerto de recepción también se elimina de la base de datos de administración de BizTalk para el grupo, además de las ubicaciones de recepción del puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="9add5-104">When you do this, the receive port is also deleted from the BizTalk Management database for the group, as are all receive locations in this receive port.</span></span>  
  
 <span data-ttu-id="9add5-105">Para que esta operación se lleve a cabo correctamente, el puerto de recepción no puede estar enlazado a una orquestación.</span><span class="sxs-lookup"><span data-stu-id="9add5-105">For this operation to succeed, the receive port cannot be bound to an orchestration.</span></span> <span data-ttu-id="9add5-106">Para obtener instrucciones acerca de cómo quitar los enlaces para un puerto de recepción, consulte [cómo separar una orquestación](../core/how-to-unbind-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="9add5-106">For instructions on removing the bindings for a receive port, see [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9add5-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9add5-107">Prerequisites</span></span>  
 <span data-ttu-id="9add5-108">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9add5-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="9add5-109">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="9add5-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-receive-port"></a><span data-ttu-id="9add5-110">Para eliminar un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="9add5-110">To delete a receive port</span></span>  
  
1. <span data-ttu-id="9add5-111">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="9add5-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="9add5-112">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de recepción que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="9add5-112">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the receive port that you want to delete.</span></span>  
  
3. <span data-ttu-id="9add5-113">Haga clic en **puertos de recepción**, haga clic en el puerto de recepción y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="9add5-113">Click **Receive Ports**, right-click the receive port, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9add5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9add5-114">See Also</span></span>  
 [<span data-ttu-id="9add5-115">Administración de puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="9add5-115">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)