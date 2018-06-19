---
title: Cómo detener un puerto de envío o un grupo de puertos de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], stopping
- managing [send port groups], stopping
- stopping, send ports
- send port groups, stopping
- stopping, send port groups
- send ports, stopping
ms.assetid: a7a5eab3-34fe-4417-900a-c37ec16ec009
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ac3391a7a14955198f7e7635765665d48af1ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255324"
---
# <a name="how-to-stop-a-send-port-or-send-port-group"></a><span data-ttu-id="33aa1-102">Cómo detener un puerto de envío o un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="33aa1-102">How to Stop a Send Port or Send Port Group</span></span>
<span data-ttu-id="33aa1-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para detener un puerto de envío o un grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="33aa1-103">This topic describes how to use the BizTalk Server Administration console to stop a send port or send port group.</span></span> <span data-ttu-id="33aa1-104">Al detener un puerto de envío o un grupo de puertos de envío, deja de procesar mensajes.</span><span class="sxs-lookup"><span data-stu-id="33aa1-104">When you stop a send port or send port group, it no longer processes messages.</span></span> <span data-ttu-id="33aa1-105">BizTalk Server suspende todos los mensajes de activación de un puerto de envío o un grupo de puertos de envío detenido.</span><span class="sxs-lookup"><span data-stu-id="33aa1-105">BizTalk Server suspends all activation messages to a stopped send port or send port group.</span></span> <span data-ttu-id="33aa1-106">La detención de un grupo de puertos de envío no afecta al estado de ninguno de los puertos de envío que contiene.</span><span class="sxs-lookup"><span data-stu-id="33aa1-106">Stopping a send port group does not affect the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33aa1-107">De forma predeterminada, al iniciar una aplicación de BizTalk, se inician todos los artefactos que contiene.</span><span class="sxs-lookup"><span data-stu-id="33aa1-107">By default, starting a BizTalk application starts all of the artifacts that it contains.</span></span> <span data-ttu-id="33aa1-108">Para obtener más información, consulte [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="33aa1-108">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="33aa1-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="33aa1-109">Prerequisites</span></span>  
 <span data-ttu-id="33aa1-110">Para llevar a cabo el procedimiento descrito en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores o del grupo de operadores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="33aa1-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="33aa1-111">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="33aa1-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-stop-a-send-port-or-send-port-group"></a><span data-ttu-id="33aa1-112">Para detener un puerto de envío o un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="33aa1-112">To stop a send port or send port group</span></span>  
  
1.  <span data-ttu-id="33aa1-113">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="33aa1-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="33aa1-114">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de envío o grupo de puertos de envío que desea Detener.</span><span class="sxs-lookup"><span data-stu-id="33aa1-114">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to stop.</span></span>  
  
3.  <span data-ttu-id="33aa1-115">Haga clic en **puertos de envío** o **grupos de puertos de envío**, haga clic en el puerto de envío o puerto de envío y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="33aa1-115">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port, and then click **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33aa1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="33aa1-116">See Also</span></span>  
 [<span data-ttu-id="33aa1-117">Administrar puertos de envío y grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="33aa1-117">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)