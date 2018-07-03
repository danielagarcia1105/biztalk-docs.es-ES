---
title: Cómo agregar una ubicación de recepción para un puerto de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, adding to receive ports
- managing [receive ports], adding receive locations
- receive ports, adding receive locations
- adding, receive locations
ms.assetid: a71d50dc-629e-4b7f-aa59-6d2274d4cac3
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c657c96c7714f04d18a2bd8d6d2d7ef90ad9cbd1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999005"
---
# <a name="how-to-add-a-receive-location-to-a-receive-port"></a><span data-ttu-id="34a6e-102">Cómo agregar una ubicación de recepción a un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="34a6e-102">How to Add a Receive Location to a Receive Port</span></span>
<span data-ttu-id="34a6e-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para agregar una nueva ubicación de recepción a un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="34a6e-103">This topic describes how to use the BizTalk Server Administration console to add a new receive location to a receive port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34a6e-104">Puede enlazar un puerto de recepción a una orquestación cuando se configura una aplicación, como se describe en [cómo configurar una aplicación](../core/how-to-configure-an-application.md) o al enlazar una orquestación, como se describe en [cómo configurar enlaces para un Orquestación](../core/how-to-configure-bindings-for-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="34a6e-104">You can bind a receive port to an orchestration when you configure an application, as described in [How to Configure an Application](../core/how-to-configure-an-application.md) or when you bind an orchestration, as described in [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="34a6e-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="34a6e-105">Prerequisites</span></span>  
 <span data-ttu-id="34a6e-106">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="34a6e-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="34a6e-107">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="34a6e-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-receive-location-to-a-receive-port"></a><span data-ttu-id="34a6e-108">Para agregar una ubicación de recepción a un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="34a6e-108">To add a receive location to a receive port</span></span>  
  
1. <span data-ttu-id="34a6e-109">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="34a6e-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="34a6e-110">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk a cuyos puertos de recepción desee agregar una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="34a6e-110">In the console tree, expand the BizTalk group and the BizTalk application for which you want to add a receive location to a receive port.</span></span>  
  
3. <span data-ttu-id="34a6e-111">Haga clic en **puertos de recepción**, haga clic en el puerto de recepción al que desea agregar una ubicación de recepción, seleccione **New**y, a continuación, haga clic en **ubicación de recepción**.</span><span class="sxs-lookup"><span data-stu-id="34a6e-111">Click **Receive Ports**, right-click the receive port to which you want to add a receive location, point to **New**, and then click **Receive Location**.</span></span>  
  
4. <span data-ttu-id="34a6e-112">En **nombre**, escriba un nombre para la nueva ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="34a6e-112">In **Name**, type a name for the new receive location.</span></span>  
  
5. <span data-ttu-id="34a6e-113">Configurar las propiedades de la ubicación de recepción siguiendo las instrucciones de [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md)y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="34a6e-113">Configure properties for the receive location by following the instructions in [How to Create a Receive Location](../core/how-to-create-a-receive-location.md), and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a6e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="34a6e-114">See Also</span></span>  
 [<span data-ttu-id="34a6e-115">Administración de puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="34a6e-115">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)