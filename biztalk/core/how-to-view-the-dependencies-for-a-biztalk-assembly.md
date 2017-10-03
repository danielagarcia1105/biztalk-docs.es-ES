---
title: "Cómo ver las dependencias de un ensamblado de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- viewing, dependencies
- assemblies, dependencies
- managing [assemblies], dependencies
- assemblies, viewing
- viewing, assemblies
- managing [assemblies], viewing
ms.assetid: 872abc99-8248-4397-9fcb-24a0ba6f4757
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99fbc09a5adb59691a4914a8ddc341c8034c8bb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-the-dependencies-for-a-biztalk-assembly"></a><span data-ttu-id="8dd76-102">Cómo ver las relaciones de dependencia de un ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8dd76-102">How to View the Dependencies for a BizTalk Assembly</span></span>
<span data-ttu-id="8dd76-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para ver la lista de artefactos que tienen relaciones de dependencia con un ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8dd76-103">This topic describes how to use the BizTalk Server Administration console to view the list of artifacts that have dependencies on a BizTalk assembly.</span></span> <span data-ttu-id="8dd76-104">Para obtener información general sobre las dependencias y cómo afectan a la implementación de aplicaciones, consulte [dependencias e implementación de aplicaciones](../core/dependencies-and-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="8dd76-104">For background information about dependencies and how they affect application deployment, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8dd76-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8dd76-105">Prerequisites</span></span>  
 <span data-ttu-id="8dd76-106">Para llevar a cabo el procedimiento descrito en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server o del grupo de operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8dd76-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Operators group.</span></span> <span data-ttu-id="8dd76-107">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="8dd76-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-dependencies-of-a-biztalk-assembly"></a><span data-ttu-id="8dd76-108">Para ver las relaciones de dependencia de un ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8dd76-108">To view the dependencies of a BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="8dd76-109">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="8dd76-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="8dd76-110">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], el grupo de BizTalk que contiene el ensamblado de BizTalk del que desea ver las relaciones de dependencia y, a continuación, la aplicación que contiene el ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8dd76-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the BizTalk assembly for which you want to view dependencies, and then expand the application containing the BizTalk assembly.</span></span>  
  
3.  <span data-ttu-id="8dd76-111">Haga clic en el **recursos** carpeta, haga clic en el ensamblado de BizTalk y, a continuación, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="8dd76-111">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="8dd76-112">Haga clic en el **dependencias** ficha.</span><span class="sxs-lookup"><span data-stu-id="8dd76-112">Click the **Dependencies** tab.</span></span>  
  
     <span data-ttu-id="8dd76-113">En la lista se muestra el nombre y el estado de los artefactos que tienen relaciones de dependencia con el ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8dd76-113">The name and status of the artifacts that have dependencies on this BizTalk assembly are displayed in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd76-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dd76-114">See Also</span></span>  
 [<span data-ttu-id="8dd76-115">Administrar ensamblados de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8dd76-115">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)