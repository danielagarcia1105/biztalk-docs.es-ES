---
title: Cómo eliminar una ubicación de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], deleting
- receive locations, deleting
- deleting, receive locations
ms.assetid: aa859355-af4c-48d9-b224-78fd3ef618fc
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3acc788e1c0bfeb9e722aee0b55d66e6f09d096
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991445"
---
# <a name="how-to-delete-a-receive-location"></a><span data-ttu-id="782eb-102">Cómo eliminar una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="782eb-102">How to Delete a Receive Location</span></span>
<span data-ttu-id="782eb-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para eliminar una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="782eb-103">This topic describes how to use the BizTalk Server Administration console to delete a receive location.</span></span> <span data-ttu-id="782eb-104">Al eliminar una ubicación de recepción, se elimina de la base de datos de administración de BizTalk y ya no se muestra más en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="782eb-104">When you delete a receive location, it is removed from the BizTalk Management database and is no longer displayed in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="782eb-105">Al eliminar una ubicación de recepción, tenga en cuenta que los siguientes puntos son importantes:</span><span class="sxs-lookup"><span data-stu-id="782eb-105">When deleting a receive location, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="782eb-106">Antes de poder eliminar una ubicación de recepción, debe deshabilitarse, como se describe en [cómo deshabilitar una ubicación de recepción](../core/how-to-disable-a-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="782eb-106">Before you can delete a receive location, it must first be disabled, as described in [How to Disable a Receive Location](../core/how-to-disable-a-receive-location.md).</span></span>  
  
-   <span data-ttu-id="782eb-107">No se puede eliminar la ubicación de recepción primaria para un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="782eb-107">You cannot delete the primary receive location for a receive port.</span></span> <span data-ttu-id="782eb-108">Si intenta hacer esto, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="782eb-108">If you attempt this, you will receive an error message.</span></span> <span data-ttu-id="782eb-109">Para eliminar la ubicación de recepción, puede eliminar el puerto de recepción, que también elimina todas las ubicaciones de recepción que contiene, o bien establecer otra ubicación de recepción como primaria y eliminar después la ubicación de recepción original.</span><span class="sxs-lookup"><span data-stu-id="782eb-109">To delete the receive location, you can either delete the receive port, which also deletes all of the receive locations that it contains, or you can make a different receive location primary and then delete the original receive location.</span></span> <span data-ttu-id="782eb-110">Para obtener instrucciones sobre cómo realizar una ubicación de recepción de la ubicación de recepción primaria, consulte [cómo editar las propiedades de una ubicación de recepción](../core/how-to-edit-the-properties-of-a-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="782eb-110">For instructions on making a receive location the primary receive location, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
-   <span data-ttu-id="782eb-111">Después de eliminar una ubicación de recepción, reinicie los procesos de trabajo de host aislado correspondientes a la ubicación de recepción eliminada.</span><span class="sxs-lookup"><span data-stu-id="782eb-111">After you delete a receive location, restart the Isolated Host Worker Processes corresponding to the deleted receive location.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="782eb-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="782eb-112">Prerequisites</span></span>  
 <span data-ttu-id="782eb-113">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="782eb-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="782eb-114">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="782eb-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-receive-location"></a><span data-ttu-id="782eb-115">Para eliminar una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="782eb-115">To delete a receive location</span></span>  
  
1. <span data-ttu-id="782eb-116">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="782eb-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="782eb-117">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk de los que desea eliminar una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="782eb-117">In the console tree, expand the BizTalk group and the BizTalk application for which you want to delete a receive location.</span></span>  
  
3. <span data-ttu-id="782eb-118">Haga clic en **ubicaciones de recepción**, haga clic en la ubicación de recepción que desea eliminar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="782eb-118">Click **Receive Locations**, right-click the receive location to delete, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782eb-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="782eb-119">See Also</span></span>  
 [<span data-ttu-id="782eb-120">Administración de ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="782eb-120">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)