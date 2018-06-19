---
title: Cómo quitar una asignación de una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, maps
- deleting, maps
- managing [maps], deleting
- managing [maps], applications
ms.assetid: 27d9bb08-36f0-46ff-ae9a-2247be6e3f96
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8b264809306e2cda40cc44be1287b6c2426fb43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254636"
---
# <a name="how-to-remove-a-map-from-an-application"></a><span data-ttu-id="4ce0c-102">Cómo quitar una asignación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="4ce0c-102">How to Remove a Map from an Application</span></span>
<span data-ttu-id="4ce0c-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para quitar una asignación de una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4ce0c-103">This topic describes how to use the BizTalk Server Administration console to remove a map from a BizTalk application.</span></span> <span data-ttu-id="4ce0c-104">Puede ser conveniente quitar una asignación después de implementar una versión nueva de ella.</span><span class="sxs-lookup"><span data-stu-id="4ce0c-104">You might want to remove a map after deploying a new version of the map.</span></span> <span data-ttu-id="4ce0c-105">Para obtener más información y consideraciones importantes para actualizar artefactos de la aplicación, consulte [actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md).</span><span class="sxs-lookup"><span data-stu-id="4ce0c-105">For more information and important considerations for updating application artifacts, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="4ce0c-106">Al quitar una asignación, ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ce0c-106">When you remove a map, the following occurs:</span></span>  
  
-   <span data-ttu-id="4ce0c-107">La asignación se elimina de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4ce0c-107">The map is deleted from the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="4ce0c-108">El ensamblado de BizTalk que contiene la asignación se elimina de la base de datos de administración de BizTalk, aunque no se quita del sistema de archivos local ni de la caché de ensamblados global (GAC), si existe en estas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="4ce0c-108">The BizTalk assembly that contains the map is deleted from the BizTalk Management database, but is not removed from the local file system or the global assembly cache (GAC), if it exists in these locations.</span></span>  
  
-   <span data-ttu-id="4ce0c-109">Como consecuencia de la eliminación del ensamblado de BizTalk, también se quitan de la base de datos de administración de BizTalk todos los artefactos que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4ce0c-109">As a consequence of the BizTalk assembly being deleted, all artifacts contained in the assembly are removed deleted the BizTalk Management database as well.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4ce0c-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4ce0c-110">Prerequisites</span></span>  
 <span data-ttu-id="4ce0c-111">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4ce0c-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4ce0c-112">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="4ce0c-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-map"></a><span data-ttu-id="4ce0c-113">Para quitar una asignación</span><span class="sxs-lookup"><span data-stu-id="4ce0c-113">To remove a map</span></span>  
  
1.  <span data-ttu-id="4ce0c-114">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="4ce0c-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4ce0c-115">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene la asignación para quitar y, a continuación, expanda la aplicación que contiene la asignación.</span><span class="sxs-lookup"><span data-stu-id="4ce0c-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the map to remove, and then expand the application containing the map.</span></span>  
  
3.  <span data-ttu-id="4ce0c-116">Haga clic en el **mapas** carpeta, haga clic en el mapa y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="4ce0c-116">Click the **Maps** folder, right-click the map, and then click **Remove**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ce0c-117">Para quitar varias asignaciones, mantenga presionada la tecla MAYÚS, haga clic en cada asignación para quitar, haga clic en una de las asignaciones y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="4ce0c-117">To remove multiple maps, hold down the shift key, click each map to remove, right-click one of the maps, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce0c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ce0c-118">See Also</span></span>  
 <span data-ttu-id="4ce0c-119">[Administración de mapas](../core/managing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="4ce0c-119">[Managing Maps](../core/managing-maps.md) </span></span>  
 <span data-ttu-id="4ce0c-120">[Cómo quitar un ensamblado de BizTalk desde una aplicación](../core/how-to-remove-a-biztalk-assembly-from-an-application.md) </span><span class="sxs-lookup"><span data-stu-id="4ce0c-120">[How to Remove a BizTalk Assembly from an Application](../core/how-to-remove-a-biztalk-assembly-from-an-application.md) </span></span>  
 [<span data-ttu-id="4ce0c-121">Anular la implementación de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4ce0c-121">Undeploying BizTalk Applications</span></span>](../core/undeploying-biztalk-applications.md)