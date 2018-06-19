---
title: Cómo iniciar una orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], starting
- starting, orchestrations
- orchestrations, starting
ms.assetid: 83411279-ee6f-4d68-aa3b-b5cd5e106088
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e277c078a36129a125937114ee9287a1e97999b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255428"
---
# <a name="how-to-start-an-orchestration"></a><span data-ttu-id="e3bec-102">Cómo iniciar una orquestación</span><span class="sxs-lookup"><span data-stu-id="e3bec-102">How to Start an Orchestration</span></span>
<span data-ttu-id="e3bec-103">En este tema se explica cómo utilizar la consola de administración de BizTalk Server para iniciar una orquestación.</span><span class="sxs-lookup"><span data-stu-id="e3bec-103">This topic describes how to use the BizTalk Server Administration console to start an orchestration.</span></span> <span data-ttu-id="e3bec-104">Al iniciar una orquestación, ésta comienza a procesar mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="e3bec-104">When you start an orchestration, it begins processing incoming messages.</span></span>  
  
 <span data-ttu-id="e3bec-105">Al iniciar una orquestación, tenga en cuenta que los siguientes puntos son importantes:</span><span class="sxs-lookup"><span data-stu-id="e3bec-105">When starting and orchestration, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="e3bec-106">Antes de poder iniciar la orquestación, debe darse de alta junto con todos los puertos de envío y grupos de puertos de envío asociados con ella.</span><span class="sxs-lookup"><span data-stu-id="e3bec-106">Before you can start the orchestration, it must be enlisted, along with all of the send ports and send port groups associated with it.</span></span> <span data-ttu-id="e3bec-107">Para obtener instrucciones, consulte [cómo dar de alta una orquestación](../core/how-to-enlist-an-orchestration.md) y [cómo dar de alta un puerto de envío o grupo de puertos de envío](../core/how-to-enlist-a-send-port-or-send-port-group.md).</span><span class="sxs-lookup"><span data-stu-id="e3bec-107">For instructions, see [How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) and [How to Enlist a Send Port or Send Port Group](../core/how-to-enlist-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="e3bec-108">Al iniciar una orquestación, no se inicia automáticamente todos los puertos de envío asociados.</span><span class="sxs-lookup"><span data-stu-id="e3bec-108">Starting an orchestration does not automatically start any associated send ports.</span></span> <span data-ttu-id="e3bec-109">Debe iniciar por separado, tal como se describe en [cómo iniciar un puerto de envío o grupo de puertos de envío](../core/how-to-start-a-send-port-or-send-port-group.md).</span><span class="sxs-lookup"><span data-stu-id="e3bec-109">You must start them separately, as described in [How to Start a Send Port or Send Port Group](../core/how-to-start-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="e3bec-110">Si da de alta los puertos de envío o los grupos de puertos de envío asociados con la orquestación, pero no los inicia, BizTalk Server coloca todos los mensajes enviados a este puerto de envío o grupo de puertos de envío en la cola de suspensión del host en el que se dio de alta al puerto de envío o al grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="e3bec-110">If you enlist the send ports and/or send port groups associated with this orchestration, but do not start them, BizTalk Server places any messages sent to this send port or send port group in the suspended queue of the host where you enlisted the send port or send port group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3bec-111">El desarrollador de aplicaciones puede iniciar una orquestación para probar su funcionalidad durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="e3bec-111">The application developer can start an orchestration to test its functionality during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e3bec-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e3bec-112">Prerequisites</span></span>  
 <span data-ttu-id="e3bec-113">Para realizar el procedimiento detallado en este tema, debe haber iniciado sesión como miembro del grupo de operadores o de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e3bec-113">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="e3bec-114">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="e3bec-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-an-orchestration"></a><span data-ttu-id="e3bec-115">Para iniciar una orquestación</span><span class="sxs-lookup"><span data-stu-id="e3bec-115">To start an orchestration</span></span>  
  
1.  <span data-ttu-id="e3bec-116">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="e3bec-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e3bec-117">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación que desea iniciar.</span><span class="sxs-lookup"><span data-stu-id="e3bec-117">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to start.</span></span>  
  
3.  <span data-ttu-id="e3bec-118">Haga clic en **orquestaciones**, haga clic en la orquestación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="e3bec-118">Click **Orchestrations**, right-click the orchestration, and then click **Start**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e3bec-119">Si, antes de iniciar la orquestación, no ha dado de alta el puerto de envío o los grupos de puertos de envío asociados, aparecerá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="e3bec-119">If you did not first enlist the associated send port and send port groups before starting the orchestration, you will see an error message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3bec-120">Para iniciar varias orquestaciones a la vez, mantenga presionada la tecla MAYÚS y seleccione cada orquestación, haga clic en una orquestación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="e3bec-120">To start multiple orchestrations at once, hold down the shift key and select each orchestration, right-click an orchestration, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3bec-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3bec-121">See Also</span></span>  
 <span data-ttu-id="e3bec-122">[Administrar orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="e3bec-122">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="e3bec-123">[Cómo detener una orquestación](../core/how-to-stop-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="e3bec-123">[How to Stop an Orchestration](../core/how-to-stop-an-orchestration.md) </span></span>  
 [<span data-ttu-id="e3bec-124">Cómo iniciar y detener una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e3bec-124">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)