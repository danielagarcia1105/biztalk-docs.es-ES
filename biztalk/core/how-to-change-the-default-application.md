---
title: "Cómo cambiar la aplicación predeterminada | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, default
- applications, modifying
- modifying, applications
ms.assetid: cfa5e88f-0bbb-4edd-a840-722dcdcce266
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33b4ffb6fbbb2463b20a7d344d0f7f27811de23b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-default-application"></a><span data-ttu-id="c6dd6-102">Cómo cambiar la aplicación predeterminada</span><span class="sxs-lookup"><span data-stu-id="c6dd6-102">How to Change the Default Application</span></span>
<span data-ttu-id="c6dd6-103">En este tema se describe cómo cambiar la aplicación predeterminada mediante la edición de las propiedades de una aplicación en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-103">This topic describes how to change the default application by editing the properties of an application in the BizTalk Server Administration console.</span></span> <span data-ttu-id="c6dd6-104">También puede cambiar la aplicación predeterminada mediante la creación de una nueva aplicación y especificar que la aplicación de forma predeterminada, como se describe en [cómo crear una aplicación](../core/how-to-create-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="c6dd6-104">You can also change the default application by creating a new application and specifying it as the default application, as described in [How to Create an Application](../core/how-to-create-an-application.md).</span></span>  
  
 <span data-ttu-id="c6dd6-105">Al instalar BizTalk Server, en la base de datos de administración de BizTalk se crea una aplicación predeterminada llamada Aplicación de BizTalk 1 y aparece en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-105">When you install BizTalk Server, a default application named BizTalk Application 1 is created in the BizTalk Management database and appears in the BizTalk Server Administration console.</span></span> <span data-ttu-id="c6dd6-106">Al actualizar desde una versión anterior de BizTalk Server, los artefactos se colocan automáticamente en esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-106">When you upgrade from an earlier version of BizTalk Server, your artifacts are automatically placed in this application.</span></span> <span data-ttu-id="c6dd6-107">Además, al importar un archivo de Windows Installer (.msi) con BTSTask sin especificar una aplicación, los artefactos del archivo .msi se importan en la aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-107">In addition, when you import a Windows Installer (.msi) file by using BTSTask without specifying an application, the artifacts in the .msi file are imported into the default application.</span></span>  
  
 <span data-ttu-id="c6dd6-108">La aplicación predeterminada no se puede eliminar, aunque puede cambiar de aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-108">You cannot delete the default application; however, you can change which application is the default.</span></span> <span data-ttu-id="c6dd6-109">Si cambia la aplicación predeterminada, puede optar por eliminar la aplicación que anteriormente era la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-109">If you change the default application, you can then delete the application that was previously the default, if you want.</span></span> <span data-ttu-id="c6dd6-110">Para obtener instrucciones, consulte [cómo eliminar una aplicación de BizTalk del grupo de BizTalk](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).</span><span class="sxs-lookup"><span data-stu-id="c6dd6-110">For instructions, see [How to Delete a BizTalk Application from the BizTalk Group](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="c6dd6-111">Al cambiar la aplicación predeterminada, todos los artefactos permanecen en la aplicación que originalmente era la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-111">When you change the default application, all of the artifacts remain in the application that was originally the default.</span></span> <span data-ttu-id="c6dd6-112">Si lo desea, puede mover de forma explícita los artefactos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-112">You can explicitly move the artifacts out of the application, if you want.</span></span> <span data-ttu-id="c6dd6-113">Para obtener instrucciones, consulte [cómo mover un artefacto a una aplicación diferente](../core/how-to-move-an-artifact-to-a-different-application.md).</span><span class="sxs-lookup"><span data-stu-id="c6dd6-113">For instructions, see [How to Move an Artifact to a Different Application](../core/how-to-move-an-artifact-to-a-different-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c6dd6-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c6dd6-114">Prerequisites</span></span>  
 <span data-ttu-id="c6dd6-115">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="c6dd6-116">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="c6dd6-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-default-application"></a><span data-ttu-id="c6dd6-117">Para cambiar la aplicación predeterminada</span><span class="sxs-lookup"><span data-stu-id="c6dd6-117">To change the default application</span></span>  
  
1.  <span data-ttu-id="c6dd6-118">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c6dd6-119">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, haga clic en la aplicación que desea establecer como predeterminada y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-119">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, right-click the application that you want to make the default, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c6dd6-120">Seleccione el **establecer esta aplicación como predeterminada** casilla de verificación y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c6dd6-120">Select the **Make this the default application** check box, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6dd6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6dd6-121">See Also</span></span>  
 [<span data-ttu-id="c6dd6-122">Creación y modificación de las aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c6dd6-122">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)