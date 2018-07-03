---
title: Cómo ver las referencias de una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, viewing
- applications, referencing
ms.assetid: 5f1026e1-c73e-495d-8160-9ba68f38b9d8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a23583edde1e1edbf4f0613904ebf24271a225f5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979277"
---
# <a name="how-to-view-the-references-of-an-application"></a><span data-ttu-id="64bad-102">Cómo ver las referencias de una aplicación</span><span class="sxs-lookup"><span data-stu-id="64bad-102">How to View the References of an Application</span></span>
<span data-ttu-id="64bad-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para ver la lista de aplicaciones a las que hace referencia la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="64bad-103">This topic describes how to use the BizTalk Server Administration console to view the list of applications to which the current application has references.</span></span> <span data-ttu-id="64bad-104">Para obtener más información sobre cómo agregar referencias, vea [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).</span><span class="sxs-lookup"><span data-stu-id="64bad-104">For more information about adding references, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span> <span data-ttu-id="64bad-105">También puede ver la lista de aplicaciones que incluyen referencias a esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="64bad-105">You can also view the list of applications that have references to this application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="64bad-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="64bad-106">Prerequisites</span></span>  
 <span data-ttu-id="64bad-107">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="64bad-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="64bad-108">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="64bad-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-references-for-an-application"></a><span data-ttu-id="64bad-109">Para ver las referencias correspondientes a una aplicación</span><span class="sxs-lookup"><span data-stu-id="64bad-109">To view the references for an application</span></span>  
  
1. <span data-ttu-id="64bad-110">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="64bad-110">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="64bad-111">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en la aplicación cuyas referencias desea ver y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="64bad-111">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click the application whose references you want to view, and click **Properties**.</span></span>  
  
3. <span data-ttu-id="64bad-112">En el panel izquierdo de la página de propiedades, haga clic en **referencias**.</span><span class="sxs-lookup"><span data-stu-id="64bad-112">In the left pane of the properties page, click **References**.</span></span>  
  
    <span data-ttu-id="64bad-113">Las aplicaciones a las que hace referencia esta aplicación aparecen enumeradas en la sección superior del panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="64bad-113">The applications to which this application refers are listed in the upper section of the right pane.</span></span> <span data-ttu-id="64bad-114">Las aplicaciones que hacen referencia a esta aplicación aparecen enumeradas en la sección inferior del panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="64bad-114">The applications that refer to this application are listed in the lower section of the right pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64bad-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="64bad-115">See Also</span></span>  
 [<span data-ttu-id="64bad-116">Creación y modificación de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="64bad-116">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)