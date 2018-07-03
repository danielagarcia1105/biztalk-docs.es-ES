---
title: Cómo crear un grupo de puertos de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send port groups
- send port groups, creating
- managing [send port groups], creating
ms.assetid: de3e72aa-83f4-4760-9f39-a488f904f1d3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f97177ac1222cd246f43af98eebb66797ae78fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980949"
---
# <a name="how-to-create-a-send-port-group"></a><span data-ttu-id="c757c-102">Cómo crear un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="c757c-102">How to Create a Send Port Group</span></span>
<span data-ttu-id="c757c-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para crear un grupo de puertos de envío en una aplicación de BizTalk para, a continuación, agregarle puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="c757c-103">This topic describes how to use the BizTalk Server Administration console to create a send port group in a BizTalk application and then add send ports to it.</span></span> <span data-ttu-id="c757c-104">Puede agregar puertos de envío unidireccional estático sólo a un grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="c757c-104">You can add static one-way send ports only to a send port group.</span></span> <span data-ttu-id="c757c-105">Para enrutar mensajes, un grupo de puertos de envío debe contener, como mínimo, un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c757c-105">A send port group must contain at least one send port to route messages.</span></span>  
  
 <span data-ttu-id="c757c-106">Es posible agregar un puerto de envío existente en una aplicación diferente.</span><span class="sxs-lookup"><span data-stu-id="c757c-106">You can add a send port that exists in a different application.</span></span> <span data-ttu-id="c757c-107">Si lo hace, tendrá que agregar una referencia de la aplicación que contenga el grupo de puertos de envío a la que contenga el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c757c-107">If you do this, you must add a reference from the application containing the send port group to the application containing the send port.</span></span> <span data-ttu-id="c757c-108">Para obtener instrucciones, consulte [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).</span><span class="sxs-lookup"><span data-stu-id="c757c-108">For instructions, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c757c-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c757c-109">Prerequisites</span></span>  
 <span data-ttu-id="c757c-110">Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c757c-110">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="c757c-111">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="c757c-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-create-a-send-port-group"></a><span data-ttu-id="c757c-112">Para crear un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="c757c-112">To create a send port group</span></span>  
  
1. <span data-ttu-id="c757c-113">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c757c-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="c757c-114">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk en los que desee crear un grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="c757c-114">In the console tree, expand the BizTalk group and the BizTalk application in which you want to create a send port group.</span></span>  
  
3. <span data-ttu-id="c757c-115">Haga clic en **grupos de puertos de envío**, apunte a **New**y, a continuación, haga clic en **grupo de puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="c757c-115">Right-click **Send Port Groups**, point to **New**, and then click **Send Port Group**.</span></span>  
  
4. <span data-ttu-id="c757c-116">En el **nombre** , escriba un nombre para el grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="c757c-116">In the **Name** box, type a name for the send port group.</span></span>  
  
5. <span data-ttu-id="c757c-117">En **puertos de envío**, haga clic en la lista desplegable bajo **nombre**y haga clic en el puerto de envío para agregar al grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="c757c-117">In **Send ports**, click the drop-down list under **Name**, and click the send port to add to the send port group.</span></span> <span data-ttu-id="c757c-118">Repita esta acción con cada uno de los puertos de envío que desee agregar al grupo.</span><span class="sxs-lookup"><span data-stu-id="c757c-118">Repeat for each send port you want to add to the group.</span></span> <span data-ttu-id="c757c-119">Para crear un nuevo puerto de envío y agregarlo, haga clic en **\<nuevo puerto de envío... \>** y, a continuación, siga las instrucciones de [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).</span><span class="sxs-lookup"><span data-stu-id="c757c-119">To create a new send port and add it, click **\<New send port…\>** and then follow the instructions in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
6. <span data-ttu-id="c757c-120">Cuando termine de agregar puertos de envío para el grupo de puertos de envío, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c757c-120">When finished adding send ports to the send port group, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c757c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c757c-121">See Also</span></span>  
 [<span data-ttu-id="c757c-122">Creación y configuración de grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="c757c-122">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)