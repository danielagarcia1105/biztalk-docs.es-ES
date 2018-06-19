---
title: Cómo habilitar enrutamiento para mensajes con errores para un puerto de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports, routing
- managing [receive ports], errors
- managing [receive ports], failed messages
- enabling, routing
- messages, failed messages
- routing, messages
- managing [receive ports], routing
- messages, routing
- receive ports, errors
- routing, receive ports
- routing, failed messages
- errors, receive ports
ms.assetid: 22366664-545d-4981-9bde-4df48b115002
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59020dc67fa2d5b070ffc95b31648d382a66437b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254092"
---
# <a name="how-to-enable-routing-for-failed-messages-for-a-receive-port"></a><span data-ttu-id="a8144-102">Cómo habilitar el enrutamiento para mensajes con errores para un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="a8144-102">How to Enable Routing for Failed Messages for a Receive Port</span></span>
<span data-ttu-id="a8144-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para habilitar el enrutamiento para los mensajes procesados por un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="a8144-103">This topic describes how to use the BizTalk Server Administration console to enable routing for the messages processed by a receive port.</span></span> <span data-ttu-id="a8144-104">Al habilitar esta opción, BizTalk Server intentará enrutar cualquier mensaje con errores de procesamiento a una aplicación de suscripción (por ejemplo, a otra programación de orquestación o puerto de recepción).</span><span class="sxs-lookup"><span data-stu-id="a8144-104">When you enable this option, BizTalk Server will attempt to route any message that fails processing to a subscribing application (such as another receive port or orchestration schedule).</span></span> <span data-ttu-id="a8144-105">Cuando esta opción no está habilitada (lo que ocurre de forma predeterminada), BizTalk Server suspende los mensajes con errores y genera una confirmación negativa (NACK).</span><span class="sxs-lookup"><span data-stu-id="a8144-105">When this option is not enabled (the default), BizTalk Server suspends failed messages and generates a negative acknowledgment (NACK).</span></span> <span data-ttu-id="a8144-106">Para obtener información general sobre la administración de mensajes con errores, vea [enrutamiento de mensajes de error utilizando](../core/using-failed-message-routing.md).</span><span class="sxs-lookup"><span data-stu-id="a8144-106">For background information about managing failed messages, see [Using Failed Message Routing](../core/using-failed-message-routing.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a8144-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a8144-107">Prerequisites</span></span>  
 <span data-ttu-id="a8144-108">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a8144-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a8144-109">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="a8144-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enable-routing-for-failed-messages-for-a-receive-port"></a><span data-ttu-id="a8144-110">Para habilitar el enrutamiento para mensajes con errores para un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="a8144-110">To enable routing for failed messages for a receive port</span></span>  
  
1.  <span data-ttu-id="a8144-111">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a8144-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a8144-112">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee configurar el enrutamiento de mensajes con errores para un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="a8144-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure failed message routing for a receive port.</span></span>  
  
3.  <span data-ttu-id="a8144-113">Haga clic en **puertos de recepción**, haga clic en el puerto de recepción y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a8144-113">Click **Receive Ports**, right-click the receive port, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="a8144-114">Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8144-114">Select the **Enable routing for failed messages** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8144-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8144-115">See Also</span></span>  
 [<span data-ttu-id="a8144-116">Administrar puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="a8144-116">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)