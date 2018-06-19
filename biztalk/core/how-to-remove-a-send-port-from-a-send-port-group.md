---
title: Cómo quitar un puerto de envío de un grupo de puertos de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send port groups, deleting send ports
- managing [send port groups], deleting send ports
- managing [send ports], deleting send ports
- deleting, send ports
- send ports, deleting from send port groups
ms.assetid: a2289bfe-5bc9-4bc7-949c-5152ffb5bc62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d109064a1286bcd622479a4075ef2d23dc8d320c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254524"
---
# <a name="how-to-remove-a-send-port-from-a-send-port-group"></a><span data-ttu-id="ff04b-102">Cómo quitar un puerto de envío de un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="ff04b-102">How to Remove a Send Port from a Send Port Group</span></span>
<span data-ttu-id="ff04b-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para quitar un puerto de envío de un grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="ff04b-103">This topic describes how to use the BizTalk Server Administration console to remove a send port from a send port group.</span></span> <span data-ttu-id="ff04b-104">Al hacerlo, el puerto de envío no se eliminará de la aplicación o de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ff04b-104">When you do this, the send port is not deleted from the application or the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="ff04b-105">Antes de poder quitar un puerto de envío, su estado debe ser detenido o dado de baja.</span><span class="sxs-lookup"><span data-stu-id="ff04b-105">Before you can remove a send port, it must be in a stopped or unenlisted state.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff04b-106">Para enrutar mensajes, un grupo de puertos de envío debe contener al menos un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ff04b-106">To route messages, a send port group must contain at least one send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ff04b-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ff04b-107">Prerequisites</span></span>  
 <span data-ttu-id="ff04b-108">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ff04b-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="ff04b-109">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="ff04b-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-send-port-from-a-send-port-group"></a><span data-ttu-id="ff04b-110">Para quitar un puerto de envío de un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="ff04b-110">To remove a send port from a send port group</span></span>  
  
1.  <span data-ttu-id="ff04b-111">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="ff04b-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ff04b-112">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk de cuyos grupos de puertos de envío desee quitar un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ff04b-112">In the console tree, expand the BizTalk group and the BizTalk application in which you want to remove a send port from a send port group.</span></span>  
  
3.  <span data-ttu-id="ff04b-113">Haga clic en **grupos de puertos de envío**, haga clic en el grupo de puertos de envío y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ff04b-113">Click **Send Port Groups**, right-click the send port group, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="ff04b-114">En **nombre**, haga clic en el puerto de envío para quitar y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="ff04b-114">Under **Name**, click the send port to remove, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff04b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff04b-115">See Also</span></span>  
 <span data-ttu-id="ff04b-116">[Crear y configurar grupos de puertos de envío](../core/creating-and-configuring-send-port-groups.md) </span><span class="sxs-lookup"><span data-stu-id="ff04b-116">[Creating and Configuring Send Port Groups](../core/creating-and-configuring-send-port-groups.md) </span></span>  
 [<span data-ttu-id="ff04b-117">Crear y configurar puertos de envío</span><span class="sxs-lookup"><span data-stu-id="ff04b-117">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)