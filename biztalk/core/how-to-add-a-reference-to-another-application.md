---
title: Cómo agregar una referencia a otra aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, referencing
ms.assetid: 6a177560-ee1f-403a-a68a-ade409a39a35
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6781ebc9c6cb0c3f7c68dfbbcff683193e15ac15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018555"
---
# <a name="how-to-add-a-reference-to-another-application"></a><span data-ttu-id="d336d-102">Cómo agregar una referencia a otra aplicación</span><span class="sxs-lookup"><span data-stu-id="d336d-102">How to Add a Reference to Another Application</span></span>
<span data-ttu-id="d336d-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para agregar una referencia de una aplicación a otra.</span><span class="sxs-lookup"><span data-stu-id="d336d-103">This topic describes how to use the BizTalk Server Administration console to add a reference from one application to another application.</span></span> <span data-ttu-id="d336d-104">También puede agregar una referencia a la otra aplicación al importar la aplicación mediante el Asistente para importación, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="d336d-104">You can also add a reference to the other application when you import your application by using the Import Wizard, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="d336d-105">Las referencias se agregan cuando se desea utilizar un artefacto en la aplicación actual que ya existe en otra aplicación del mismo grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d336d-105">You add a reference when you want to use an artifact in the current application that already exists in another application in the same BizTalk group.</span></span> <span data-ttu-id="d336d-106">Esto se debe a que la mayoría de los tipos de artefactos deben ser únicos dentro de un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d336d-106">This is because most types of artifacts must be unique in a BizTalk group.</span></span> <span data-ttu-id="d336d-107">En lugar de agregar el artefacto duplicado a la aplicación actual, se agrega una referencia a la otra aplicación que ya contiene el artefacto.</span><span class="sxs-lookup"><span data-stu-id="d336d-107">Rather than adding the duplicate artifact to the current application, you add a reference to the other application that already contains the artifact.</span></span> <span data-ttu-id="d336d-108">Para obtener más información, consulte [artefactos que deben ser únicos en una aplicación o grupo](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span><span class="sxs-lookup"><span data-stu-id="d336d-108">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span>  
  
 <span data-ttu-id="d336d-109">No es necesario agregar una referencia cuando desea utilizar un directorio virtual o un certificado que ya existe en otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="d336d-109">It is not necessary to add a reference when you want to use a virtual directory or a certificate that already exists in another application.</span></span> <span data-ttu-id="d336d-110">Además, no se recomienda este procedimiento porque puede crear una referencia circular.</span><span class="sxs-lookup"><span data-stu-id="d336d-110">Furthermore, we recommend against doing this because it can create a circular reference.</span></span>  
  
 <span data-ttu-id="d336d-111">Al importar una aplicación con dependencias, también se pueden importar las referencias.</span><span class="sxs-lookup"><span data-stu-id="d336d-111">When you import an application that has dependencies, references can be imported as well.</span></span> <span data-ttu-id="d336d-112">Al agregar una referencia a otra aplicación, no olvide que esto afecta al modo de implementar ambas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d336d-112">When adding a reference to another application, bear in mind that this affects the way you deploy both applications.</span></span> <span data-ttu-id="d336d-113">Para obtener más información, consulte [dependencias e implementación de aplicación](../core/dependencies-and-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="d336d-113">For more information, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d336d-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d336d-114">Prerequisites</span></span>  
 <span data-ttu-id="d336d-115">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d336d-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d336d-116">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="d336d-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-reference-to-another-application"></a><span data-ttu-id="d336d-117">Para agregar una referencia a otra aplicación</span><span class="sxs-lookup"><span data-stu-id="d336d-117">To add a reference to another application</span></span>  
  
1. <span data-ttu-id="d336d-118">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d336d-118">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d336d-119">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y haga clic con el botón secundario en la aplicación en la que desea crear una referencia.</span><span class="sxs-lookup"><span data-stu-id="d336d-119">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and right-click the application in which you want to create a reference.</span></span> <span data-ttu-id="d336d-120">Se trata de la aplicación en la que desea utilizar un artefacto que se encuentra en otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="d336d-120">This is the application in which you want to use an artifact that is contained in another application.</span></span>  
  
3. <span data-ttu-id="d336d-121">Seleccione **agregar** y, a continuación, haga clic en **referencias**.</span><span class="sxs-lookup"><span data-stu-id="d336d-121">Point to **Add** and then click **References**.</span></span>  
  
4. <span data-ttu-id="d336d-122">En **aplicaciones**, active la casilla de verificación de la aplicación a la que desea agregar una referencia (la aplicación que contiene el artefacto o artefactos que desea usar) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d336d-122">In **Applications**, select the check box of the application to which you want to add a reference (the application containing the artifact or artifacts that you want to use), and then click **OK**.</span></span>  
  
    <span data-ttu-id="d336d-123">La referencia se agregará a la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="d336d-123">The reference is added to the current application.</span></span> <span data-ttu-id="d336d-124">En el árbol de consola, se agrega un icono de mano a la aplicación a la que hace referencia desde esta aplicación para indicar que hay una o varias aplicaciones que hacen referencia a ella.</span><span class="sxs-lookup"><span data-stu-id="d336d-124">In the console tree, a hand icon is added to the application that you referred from this application to indicate that it is referenced by one or more other applications.</span></span>  
  
    <span data-ttu-id="d336d-125">![Icono de aplicación compartido](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")</span><span class="sxs-lookup"><span data-stu-id="d336d-125">![Shared application icon](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d336d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d336d-126">See Also</span></span>  
 [<span data-ttu-id="d336d-127">Creación y modificación de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d336d-127">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)