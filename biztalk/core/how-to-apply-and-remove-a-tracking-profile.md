---
title: Cómo aplicar y quitar un perfil de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, testing
- tracking profiles, deleting
- testing, tracking profiles
ms.assetid: 77cef14b-c390-4da7-a383-b3abe414a168
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 955b2ccddb215b79fd7cdc7d51ed6f5160c297fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248300"
---
# <a name="how-to-apply-and-remove-a-tracking-profile"></a><span data-ttu-id="44566-102">Cómo aplicar y quitar un perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="44566-102">How to Apply and Remove a Tracking Profile</span></span>
<span data-ttu-id="44566-103">Tras crear o modificar el perfil de seguimiento, el siguiente paso es aplicarlo a una base de datos de prueba y comprobar el resultado en la prueba de integración.</span><span class="sxs-lookup"><span data-stu-id="44566-103">Once you have created or modified the tracking profile, the next step is to apply it to a test database and verify the result through integration testing.</span></span> <span data-ttu-id="44566-104">Puede aplicar el perfil de seguimiento desde el propio Editor de perfiles de seguimiento (TPE) o mediante la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="44566-104">You can apply the tracking profile from within Tracking Profile Editor (TPE) itself or by using the command line.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="44566-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="44566-105">Prerequisites</span></span>  
 <span data-ttu-id="44566-106">Un perfil de seguimiento que se ha creado anteriormente y que guardó en su disco duro.</span><span class="sxs-lookup"><span data-stu-id="44566-106">A previously created tracking profile that you saved to your hard drive.</span></span>  
  
### <a name="to-apply-the-tracking-profile-from-within-the-tpe"></a><span data-ttu-id="44566-107">Para aplicar el perfil de seguimiento desde el TPE</span><span class="sxs-lookup"><span data-stu-id="44566-107">To apply the tracking profile from within the TPE</span></span>  
  
1.  <span data-ttu-id="44566-108">Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Editor de perfiles de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="44566-108">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44566-109">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="44566-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="44566-110">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="44566-110">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="44566-111">En el **archivo** menú, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="44566-111">On the **File** menu, click **Open**.</span></span> <span data-ttu-id="44566-112">Desplácese al archivo .btt correspondiente en el disco duro.</span><span class="sxs-lookup"><span data-stu-id="44566-112">Navigate to the correct .btt file on your hard drive.</span></span> <span data-ttu-id="44566-113">Haga clic en **abiertos** para cargar el recurso.</span><span class="sxs-lookup"><span data-stu-id="44566-113">Click **Open** to load it.</span></span>  
  
3.  <span data-ttu-id="44566-114">En el **herramientas** menú, haga clic en **aplicar perfil de seguimiento** para aplicar el archivo .btt a una base de datos de administración que ha establecido desde el **establecer base de datos de administración** elemento de menú en el **Herramientas** menú.</span><span class="sxs-lookup"><span data-stu-id="44566-114">On the **Tools** menu, click **Apply Tracking Profile** to apply the .btt file to a management database that you have set from the **Set Management Database** menu item on the **Tools** menu.</span></span> <span data-ttu-id="44566-115">Compruebe el resultado a través de la prueba de integración.</span><span class="sxs-lookup"><span data-stu-id="44566-115">Verify the result through integration testing.</span></span>  
  
4.  <span data-ttu-id="44566-116">Envíe una notificación a la persona responsable de la implementación en su organización que avise de que el perfil de seguimiento funciona correctamente y que está listo para la implementación.</span><span class="sxs-lookup"><span data-stu-id="44566-116">Notify the person in your organization responsible for deployment that the tracking profile tests correctly and is ready for deployment.</span></span>  
  
### <a name="to-apply-the-tracking-profile-from-the-command-line"></a><span data-ttu-id="44566-117">Para aplicar el perfil de seguimiento desde la utilidad de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="44566-117">To apply the tracking profile from the command line</span></span>  
  
-   <span data-ttu-id="44566-118">En el símbolo del sistema, ejecute la herramienta bttdeploy.exe que se encuentra en la carpeta \Tracking, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="44566-118">From the command prompt, run the bttdeploy.exe tool located in the \Tracking folder as follows:</span></span>  
  
    ```  
    bttdeploy.exe <profile name>.btt  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="44566-119">Debe tener privilegios de administrador de BizTalk para utilizar esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="44566-119">You must have BizTalk Administrator privileges to use this tool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44566-120">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="44566-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="44566-121">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="44566-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="44566-122">Durante la implementación, bttdeploy comprueba la versión de ensamblado de los perfiles de seguimiento y la hace coincidir con la versión del ensamblado implementado.</span><span class="sxs-lookup"><span data-stu-id="44566-122">During the deployment, bttdeploy verifies the assembly version contained in the tracking profiles and matches it to the version of the deployed assembly.</span></span> <span data-ttu-id="44566-123">Se producirá un error en Bttdeploy si el ensamblado no está implementado actualmente.</span><span class="sxs-lookup"><span data-stu-id="44566-123">Bttdeploy will fail if the assembly is not currently deployed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="44566-124">Cuando aplica un perfil de seguimiento desde la línea de comandos, bttdeploy aplica el perfil a la base de datos de administración de BizTalk que indicó cuando ejecutó el asistente para configuración.</span><span class="sxs-lookup"><span data-stu-id="44566-124">When applying a tracking profile from the command line, bttdeploy applies the profile to the BizTalk Management database that you indicated when you ran the configuration wizard.</span></span> <span data-ttu-id="44566-125">Si especifica una configuración de base de datos diferente en la opción del Editor de perfiles de seguimiento "Establecer base de datos de administración", se utiliza esa configuración.</span><span class="sxs-lookup"><span data-stu-id="44566-125">If you specify a different database setting in the Tracking Profile Editor Option "Set Management Database," then that setting is used.</span></span> <span data-ttu-id="44566-126">Si especifica un servidor de administración y una base de datos como parte de la opción de línea de comandos como bttdeploy, la opción de línea de comandos reemplaza todo lo demás.</span><span class="sxs-lookup"><span data-stu-id="44566-126">If you specify a management server and database as part of the command line option to bttdeploy, then the command line option overrides everything else.</span></span> <span data-ttu-id="44566-127">Para obtener más información sobre el uso de bttdeploy, vea [utilidad de implementación de perfiles de seguimiento](../core/tracking-profile-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="44566-127">For more information about using bttdeploy, see [Tracking Profile Deployment Utility](../core/tracking-profile-deployment-utility.md).</span></span>  
  
### <a name="to-remove-a-tracking-profile"></a><span data-ttu-id="44566-128">Para quitar un perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="44566-128">To remove a tracking profile</span></span>  
  
1.  <span data-ttu-id="44566-129">Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Editor de perfiles de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="44566-129">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44566-130">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="44566-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="44566-131">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="44566-131">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="44566-132">En el **archivo** menú, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="44566-132">On the **File** menu, click **Open**.</span></span> <span data-ttu-id="44566-133">Desplácese al archivo .btt correspondiente en el disco duro.</span><span class="sxs-lookup"><span data-stu-id="44566-133">Navigate to the correct .btt file on your hard drive.</span></span> <span data-ttu-id="44566-134">Haga clic en **abiertos** para cargar el recurso.</span><span class="sxs-lookup"><span data-stu-id="44566-134">Click **Open** to load it.</span></span>  
  
3.  <span data-ttu-id="44566-135">En el **herramientas** menú, haga clic en **quitar perfil de seguimiento** para quitar el perfil de seguimiento basado en el archivo .btt de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="44566-135">On the **Tools** menu, click **Remove Tracking Profile** to remove the tracking profile based on the .btt file from the BizTalk Management database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44566-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="44566-136">See Also</span></span>  
 [<span data-ttu-id="44566-137">Creación de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="44566-137">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)