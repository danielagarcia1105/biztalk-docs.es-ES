---
title: Cómo modificar la configuración de Host | Documentos de Microsoft
description: Cambiar la configuración de host de BizTalk en administración de BizTalk Server para mejorar el rendimiento y limitación
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0759b3a0-560e-4a11-92e6-9de0e15f463b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 998c668bf787c9db260597c3a350e0e571492212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254556"
---
# <a name="update-biztalk-host-settings"></a><span data-ttu-id="daac9-103">Actualizar la configuración de host de BizTalk</span><span class="sxs-lookup"><span data-stu-id="daac9-103">Update BizTalk host settings</span></span>

## <a name="overview"></a><span data-ttu-id="daac9-104">Información general</span><span class="sxs-lookup"><span data-stu-id="daac9-104">Overview</span></span>
<span data-ttu-id="daac9-105">Mediante el uso del Panel de configuración, puede modificar la información de configuración de un host dado en todo un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="daac9-105">Using the Settings Dashboard, you can modify the configuration information of a given host, across a BizTalk group.</span></span> <span data-ttu-id="daac9-106">En este tema se proporciona el procedimiento paso a paso para modificar la configuración de rendimiento de nivel de host en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daac9-106">This topic provides the step-by-step procedure to modify the host-level performance settings in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="daac9-107">También puede modificar la configuración de instancia de host y de grupo.</span><span class="sxs-lookup"><span data-stu-id="daac9-107">You can also modify the group and host instance settings.</span></span> <span data-ttu-id="daac9-108">Para obtener información sobre cómo modificar la configuración, consulte [uso del panel de configuración para la optimización de rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span><span class="sxs-lookup"><span data-stu-id="daac9-108">For information about how to modify the settings, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
 <span data-ttu-id="daac9-109">La configuración actual de BizTalk Server puede exportarse a un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="daac9-109">The current BizTalk Server settings can be exported to an XML file.</span></span> <span data-ttu-id="daac9-110">Posteriormente, puede importarse dicha configuración en el panel de configuraciones, en lugar de configurar nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="daac9-110">Later, you can import those settings to the Settings Dashboard instead of setting up new values.</span></span> <span data-ttu-id="daac9-111">Para obtener información acerca de cómo importar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración, consulte [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md) y [importación o exportación BTSTask de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-btstask.md).</span><span class="sxs-lookup"><span data-stu-id="daac9-111">For information on importing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) and [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="daac9-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="daac9-112">Prerequisites</span></span>  
 <span data-ttu-id="daac9-113">Para realizar esta operación, debe iniciar sesión como miembro del grupo Administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="daac9-113">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="update-the-host-level-settings"></a><span data-ttu-id="daac9-114">Actualizar la configuración de nivel de host</span><span class="sxs-lookup"><span data-stu-id="daac9-114">Update the host-level settings</span></span>  
  
1.  <span data-ttu-id="daac9-115">En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="daac9-115">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2.  <span data-ttu-id="daac9-116">En el **panel de configuración de BizTalk** cuadro de diálogo, en la **Hosts** página, realice una o varias de las acciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="daac9-116">In the **BizTalk Settings Dashboard** dialog box, on the **Hosts** page, do one or more of the following.</span></span>  
  
    -   <span data-ttu-id="daac9-117">Modificar la configuración de rendimiento general del host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="daac9-117">Modify the general performance settings of the BizTalk host.</span></span> <span data-ttu-id="daac9-118">Vea [cómo modificar la configuración General](../core/how-to-modify-general-settings.md).</span><span class="sxs-lookup"><span data-stu-id="daac9-118">See [How to Modify General Settings](../core/how-to-modify-general-settings.md).</span></span>  
  
    -   <span data-ttu-id="daac9-119">Modificar la configuración de limitación basada en recursos del host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="daac9-119">Modify the resource-based throttling settings of the BizTalk host.</span></span> <span data-ttu-id="daac9-120">Vea [modificar recursos basada en valores de límite](../core/how-to-modify-resource-based-throttling-settings.md).</span><span class="sxs-lookup"><span data-stu-id="daac9-120">See [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span>  
  
    -   <span data-ttu-id="daac9-121">Modifique la configuración de limitación según la velocidad del host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="daac9-121">Modify the rate-based throttling settings of the BizTalk host.</span></span> <span data-ttu-id="daac9-122">Vea [Modificar tasa basada en valores de límite](../core/how-to-modify-rate-based-throttling-settings.md).</span><span class="sxs-lookup"><span data-stu-id="daac9-122">See [How to Modify Rate Based Throttling Settings](../core/how-to-modify-rate-based-throttling-settings.md).</span></span>  
  
    -   <span data-ttu-id="daac9-123">Modificar la configuración de limitación de orquestación del host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="daac9-123">Modify the orchestration throttling settings of the BizTalk host.</span></span> <span data-ttu-id="daac9-124">Vea [cómo modificar la configuración de limitación de orquestación](../core/how-to-modify-orchestration-throttling-settings.md).</span><span class="sxs-lookup"><span data-stu-id="daac9-124">See [How to Modify Orchestration Throttling Settings](../core/how-to-modify-orchestration-throttling-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daac9-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="daac9-125">See Also</span></span>  
 [<span data-ttu-id="daac9-126">Usar el panel de configuración para el servidor BizTalk Server ajuste del rendimiento</span><span class="sxs-lookup"><span data-stu-id="daac9-126">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)