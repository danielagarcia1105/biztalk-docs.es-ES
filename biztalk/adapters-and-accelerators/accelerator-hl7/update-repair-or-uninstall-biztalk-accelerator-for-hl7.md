---
title: Actualizar, reparar o desinstalar el Acelerador de BizTalk para HL7 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2fc84d2-1262-4a6e-ae9c-488a00ab4099
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb49cdff18e880c91034aaf7d2ab81500c40dbab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="update-repair-or-uninstall-biztalk-accelerator-for-hl7"></a><span data-ttu-id="2429e-102">Actualizar, reparar o desinstalar el Acelerador de BizTalk para HL7</span><span class="sxs-lookup"><span data-stu-id="2429e-102">Update, repair, or uninstall BizTalk Accelerator for HL7</span></span>

<span data-ttu-id="2429e-103">Cambiar, reparar o desinstalar el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2429e-103">Change, repair or uninstall the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2429e-104">No olvide desinstalar [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] antes de desinstalar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2429e-104">Be sure to uninstall [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] before uninstalling [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]<span data-ttu-id="2429e-105">no se puede desinstalar si [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ya no está instalado.</span><span class="sxs-lookup"><span data-stu-id="2429e-105"> cannot be uninstalled if [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is no longer installed.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="2429e-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2429e-106">Prerequisites</span></span>
* <span data-ttu-id="2429e-107">Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="2429e-107">Sign in using an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

* <span data-ttu-id="2429e-108">Esta cuenta de usuario también debe ser miembro del grupo Administradores en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] que almacena el Acelerador de BizTalk para HL7 datos.</span><span class="sxs-lookup"><span data-stu-id="2429e-108">This user account must also be a member of the Administrators group on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] that stores the BizTalk Accelerator for HL7 data.</span></span>  
    
## <a name="update-an-existing-installation"></a><span data-ttu-id="2429e-109">Actualizar una instalación existente</span><span class="sxs-lookup"><span data-stu-id="2429e-109">Update an existing installation</span></span>

> [!NOTE]
>  <span data-ttu-id="2429e-110">Al modificar la instalación de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)], el Tutorial to-End no se ejecuta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2429e-110">When you modify your installation of [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)], the End-to-End Tutorial does not automatically run.</span></span> 
> 
> <span data-ttu-id="2429e-111">Para ejecutar el tutorial y verificar que la instalación modificada se ha ejecutado correctamente, ejecute el tutorial manualmente desde el  ***\<unidad >*** **\Program BizTalk \<versión > Acelerador para HL7\SDK\End-to-End Tutorial** carpeta.</span><span class="sxs-lookup"><span data-stu-id="2429e-111">To run the tutorial and verify that the modified installation executed correctly, run the tutorial manually from the ***\<drive>*** **\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\End-to-End Tutorial** folder.</span></span>
  
1. <span data-ttu-id="2429e-112">Ejecute el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe** como administrador</span><span class="sxs-lookup"><span data-stu-id="2429e-112">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe** as an administrator</span></span> 
  
2.  <span data-ttu-id="2429e-113">En la página de bienvenida, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2429e-113">On the welcome page, select **Next**.</span></span>  
  
3.  <span data-ttu-id="2429e-114">En **mantenimiento del programa**, seleccione **modificar**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2429e-114">In **Program Maintenance**, select **Modify**, and then select **Next**.</span></span>  
  
4.  <span data-ttu-id="2429e-115">En **personalizada**, seleccione las características que desea instalar, desactive las características no desee y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2429e-115">In **Custom Setup**, select the features that you want to install, clear the features you don't want, and then select **Next**.</span></span>  
  
5.  <span data-ttu-id="2429e-116">En el resumen, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2429e-116">In the summary, select **Next**.</span></span>  
  
6.  <span data-ttu-id="2429e-117">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="2429e-117">Select **Install**.</span></span>  
  
7. <span data-ttu-id="2429e-118">Cuando haya finalizado, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2429e-118">When complete, select **Finish**.</span></span>  

## <a name="repair-an-existing-installation"></a><span data-ttu-id="2429e-119">Reparar una instalación existente</span><span class="sxs-lookup"><span data-stu-id="2429e-119">Repair an existing installation</span></span>
<span data-ttu-id="2429e-120">El [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] Asistente para repara una instalación arreglando archivos ausentes o dañados, accesos directos o entradas del registro.</span><span class="sxs-lookup"><span data-stu-id="2429e-120">The [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] Wizard repairs an installation by fixing missing or corrupt files, shortcuts, or registry entries.</span></span>  
  
1. <span data-ttu-id="2429e-121">Ejecute el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe** como administrador.</span><span class="sxs-lookup"><span data-stu-id="2429e-121">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe** as administrator.</span></span>  
  
2.  <span data-ttu-id="2429e-122">En la página de bienvenida, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2429e-122">On the welcome page, select **Next**.</span></span>  
  
3.  <span data-ttu-id="2429e-123">En **mantenimiento del programa**, seleccione **reparación**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2429e-123">In **Program Maintenance**, select **Repair**, and then select **Next**.</span></span>  
  
4.  <span data-ttu-id="2429e-124">En **cuenta de servicio de registro**, vuelva a escribir la cuenta de usuario y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2429e-124">In **Logging Service Account**, re-enter the user account, and then select **OK**.</span></span>  
  
4.  <span data-ttu-id="2429e-125">Si se le pide **se ha concedido el nombre de cuenta de inicio de sesión como servicio derecho**, a continuación, seleccione **Aceptar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="2429e-125">If prompted **The account name has been granted logon as a service right**, then select **OK** to continue.</span></span>  
  
5.  <span data-ttu-id="2429e-126">Cuando esté listo para reparar, seleccione **instalar**.</span><span class="sxs-lookup"><span data-stu-id="2429e-126">When ready to repair, select **Install**.</span></span>  
  
6. <span data-ttu-id="2429e-127">Cuando haya completado, seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2429e-127">When completed, select **Finish**.</span></span> 

  
## <a name="uninstall-btahl7"></a><span data-ttu-id="2429e-128">Desinstalar BTAHL7</span><span class="sxs-lookup"><span data-stu-id="2429e-128">Uninstall BTAHL7</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="2429e-129">Si no hay una ubicación de recepción o puerto de envío mediante el tipo de transporte MLLP, el programa de instalación de BTAHL7 no quita el adaptador MLLP durante la desinstalación de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="2429e-129">If there is a receive location or send port using the MLLP transport type, the BTAHL7 setup does not remove the MLLP adapter during the uninstall of BTAHL7.</span></span> <span data-ttu-id="2429e-130">Antes de desinstalar, quite todas las ubicaciones de recepción o envían puertos mediante el transporte MLLP.</span><span class="sxs-lookup"><span data-stu-id="2429e-130">Before you uninstall, remove all receive locations or send ports using the MLLP transport.</span></span> <span data-ttu-id="2429e-131">O bien, cambiar el tipo de transporte de MLLP a otro tipo.</span><span class="sxs-lookup"><span data-stu-id="2429e-131">Or, change the transport type from MLLP to another type.</span></span> <span data-ttu-id="2429e-132">A continuación, la desinstalación quitará el adaptador MLLP.</span><span class="sxs-lookup"><span data-stu-id="2429e-132">Then, the uninstall will remove the MLLP adapter.</span></span>  
      
1.  <span data-ttu-id="2429e-133">Abra **Programas y características**.</span><span class="sxs-lookup"><span data-stu-id="2429e-133">Open **Programs and Features**.</span></span>  
  
2.  <span data-ttu-id="2429e-134">Seleccione [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]y, a continuación, seleccione **desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="2429e-134">Select [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], and then select **Uninstall**.</span></span>  
  
4.  <span data-ttu-id="2429e-135">Seleccione **Sí** si se le solicita que confirme.</span><span class="sxs-lookup"><span data-stu-id="2429e-135">Select **Yes** if asked to confirm.</span></span> 
  
5.  <span data-ttu-id="2429e-136">Cuando haya completado, seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2429e-136">When completed, select **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2429e-137">BTAHL7 no desinstala automáticamente [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artefactos y ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2429e-137">BTAHL7 does not automatically uninstall [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artifacts and assemblies.</span></span>  
  

  
## <a name="troubleshooting-installation-issues"></a><span data-ttu-id="2429e-138">Solución de problemas de instalación</span><span class="sxs-lookup"><span data-stu-id="2429e-138">Troubleshooting Installation Issues</span></span>  
 <span data-ttu-id="2429e-139">Si el servidor es no se puede validar si el usuario es un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] administrador, al desinstalar BTAHL7 devuelve el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="2429e-139">If the server is unable to validate whether the user is a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrator, uninstalling BTAHL7 returns the following error:</span></span> 
 
 `Fatal error during uninstallation`  
  
<span data-ttu-id="2429e-140">Para continuar con la desinstalación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2429e-140">To continue with uninstallation, do the following:</span></span>  
  
1.  <span data-ttu-id="2429e-141">Inicie sesión como administrador local el servidor.</span><span class="sxs-lookup"><span data-stu-id="2429e-141">Sign in to the server as a local administrator.</span></span>  
  
2.  <span data-ttu-id="2429e-142">Desinstale [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2429e-142">Uninstall [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="2429e-143">Desinstale [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2429e-143">Uninstall [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2429e-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="2429e-144">See Also</span></span>  
[<span data-ttu-id="2429e-145">Instalar o actualizar Acelerador de Microsoft BizTalk para HL7</span><span class="sxs-lookup"><span data-stu-id="2429e-145">Install or upgrade Microsoft BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)