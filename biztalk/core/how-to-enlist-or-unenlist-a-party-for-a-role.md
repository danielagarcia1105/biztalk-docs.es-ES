---
title: Cómo dar de alta o baja una entidad para un rol | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [role links], enlisting
- enlisting, role links
- role links, unenlisting
- role links, enlisting
- managing [role links], unenlisting
ms.assetid: 06fc2a64-3add-400c-9f9d-fab22fdf5366
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8af988a001e63ba210e5d5c224eeb486800b7286
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253788"
---
# <a name="how-to-enlist-or-unenlist-a-party-for-a-role"></a><span data-ttu-id="64b6c-102">Cómo dar de alta o de baja una entidad para un rol</span><span class="sxs-lookup"><span data-stu-id="64b6c-102">How to Enlist or Unenlist a Party for a Role</span></span>
<span data-ttu-id="64b6c-103">En este tema se explica cómo usar la consola de administración de BizTalk Server para dar de alta o de baja una entidad para un rol.</span><span class="sxs-lookup"><span data-stu-id="64b6c-103">This topic describes how to use the BizTalk Server Administration console to enlist or unenlist a party for a role.</span></span> <span data-ttu-id="64b6c-104">Al dar de alta una entidad para un rol, ésta se asigna al rol; por el contrario, al darla de baja, la entidad se quita del rol.</span><span class="sxs-lookup"><span data-stu-id="64b6c-104">Enlisting a party for a role assigns the party to the role and unenlisting the party removes the party from the role.</span></span>  
  
 <span data-ttu-id="64b6c-105">Al dar de alta o de baja una entidad para un rol, tenga en cuenta los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="64b6c-105">When enlisting or unenlisting a party for a role, bear in mind the following points:</span></span>  
  
-   <span data-ttu-id="64b6c-106">Debe crear una entidad antes de darla de alta.</span><span class="sxs-lookup"><span data-stu-id="64b6c-106">You must create a party before you can enlist it.</span></span> <span data-ttu-id="64b6c-107">Para obtener instrucciones, consulte [cómo crear una entidad](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span><span class="sxs-lookup"><span data-stu-id="64b6c-107">For instructions, see [How to Create a Party](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span></span>  
  
-   <span data-ttu-id="64b6c-108">Una entidad se puede dar de alta o de baja para un rol sin necesidad de reiniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64b6c-108">You can enlist or unenlist a party for a role without needing to restart the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64b6c-109">El desarrollador de aplicaciones puede dar de alta o baja a una entidad durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="64b6c-109">The application developer can enlist or unenlist a party during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="64b6c-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="64b6c-110">Prerequisites</span></span>  
 <span data-ttu-id="64b6c-111">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="64b6c-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="64b6c-112">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="64b6c-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-or-unenlist-a-party-for-a-role"></a><span data-ttu-id="64b6c-113">Para dar de alta o de baja una entidad para un rol</span><span class="sxs-lookup"><span data-stu-id="64b6c-113">To enlist or unenlist a party for a role</span></span>  
  
1.  <span data-ttu-id="64b6c-114">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="64b6c-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="64b6c-115">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el vínculo de función para la que desea dar de alta o dar de baja a una entidad.</span><span class="sxs-lookup"><span data-stu-id="64b6c-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the role link for which you want to enlist or unenlist a party.</span></span>  
  
3.  <span data-ttu-id="64b6c-116">Haga clic en **vínculos de función**, haga clic en el vínculo de función para la que desea dar de alta o baja una entidad y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="64b6c-116">Click **Role Links**, right-click the role link for which you want to enlist or unenlist a party, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="64b6c-117">Para dar de alta una entidad, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="64b6c-117">To enlist a party, do the following:</span></span>  
  
    -   <span data-ttu-id="64b6c-118">Haga clic en **dar de alta** y haga clic en la entidad para dar de alta.</span><span class="sxs-lookup"><span data-stu-id="64b6c-118">Click **Enlist** and click the party to enlist.</span></span>  
  
    -   <span data-ttu-id="64b6c-119">Haga clic en **enlazar**, en la **puerto de envío** lista desplegable, haga clic en el envío de puerto para que se utilizará para esta entidad y, a continuación, haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="64b6c-119">Click **Bind**, in the **Send Port** drop-down list, click the send port to use for this party, and then click **OK** twice.</span></span>  
  
5.  <span data-ttu-id="64b6c-120">Para dar de baja una entidad, haga clic en la entidad, haga clic en **dar de baja**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="64b6c-120">To unenlist a party, click the party, click **Unenlist**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b6c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="64b6c-121">See Also</span></span>  
 [<span data-ttu-id="64b6c-122">Administrar vínculos de rol</span><span class="sxs-lookup"><span data-stu-id="64b6c-122">Managing Role Links</span></span>](../core/managing-role-links.md)