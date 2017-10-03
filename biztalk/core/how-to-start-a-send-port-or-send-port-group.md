---
title: "Cómo iniciar un puerto de envío o grupo de puertos de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- starting, send port groups
- starting, send ports
- managing [send port groups], starting
- managing [send ports], starting
- send port groups, starting
- send ports, starting
ms.assetid: f17c0b7c-cad7-4c5e-a08c-3ebf838faa54
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 558a9b8444a38607f18757ff09196e44a3ae0b71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-start-a-send-port-or-send-port-group"></a><span data-ttu-id="a062f-102">Cómo iniciar un puerto de envío o un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="a062f-102">How to Start a Send Port or Send Port Group</span></span>
<span data-ttu-id="a062f-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para iniciar un puerto de envío o un grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="a062f-103">This topic describes how to use the BizTalk Server Administration console to start a send port or send port group.</span></span> <span data-ttu-id="a062f-104">Es preciso iniciar un puerto de envío o un grupo de ellos antes de poder procesar mensajes.</span><span class="sxs-lookup"><span data-stu-id="a062f-104">You must start a send port or send port group before it can process messages.</span></span> <span data-ttu-id="a062f-105">Si inicia un puerto de envío o un grupo de ellos que se ha dado de baja, BizTalk lo da de alta antes de iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="a062f-105">If you start an unenlisted send port or send port group, BizTalk enlists the send port or send port group before starting it.</span></span> <span data-ttu-id="a062f-106">Antes de poder iniciar un grupo de puertos de envío, es preciso que éste contenga, al menos, un puerto de envío dado de alta.</span><span class="sxs-lookup"><span data-stu-id="a062f-106">A send port group must contain at least one send port in an enlisted state before you can start the send port group.</span></span> <span data-ttu-id="a062f-107">El inicio y la detención de un grupo de puertos de envío no afecta al estado de ninguno de los puertos de envío que contiene.</span><span class="sxs-lookup"><span data-stu-id="a062f-107">Starting and stopping a send port group does not affect the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a062f-108">De forma predeterminada, al iniciar una aplicación de BizTalk, se inician todos los artefactos que contiene.</span><span class="sxs-lookup"><span data-stu-id="a062f-108">By default, starting a BizTalk application starts all of the artifacts that it contains.</span></span> <span data-ttu-id="a062f-109">Para obtener más información, consulte [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="a062f-109">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a062f-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a062f-110">Prerequisites</span></span>  
 <span data-ttu-id="a062f-111">Para realizar el procedimiento detallado en este tema, debe haber iniciado sesión como miembro del grupo de operadores o de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a062f-111">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a062f-112">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="a062f-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-a-send-port-or-send-port-group"></a><span data-ttu-id="a062f-113">Para iniciar un puerto de envío o un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="a062f-113">To start a send port or send port group</span></span>  
  
1.  <span data-ttu-id="a062f-114">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a062f-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a062f-115">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de envío o grupo de puertos de envío que desea iniciar.</span><span class="sxs-lookup"><span data-stu-id="a062f-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to start.</span></span>  
  
3.  <span data-ttu-id="a062f-116">Haga clic en **puertos de envío** o **grupos de puertos de envío**, haga clic en el puerto de envío o grupo de puertos de envío y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="a062f-116">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a062f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a062f-117">See Also</span></span>  
 [<span data-ttu-id="a062f-118">Administrar puertos de envío y grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="a062f-118">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)