---
title: Modificar un PIP existente en Rnpip | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RNPIPs
- modifying, PIPs
- PIPs, modifying
- assemblies, RNPIPs
ms.assetid: f2ed25c4-1979-4691-9315-e7568e7cca8b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e3867c50e73c1747ed6e800f624b674e2ee737c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004869"
---
# <a name="modifying-an-existing-pip-in-rnpips"></a><span data-ttu-id="3f6a2-102">Modificar un PIP existente en Rnpip</span><span class="sxs-lookup"><span data-stu-id="3f6a2-102">Modifying an Existing PIP in RNPIPs</span></span>
<span data-ttu-id="3f6a2-103">Este tema describe cómo cambiar y volver a implementar uno de los esquemas de proceso de interfaz de socio (PIP) que se instalan con Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-103">This topic describes how to change and re-deploy one of the Partner Interface Process (PIP) schemas installed by Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] setup.</span></span> <span data-ttu-id="3f6a2-104">El esquema se implementa como parte del ensamblado de los RNPIP.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-104">You deploy the schema as part of the RNPIPs assembly.</span></span>  
  
### <a name="to-modify-an-existing-pip-in-rnpips"></a><span data-ttu-id="3f6a2-105">Para modificar un PIP existente en los RNPIP</span><span class="sxs-lookup"><span data-stu-id="3f6a2-105">To modify an existing PIP in RNPIPs</span></span>  
  
1. <span data-ttu-id="3f6a2-106">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-106">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="3f6a2-107">Busque el \< *unidad*\>\Program Files\Microsoft BizTalk \<versión\> Acelerador de la carpeta RosettaNet\SDK\Utilities\Schema Generator.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-107">Locate the \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Utilities\Schema Generator folder.</span></span>  
  
3. <span data-ttu-id="3f6a2-108">En el símbolo del sistema, escriba **CScript InstallDTD.vbs**y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-108">At the command prompt, type **CScript InstallDTD.vbs**, and then press ENTER.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3f6a2-109">Solo debe realizar los pasos 1 y 2 una vez después de instalar a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-109">You only have to do steps 1 and 2 one time after you install BizTalk Server.</span></span>  
  
4. <span data-ttu-id="3f6a2-110">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-110">Start **Microsoft Visual Studio 2012**.</span></span>  
  
5. <span data-ttu-id="3f6a2-111">En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-111">In the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
6. <span data-ttu-id="3f6a2-112">En el **Abrir proyecto** cuadro de diálogo, desplácese a \< *unidad*\>\Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\ Los esquemas y, a continuación, seleccione **RNPIPs.btproj**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-112">In the **Open Project** dialog box, move to \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas, and then select **RNPIPs.btproj**.</span></span>  
  
7. <span data-ttu-id="3f6a2-113">En el menú **Ver** , haga clic en **Explorador de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-113">In the **View** menu, click **BizTalk Explorer**.</span></span> <span data-ttu-id="3f6a2-114">Expanda **Ensamblados**y, a continuación, haga clic con el botón derecho en **Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-114">Expand **Assemblies**, and then right-click **Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)**.</span></span> <span data-ttu-id="3f6a2-115">Haga clic en **Anular la implementación**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-115">Click **Undeploy**.</span></span>  
  
8. <span data-ttu-id="3f6a2-116">Inicie un **símbolo del sistema de Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-116">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
9. <span data-ttu-id="3f6a2-117">Vaya a la ubicación especificada en el paso 6, en el símbolo del sistema escriba **sn -k RNPIPs.snk**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-117">Move to the location entered in step 6, at the command prompt, type **sn -k RNPIPs.snk**, and then press **Enter**.</span></span>  
  
10. <span data-ttu-id="3f6a2-118">En el Explorador de soluciones, haga clic con el botón derecho en **RNPIP**, haga clic en **Propiedades**, en **Propiedades comunes**y en **Ensamblado.**</span><span class="sxs-lookup"><span data-stu-id="3f6a2-118">In Solution Explorer, right-click **RNPIPs**, click **Properties**, click **Common Properties**, and then click **Assembly.**</span></span>  
  
11. <span data-ttu-id="3f6a2-119">En el panel derecho, desplácese hacia abajo hasta **Nombre seguro**, en la sección **Archivo de clave de ensamblado** haga clic en el botón de puntos suspensivos (...), vaya a la ubicación especificada en el paso 6, en el símbolo del sistema escriba **RNPIPs.snk**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-119">In the right pane, scroll down to **Strong Name**, in the **Assembly Key File** section, click the ellipsis button (...) button, go to the location entered in step 6, at the command prompt, type **RNPIPs.snk**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="3f6a2-120">En el cuadro de diálogo **Páginas de propiedades** , haga clic en **Propiedades de configuración**, en **Implementación**, en **Volver a implementar**, seleccione `True`y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-120">In the **Property Pages** dialog box, click **Configuration Properties**, click **Deployment**, click **Redeploy**, select `True`, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="3f6a2-121">Edite los esquemas existentes en los RNPIP, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-121">Edit any of the existing schemas in RNPIPs, as required.</span></span>  
  
14. <span data-ttu-id="3f6a2-122">Haga clic en **Archivo**y, a continuación, en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-122">Click **File**, and then click **Save**.</span></span>  
  
15. <span data-ttu-id="3f6a2-123">Haga clic con el botón derecho en el nombre del proyecto y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-123">Right-click the project name, and then click **Build**.</span></span>  
  
16. <span data-ttu-id="3f6a2-124">Haga clic con el botón derecho en el nombre del proyecto y haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-124">Right-click the project name, and then click **Deploy**.</span></span>  
  
17. <span data-ttu-id="3f6a2-125">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-125">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
18. <span data-ttu-id="3f6a2-126">En la consola de administración de BizTalk, expanda **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)** y, a continuación, expanda **Hosts**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-126">In BizTalk Administration Console, expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, and then expand **Hosts**.</span></span>  
  
19. <span data-ttu-id="3f6a2-127">En el panel derecho, haga clic con el botón derecho en el nombre del host y, a continuación, haga clic en **Detener**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-127">In the right pane, right-click the name of the host, and then click **Stop**.</span></span> <span data-ttu-id="3f6a2-128">Una vez detenido el servicio, haga clic con el botón derecho en el nombre del host y, a continuación, haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="3f6a2-128">After the service has stopped, right-click the name of the host, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6a2-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f6a2-129">See Also</span></span>  
 <span data-ttu-id="3f6a2-130">[Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span><span class="sxs-lookup"><span data-stu-id="3f6a2-130">[Programming Guide](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span></span>  
 [<span data-ttu-id="3f6a2-131">Incorporación de un nuevo proceso de interfaz de socio comercial</span><span class="sxs-lookup"><span data-stu-id="3f6a2-131">Incorporating a New Partner Interface Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)