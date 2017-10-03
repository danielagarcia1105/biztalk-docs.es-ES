---
title: "Cómo eliminar un puerto de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [receive ports], deleting
- deleting, receive ports
- receive ports, deleting
ms.assetid: 69cd86f7-e3cc-4a50-8d15-5f978c94a6be
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c5ad0b1d69747f3a890fbc20c63b8aa76c30639
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-a-receive-port"></a><span data-ttu-id="4da0d-102">Cómo eliminar un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="4da0d-102">How to Delete a Receive Port</span></span>
<span data-ttu-id="4da0d-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para eliminar un puerto de recepción de una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4da0d-103">This topic describes how to use the BizTalk Server Administration console to delete a receive port from a BizTalk application.</span></span> <span data-ttu-id="4da0d-104">Al hacer esto, el puerto de recepción también se elimina de la base de datos de administración de BizTalk para el grupo, además de las ubicaciones de recepción del puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="4da0d-104">When you do this, the receive port is also deleted from the BizTalk Management database for the group, as are all receive locations in this receive port.</span></span>  
  
 <span data-ttu-id="4da0d-105">Para que esta operación se lleve a cabo correctamente, el puerto de recepción no puede estar enlazado a una orquestación.</span><span class="sxs-lookup"><span data-stu-id="4da0d-105">For this operation to succeed, the receive port cannot be bound to an orchestration.</span></span> <span data-ttu-id="4da0d-106">Para obtener instrucciones acerca de cómo quitar los enlaces para un puerto de recepción, consulte [cómo separar una orquestación](../core/how-to-unbind-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="4da0d-106">For instructions on removing the bindings for a receive port, see [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4da0d-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4da0d-107">Prerequisites</span></span>  
 <span data-ttu-id="4da0d-108">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4da0d-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4da0d-109">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="4da0d-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-receive-port"></a><span data-ttu-id="4da0d-110">Para eliminar un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="4da0d-110">To delete a receive port</span></span>  
  
1.  <span data-ttu-id="4da0d-111">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="4da0d-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4da0d-112">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de recepción que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="4da0d-112">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the receive port that you want to delete.</span></span>  
  
3.  <span data-ttu-id="4da0d-113">Haga clic en **puertos de recepción**, haga clic en el puerto de recepción y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4da0d-113">Click **Receive Ports**, right-click the receive port, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da0d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4da0d-114">See Also</span></span>  
 [<span data-ttu-id="4da0d-115">Administrar puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="4da0d-115">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)