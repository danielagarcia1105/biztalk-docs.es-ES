---
title: Cómo agregar un puerto de envío a un grupo de puertos de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send port groups], adding send ports
- managing [send ports], adding to send port groups
- send port groups, send ports
- send ports, send port groups
- adding, send ports
ms.assetid: a61b3b32-c05e-40b9-abf1-09b7065fb6a2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6c2b616952aa4f24e40ddd56e035a6de4a77c58
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007181"
---
# <a name="how-to-add-a-send-port-to-a-send-port-group"></a><span data-ttu-id="d815f-102">Cómo agregar un puerto de envío a un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="d815f-102">How to Add a Send Port to a Send Port Group</span></span>
<span data-ttu-id="d815f-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para agregar uno o varios puertos de envío a un grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="d815f-103">This topic describes how to use the BizTalk Server Administration console to add one or more send ports to a send port group.</span></span> <span data-ttu-id="d815f-104">Solo se pueden agregar puertos de envío estáticos unidireccionales a un grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="d815f-104">You can only add one-way static send ports to a send port group.</span></span>  
  
 <span data-ttu-id="d815f-105">Es posible agregar un puerto de envío existente en una aplicación diferente.</span><span class="sxs-lookup"><span data-stu-id="d815f-105">You can add a send port that exists in a different application.</span></span> <span data-ttu-id="d815f-106">Si lo hace, tendrá que agregar una referencia de la aplicación que contenga el grupo de puertos de envío a la que contenga el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="d815f-106">If you do this, you must add a reference from the application containing the send port group to the application containing the send port.</span></span> <span data-ttu-id="d815f-107">Para obtener instrucciones, consulte [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).</span><span class="sxs-lookup"><span data-stu-id="d815f-107">For instructions, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d815f-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d815f-108">Prerequisites</span></span>  
 <span data-ttu-id="d815f-109">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d815f-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d815f-110">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="d815f-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-send-port-to-a-send-port-group"></a><span data-ttu-id="d815f-111">Para agregar un puerto de envío a un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="d815f-111">To add a send port to a send port group</span></span>  
  
1. <span data-ttu-id="d815f-112">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d815f-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d815f-113">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk a cuyos grupos de puertos de envío desee agregar un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="d815f-113">In the console tree, expand the BizTalk group and the BizTalk application in which you want to add a send port to a send port group.</span></span>  
  
3. <span data-ttu-id="d815f-114">Haga clic en **grupos de puertos de envío**, haga clic en el grupo de puertos de envío y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d815f-114">Click **Send Port Groups**, right-click the send port group, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="d815f-115">En **puertos de envío**, haga clic en la lista desplegable bajo **nombre**y haga clic en el puerto de envío para agregar al grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="d815f-115">In **Send ports**, click the drop-down list under **Name**, and click the send port to add to the send port group.</span></span> <span data-ttu-id="d815f-116">Repita esta acción con cada uno de los puertos de envío que desee agregar al grupo.</span><span class="sxs-lookup"><span data-stu-id="d815f-116">Repeat for each send port you want to add to the group.</span></span> <span data-ttu-id="d815f-117">Para crear un nuevo puerto de envío y agregarlo, haga clic en **\<nuevo puerto de envío... \>** y, a continuación, siga las instrucciones de [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).</span><span class="sxs-lookup"><span data-stu-id="d815f-117">To create a new send port and add it, click **\<New send port…\>** and then follow the instructions in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
5. <span data-ttu-id="d815f-118">Cuando termine de agregar puertos de envío para el grupo de puertos de envío, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d815f-118">When finished adding send ports to the send port group, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d815f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d815f-119">See Also</span></span>  
 <span data-ttu-id="d815f-120">[Crear y configurar grupos de puertos de envío](../core/creating-and-configuring-send-port-groups.md) </span><span class="sxs-lookup"><span data-stu-id="d815f-120">[Creating and Configuring Send Port Groups](../core/creating-and-configuring-send-port-groups.md) </span></span>  
 [<span data-ttu-id="d815f-121">Creación y configuración de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="d815f-121">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)