---
title: Cómo dar de baja un puerto de envío o grupo de puertos de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unenlisting, send port groups
- send port groups, unenlisting
- managing [send ports], unenlisting
- managing [send port groups], unenlisting
- unenlisting, send ports
- send ports, unenlisting
ms.assetid: 3185adad-2efa-4abd-a532-77ae6c7b4c1d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac2599ae3d06a75506de244a4f996a9e77cef6ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256676"
---
# <a name="how-to-unenlist-a-send-port-or-send-port-group"></a><span data-ttu-id="29b65-102">Cómo dar de baja un puerto de envío o un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="29b65-102">How to Unenlist a Send Port or Send Port Group</span></span>
<span data-ttu-id="29b65-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para dar de baja un puerto de envío o un grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="29b65-103">This topic describes how to use the BizTalk Server Administration console to unenlist a send port or send port group.</span></span> <span data-ttu-id="29b65-104">Al dar de baja un puerto de envío o un grupo de puertos de envío, se eliminan todas las suscripciones asociadas con el puerto de envío o con el grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="29b65-104">Unenlisting a send port or send port group eliminates all subscriptions associated with that send port or send port group.</span></span> <span data-ttu-id="29b65-105">Es posible dar de baja los grupos de puertos de envío o los puertos de envío que estén detenidos o en ejecución.</span><span class="sxs-lookup"><span data-stu-id="29b65-105">You can unenlist both running and stopped send ports or send port groups.</span></span> <span data-ttu-id="29b65-106">Al dar de baja un puerto de envío o un grupo de puertos de envío, éstos se detienen.</span><span class="sxs-lookup"><span data-stu-id="29b65-106">Unenlisting a send port or send port group automatically stops it.</span></span>  
  
 <span data-ttu-id="29b65-107">Por ejemplo, es posible que desee dar de baja un puerto de envío o un grupo de puertos de envío para editar sus enlaces, o en el caso de que tenga la intención de quitar aquéllos del entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="29b65-107">For example, you may want to unenlist a send port or send port group to edit its bindings, or if you want to remove the send port or send port group from the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="29b65-108">No es posible dar de baja el último puerto de envío dado de alta en un grupo de puertos de envío que se haya dado de alta o que esté en ejecución.</span><span class="sxs-lookup"><span data-stu-id="29b65-108">You cannot unenlist the last enlisted send port within a send port group that is enlisted or running.</span></span> <span data-ttu-id="29b65-109">El estado de los puertos de envío pertenecientes a un grupo no se modifica cuando este último se da de baja.</span><span class="sxs-lookup"><span data-stu-id="29b65-109">Unenlisting a send port group does not change the state of any send ports that it contains.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="29b65-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="29b65-110">Prerequisites</span></span>  
 <span data-ttu-id="29b65-111">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="29b65-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="29b65-112">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="29b65-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-unenlist-a-send-port-or-send-port-group"></a><span data-ttu-id="29b65-113">Para dar de baja un puerto de envío o un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="29b65-113">To unenlist a send port or send port group</span></span>  
  
1.  <span data-ttu-id="29b65-114">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="29b65-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="29b65-115">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de envío o grupo de puertos de envío que desea dar de baja.</span><span class="sxs-lookup"><span data-stu-id="29b65-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to unenlist.</span></span>  
  
3.  <span data-ttu-id="29b65-116">Haga clic en **puertos de envío** o **grupos de puertos de envío**, haga clic en el puerto de envío o grupo de puertos de envío y, a continuación, haga clic en **dar de baja**.</span><span class="sxs-lookup"><span data-stu-id="29b65-116">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Unenlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b65-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="29b65-117">See Also</span></span>  
 [<span data-ttu-id="29b65-118">Administrar puertos de envío y grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="29b65-118">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)