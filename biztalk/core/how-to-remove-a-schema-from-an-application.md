---
title: Cómo quitar un esquema de una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, schemas
- applications, schemas
- schemas, deleting
- managing [schemas], deleting
- managing [schemas], applications
- schemas, applications
ms.assetid: 17dd5869-b56c-4166-9f02-03e04e691eda
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0693d94736c4ef3d8ad5ee561ed6b42650c90ab3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985437"
---
# <a name="how-to-remove-a-schema-from-an-application"></a><span data-ttu-id="fd653-102">Cómo quitar un esquema de una aplicación</span><span class="sxs-lookup"><span data-stu-id="fd653-102">How to Remove a Schema from an Application</span></span>
<span data-ttu-id="fd653-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para quitar un esquema de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd653-103">This topic describes how to use the BizTalk Server Administration console to remove a schema from an application.</span></span> <span data-ttu-id="fd653-104">Este procedimiento quita el esquema de la base de datos de administración de BizTalk y también para el grupo.</span><span class="sxs-lookup"><span data-stu-id="fd653-104">This procedure removes the schema from the BizTalk Management database for the group as well.</span></span> <span data-ttu-id="fd653-105">Puede ser conveniente quitar un esquema después de implementar una versión nueva de él.</span><span class="sxs-lookup"><span data-stu-id="fd653-105">You might want to remove a schema after deploying a new version of the schema.</span></span> <span data-ttu-id="fd653-106">Para obtener más información y consideraciones importantes para actualizar artefactos de la aplicación, consulte [actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md).</span><span class="sxs-lookup"><span data-stu-id="fd653-106">For more information and important considerations for updating application artifacts, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="fd653-107">Cuando se quita un esquema y en la aplicación existe una versión anterior de éste con el mismo espacio de nombres raíz, la versión anterior se convierte en la versión activa.</span><span class="sxs-lookup"><span data-stu-id="fd653-107">When you remove a schema, and a previous version of the schema having the same root namespace exists in the application, the previous version will become active.</span></span>  
  
 <span data-ttu-id="fd653-108">Al quitar un esquema, ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd653-108">When you remove a schema, the following occurs:</span></span>  
  
-   <span data-ttu-id="fd653-109">El esquema se elimina de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fd653-109">The schema is deleted from the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="fd653-110">El ensamblado de BizTalk que contiene el esquema se elimina de la base de datos de administración de BizTalk, aunque no se quita del sistema de archivos local ni de la caché de ensamblados global (GAC), si existe en estas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="fd653-110">The BizTalk assembly that contains the schema is deleted from the BizTalk Management database, but is not removed from the local file system or the global assembly cache (GAC), if it exists in these locations.</span></span>  
  
-   <span data-ttu-id="fd653-111">Como consecuencia de la eliminación del ensamblado de BizTalk, también se quitan de la base de datos de administración de BizTalk todos los artefactos que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fd653-111">As a consequence of the BizTalk assembly being deleted, all artifacts contained in the assembly are removed deleted the BizTalk Management database as well.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fd653-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fd653-112">Prerequisites</span></span>  
 <span data-ttu-id="fd653-113">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fd653-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="fd653-114">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="fd653-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-schema"></a><span data-ttu-id="fd653-115">Para quitar un esquema</span><span class="sxs-lookup"><span data-stu-id="fd653-115">To remove a schema</span></span>  
  
1. <span data-ttu-id="fd653-116">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="fd653-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="fd653-117">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene el esquema para quitar y la aplicación que contiene el esquema.</span><span class="sxs-lookup"><span data-stu-id="fd653-117">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema to remove and the application containing the schema.</span></span>  
  
3. <span data-ttu-id="fd653-118">Haga clic en **esquemas**, haga clic en el esquema y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="fd653-118">Click **Schemas**, right-click the schema, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd653-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd653-119">See Also</span></span>  
 [<span data-ttu-id="fd653-120">Administración de esquemas</span><span class="sxs-lookup"><span data-stu-id="fd653-120">Managing Schemas</span></span>](../core/managing-schemas.md)