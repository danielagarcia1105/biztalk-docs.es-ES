---
title: Cómo quitar una referencia a otra aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, references
ms.assetid: cc867706-7c56-4386-b7ec-9fd7cf6c83a4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de51adb1a9c42874025527ad458ecb6e3c311b3f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-reference-to-another-application"></a><span data-ttu-id="30c25-102">Cómo quitar una referencia a otra aplicación</span><span class="sxs-lookup"><span data-stu-id="30c25-102">How to Remove a Reference to Another Application</span></span>
<span data-ttu-id="30c25-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para quitar una referencia de una aplicación a otra.</span><span class="sxs-lookup"><span data-stu-id="30c25-103">This topic describes how to use the BizTalk Server Administration console to remove a reference from one application to another application.</span></span> <span data-ttu-id="30c25-104">Las referencias se quitan cuando se deja de utilizar un artefacto en la aplicación actual que existe en otra aplicación del mismo grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="30c25-104">You remove a reference when you no longer need to use an artifact in the current application that exists in another application in the same BizTalk group.</span></span> <span data-ttu-id="30c25-105">Para obtener más información sobre cómo agregar referencias, vea [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).</span><span class="sxs-lookup"><span data-stu-id="30c25-105">For more information on adding references, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
 <span data-ttu-id="30c25-106">Si los artefactos de la aplicación actual siguen usando artefactos de la otra aplicación, se producirá un error en la operación para quitar la referencia.</span><span class="sxs-lookup"><span data-stu-id="30c25-106">If artifacts in the current application still use artifacts in the referenced application, the operation to remove the reference will fail.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="30c25-107">Todas las aplicaciones de BizTalk Server contienen automáticamente una referencia a la aplicación BizTalk.System.</span><span class="sxs-lookup"><span data-stu-id="30c25-107">Every application in BizTalk Server automatically contains a reference to the BizTalk.System application.</span></span> <span data-ttu-id="30c25-108">Ello se debe a que todas las aplicaciones de BizTalk utilizan los artefactos que contiene BizTalk.System.</span><span class="sxs-lookup"><span data-stu-id="30c25-108">This is because the artifacts that BizTalk.System contains are used by every BizTalk application.</span></span> <span data-ttu-id="30c25-109">No debe quitar nunca las referencias a la aplicación BizTalk.System.</span><span class="sxs-lookup"><span data-stu-id="30c25-109">You should never remove a reference to the BizTalk.System application.</span></span> <span data-ttu-id="30c25-110">Si lo hace, la aplicación podría no funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="30c25-110">If you do, your application may not function correctly.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="30c25-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="30c25-111">Prerequisites</span></span>  
 <span data-ttu-id="30c25-112">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="30c25-112">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="30c25-113">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="30c25-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-reference-to-another-application"></a><span data-ttu-id="30c25-114">Para quitar una referencia a otra aplicación</span><span class="sxs-lookup"><span data-stu-id="30c25-114">To remove a reference to another application</span></span>  
  
1.  <span data-ttu-id="30c25-115">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="30c25-115">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="30c25-116">En el árbol de consola, expanda **administración de BizTalk Server**, haga clic en la aplicación desde el que desea quitar una referencia (la que hace referencia a otra aplicación) y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="30c25-116">In the console tree, expand  **BizTalk Server Administration**, right-click the application from which you want to remove a reference (the one that refers to another application), and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="30c25-117">En el panel izquierdo de la página de propiedades, haga clic en **referencias**.</span><span class="sxs-lookup"><span data-stu-id="30c25-117">In the left pane of the properties page, click **References**.</span></span>  
  
4.  <span data-ttu-id="30c25-118">En el panel derecho, haga clic en la aplicación que ya no desea hacer referencia desde esta aplicación, haga clic en **quitar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30c25-118">In the right pane, click the application that you no longer want to reference from this application, click **Remove**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c25-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="30c25-119">See Also</span></span>  
 [<span data-ttu-id="30c25-120">Creación y modificación de las aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="30c25-120">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)