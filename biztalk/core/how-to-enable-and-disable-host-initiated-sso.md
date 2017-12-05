---
title: "Cómo habilitar y deshabilitar el Host para SSO iniciado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host initiated SSO, disabling
- disabling, host initiated SSO
- enabling, host initiated SSO
- host initiated SSO, enabling
ms.assetid: a11d314a-6ff9-4d0a-89c3-c412541c2cec
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1e5783893bbc9091d0a5f1fb3f116b17413bc5d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-and-disable-host-initiated-sso"></a><span data-ttu-id="e5431-102">Cómo habilitar y deshabilitar el Host para SSO iniciado</span><span class="sxs-lookup"><span data-stu-id="e5431-102">How to Enable and Disable Host Initiated SSO</span></span>
<span data-ttu-id="e5431-103">De forma predeterminada, el inicio de sesión único iniciado por host no se encuentra habilitado en el sistema de inicio de sesión único, y debe habilitarlo el administrador de SSO.</span><span class="sxs-lookup"><span data-stu-id="e5431-103">By default, host initiated Single Sign-On is not enabled in the Single Sign-On system, and must be enabled by the SSO Administrator.</span></span>  
  
### <a name="to-enable-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="e5431-104">Para habilitar el SSO iniciado por host con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="e5431-104">To enable host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="e5431-105">En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="e5431-105">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="e5431-106">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="e5431-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="e5431-107">Haga clic en **System**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e5431-107">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="e5431-108">Haga clic en el **opciones** ficha.</span><span class="sxs-lookup"><span data-stu-id="e5431-108">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="e5431-109">Seleccione el **SSO iniciado por host Enable** cuadro y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e5431-109">Select the **Enable host initiated SSO** box, and click **OK**.</span></span>  
  
### <a name="to-enable-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="e5431-110">Para habilitar el SSO iniciado por host con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="e5431-110">To enable host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="e5431-111">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e5431-111">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="e5431-112">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e5431-112">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="e5431-113">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="e5431-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="e5431-114">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="e5431-114">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="e5431-115">Tipo de **ssomanage-habilitar hisso**.</span><span class="sxs-lookup"><span data-stu-id="e5431-115">Type **ssomanage -enable hisso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e5431-116">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e5431-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
 <span data-ttu-id="e5431-117">El SSO se deshabilita en todo el sistema de SSO y se desactivan todas las operaciones relacionadas con el SSO iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="e5431-117">Disabling SSO applies to the entire SSO system, and all operations related to host initiated SSO are turned off.</span></span>  
  
#### <a name="to-disable-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="e5431-118">Para deshabilitar el SSO iniciado por host con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="e5431-118">To disable host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="e5431-119">En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="e5431-119">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="e5431-120">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="e5431-120">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="e5431-121">Haga clic en **System**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e5431-121">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="e5431-122">Haga clic en el **opciones** ficha.</span><span class="sxs-lookup"><span data-stu-id="e5431-122">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="e5431-123">Desactive el **SSO iniciado por host Enable** cuadro y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e5431-123">Clear the **Enable host initiated SSO** box, and click **OK**.</span></span>  
  
#### <a name="to-disable-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="e5431-124">Para deshabilitar el SSO iniciado por host con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="e5431-124">To disable host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="e5431-125">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e5431-125">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="e5431-126">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e5431-126">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="e5431-127">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="e5431-127">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="e5431-128">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="e5431-128">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="e5431-129">Tipo de **ssomanage-deshabilitar hisso** según corresponda.</span><span class="sxs-lookup"><span data-stu-id="e5431-129">Type **ssomanage -disable hisso** as appropriate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e5431-130">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e5431-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5431-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5431-131">See Also</span></span>  
 [<span data-ttu-id="e5431-132">SSO iniciado por host</span><span class="sxs-lookup"><span data-stu-id="e5431-132">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)