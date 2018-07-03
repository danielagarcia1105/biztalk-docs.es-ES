---
title: Actualizar la configuración de la instancia de Host | Microsoft Docs
description: Cambiar la configuración de la instancia de host en el Administrador de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2338255b-cc13-4f6a-86c3-9ecc666c43e5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6102e4cce6a850c7e2ed5656a8fd5aacfd5d5a09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011717"
---
# <a name="update-biztalk-host-instance-settings"></a><span data-ttu-id="41ca2-103">Actualizar la configuración de instancia de host de BizTalk</span><span class="sxs-lookup"><span data-stu-id="41ca2-103">Update BizTalk host instance settings</span></span>

## <a name="overview"></a><span data-ttu-id="41ca2-104">Información general</span><span class="sxs-lookup"><span data-stu-id="41ca2-104">Overview</span></span>
<span data-ttu-id="41ca2-105">Mediante el uso del [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], puede modificar la información de configuración de un host dado en todo un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="41ca2-105">Using the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], you can modify the configuration information of a given host instance, across a BizTalk group.</span></span> <span data-ttu-id="41ca2-106">En este tema se proporciona el procedimiento paso a paso para modificar la configuración de rendimiento de nivel de instancia en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41ca2-106">This topic provides the step-by-step procedure to modify the host instance level performance settings in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="41ca2-107">A menudo tienen la configuración de BizTalk (desde un entorno de origen) guardada como archivo XML.</span><span class="sxs-lookup"><span data-stu-id="41ca2-107">Often you have the BizTalk settings (from a source environment) saved as an XML file.</span></span> <span data-ttu-id="41ca2-108">El archivo XML contiene información que le permite replicar la configuración en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="41ca2-108">The XML file contains information that allows you to replicate the settings on the target machine.</span></span> <span data-ttu-id="41ca2-109">Puede importar dicha configuración al Panel de configuración, en lugar de configurar nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="41ca2-109">You can import those settings to Settings Dashboard, instead of setting up new values.</span></span> <span data-ttu-id="41ca2-110">Por otro lado, después de configurar nuevos valores para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede exportarlos a un archivo XML para su uso en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="41ca2-110">On the other hand, after setting up new values for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can export them to an XML file to be used in another machine.</span></span>  
  
 <span data-ttu-id="41ca2-111">Para obtener información sobre cómo importar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración, consulte [importación o exportación usando configuración de panel de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md) y [importación o exportación de configuración de BizTalk mediante BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span><span class="sxs-lookup"><span data-stu-id="41ca2-111">For information on importing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) and [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="41ca2-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="41ca2-112">Prerequisites</span></span>  
 <span data-ttu-id="41ca2-113">Para realizar esta operación, debe iniciado sesión como miembro del grupo Administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="41ca2-113">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="update-the-host-instance-level-settings"></a><span data-ttu-id="41ca2-114">Actualizar la configuración de nivel de instancia de host</span><span class="sxs-lookup"><span data-stu-id="41ca2-114">Update the host instance level settings</span></span>  
  
1. <span data-ttu-id="41ca2-115">En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="41ca2-115">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2. <span data-ttu-id="41ca2-116">En el **panel de configuración de BizTalk** cuadro de diálogo el **instancias de Host** ficha, realice cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="41ca2-116">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instances** tab, do any of the following:</span></span>  
  
   -   <span data-ttu-id="41ca2-117">Modificar la configuración de .NET CLR para una instancia de host.</span><span class="sxs-lookup"><span data-stu-id="41ca2-117">Modify the .NET CLR settings for a host instance.</span></span> <span data-ttu-id="41ca2-118">Consulte [cambiar la configuración de .NET CLR](../core/how-to-modify-net-clr-settings.md).</span><span class="sxs-lookup"><span data-stu-id="41ca2-118">See [Change the .NET CLR Settings](../core/how-to-modify-net-clr-settings.md).</span></span>  
  
   -   <span data-ttu-id="41ca2-119">Modificar configuración de la limitación de la memoria de orquestación.</span><span class="sxs-lookup"><span data-stu-id="41ca2-119">Modify the orchestration memory throttling settings.</span></span> <span data-ttu-id="41ca2-120">Consulte [cambiar la configuración de la limitación de memoria de orquestación](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span><span class="sxs-lookup"><span data-stu-id="41ca2-120">See [Change the Orchestration Memory Throttling Settings](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41ca2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="41ca2-121">See Also</span></span>  
 [<span data-ttu-id="41ca2-122">Uso del panel de configuración para ajustar el rendimiento de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="41ca2-122">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)