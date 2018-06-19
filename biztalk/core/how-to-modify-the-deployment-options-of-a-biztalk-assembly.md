---
title: Cómo modificar las opciones de implementación de un ensamblado de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, deploying
- managing [assemblies], modifying
- deploying, assemblies
- managing [assemblies], deploying
- assemblies, deploying
ms.assetid: d25e2f71-08bd-4786-ab6c-35ae4e88b8cc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58365383b1981ae40e87ee23891929bf05c8530e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007757"
---
# <a name="how-to-modify-the-deployment-options-of-a-biztalk-assembly"></a><span data-ttu-id="83f85-102">Cómo modificar las opciones de implementación de un ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="83f85-102">How to Modify the Deployment Options of a BizTalk Assembly</span></span>
<span data-ttu-id="83f85-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para modificar las opciones de implementación de un ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="83f85-103">This topic describes how to use the BizTalk Server Administration console to modify the deployment options of a BizTalk assembly.</span></span>  
  
 <span data-ttu-id="83f85-104">Puede especificar las siguientes opciones de implementación:</span><span class="sxs-lookup"><span data-stu-id="83f85-104">You can specify the following deployment options:</span></span>  
  
-   <span data-ttu-id="83f85-105">**Agregar a la caché global de ensamblados de agregar recursos (gacutil).**</span><span class="sxs-lookup"><span data-stu-id="83f85-105">**Add to the global assembly cache on add resource (gacutil).**</span></span> <span data-ttu-id="83f85-106">al activar esta opción, el ensamblado se agrega a la caché de ensamblados global (GAC) en el equipo local cuando el ensamblado se agrega a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="83f85-106">When you select this option, the assembly is added to the global assembly cache (GAC) on the local computer when the assembly is added to the application.</span></span> <span data-ttu-id="83f85-107">Además, si actualiza posteriormente el ensamblado (haga clic en él y haga clic en **actualizar**), el ensamblado se agrega a la GAC.</span><span class="sxs-lookup"><span data-stu-id="83f85-107">In addition, if you later refresh the assembly (right-click it and click **Refresh**), the assembly is added to the GAC.</span></span> <span data-ttu-id="83f85-108">Al desactivar la casilla de verificación de esta opción, el ensamblado no se quita de la GAC si actualmente existe en dicho lugar.</span><span class="sxs-lookup"><span data-stu-id="83f85-108">Clearing the check box for this option does not remove the assembly from the GAC, if it currently exists there.</span></span>  
  
-   <span data-ttu-id="83f85-109">**Agregar a la caché de ensamblados global en la importación de archivo MSI (gacutil).**</span><span class="sxs-lookup"><span data-stu-id="83f85-109">**Add to the global assembly cache on MSI file import (gacutil).**</span></span> <span data-ttu-id="83f85-110">instala el ensamblado en la GAC del equipo local cuando se importa el archivo .msi de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="83f85-110">Install the assembly to the GAC on the local computer when the application .msi file is imported.</span></span>  
  
-   <span data-ttu-id="83f85-111">**Agregar a la caché de ensamblados global en la instalación de archivos MSI (gacutil).**</span><span class="sxs-lookup"><span data-stu-id="83f85-111">**Add to the global assembly cache on MSI file install (gacutil).**</span></span> <span data-ttu-id="83f85-112">instala el ensamblado en la GAC del equipo local cuando se instala la aplicación desde el archivo .msi.</span><span class="sxs-lookup"><span data-stu-id="83f85-112">Install the assembly to the GAC on the local computer when the application is installed from the .msi file.</span></span>  
  
-   <span data-ttu-id="83f85-113">**Ubicación de destino:** ruta de acceso a la que se copiará el archivo de ensamblado cuando se instala la aplicación.</span><span class="sxs-lookup"><span data-stu-id="83f85-113">**Destination location:** Path to which the assembly file will be copied when the application is installed.</span></span> <span data-ttu-id="83f85-114">Si no se proporciona una ruta, el archivo de ensamblado no se copiará en el sistema de archivos local durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="83f85-114">If a path is not provided, the assembly file is not copied to the local file system on installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="83f85-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="83f85-115">Prerequisites</span></span>  
 <span data-ttu-id="83f85-116">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="83f85-116">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="83f85-117">Además, si selecciona una opción que agrega inmediatamente el ensamblado a la GAC, la cuenta debe pertenecer también al grupo de administradores local.</span><span class="sxs-lookup"><span data-stu-id="83f85-117">In addition, if you select an option that immediately adds the assembly to the GAC, your account must also be a member of the local Administrator's group.</span></span> <span data-ttu-id="83f85-118">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="83f85-118">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-options-of-a-biztalk-assembly"></a><span data-ttu-id="83f85-119">Para modificar las opciones de implementación de un ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="83f85-119">To modify the deployment options of a BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="83f85-120">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="83f85-120">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="83f85-121">En el árbol de consola, expanda Administración de BizTalk Server, expanda el grupo de BizTalk que contiene el ensamblado de BizTalk para el que se va a modificar opciones de implementación y, a continuación, expanda la aplicación que contiene el ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="83f85-121">In the console tree, expand BizTalk Server Administration, expand the BizTalk group containing the BizTalk assembly for which to modify deployment options, and then expand the application containing the BizTalk assembly.</span></span>  
  
3.  <span data-ttu-id="83f85-122">Haga clic en el **recursos** carpeta, haga clic en el ensamblado de BizTalk y, a continuación, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="83f85-122">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="83f85-123">En **opciones**, active las casillas de las opciones de implementación que desee.</span><span class="sxs-lookup"><span data-stu-id="83f85-123">In **Options**, select the check boxes of the deployment options that you want.</span></span>  
  
5.  <span data-ttu-id="83f85-124">Si es necesario, en **ubicación de destino** modificar la ruta de acceso donde se copiará cuando la aplicación se instala el ensamblado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="83f85-124">If necessary, in **Destination location** edit the path where the assembly will be copied when the application is installed, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83f85-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="83f85-125">See Also</span></span>  
 [<span data-ttu-id="83f85-126">Administración de ensamblados de BizTalk</span><span class="sxs-lookup"><span data-stu-id="83f85-126">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)