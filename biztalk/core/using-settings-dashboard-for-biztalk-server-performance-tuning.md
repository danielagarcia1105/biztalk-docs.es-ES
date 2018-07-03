---
title: Mediante el panel de configuración de BizTalk Server Performance Tuning | Microsoft Docs
description: Usar el panel de configuración de administración de BizTalk Server para actualizar la configuración de la instancia de host, el host y el grupo
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb1ddac-1e8f-4928-9c70-8326ae64a734
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b6ed0c44bea5abaaac7b2009e27819e66043957
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974861"
---
# <a name="use-settings-dashboard-for-biztalk-server-performance-tuning"></a><span data-ttu-id="c4284-103">Usar el panel de configuración para el servidor BizTalk Server optimización del rendimiento</span><span class="sxs-lookup"><span data-stu-id="c4284-103">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>

## <a name="overview"></a><span data-ttu-id="c4284-104">Información general</span><span class="sxs-lookup"><span data-stu-id="c4284-104">Overview</span></span>
<span data-ttu-id="c4284-105">Con el panel de configuración, puede ajustar ampliamente la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para optimizar su rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c4284-105">Using the Settings Dashboard, you can extensively tweak [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings for performance optimization.</span></span> <span data-ttu-id="c4284-106">También puede modificar la configuración del grupo de BizTalk, el host de BizTalk y la instancia de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c4284-106">You can also modify settings for the BizTalk Group, BizTalk Host, and BizTalk Host Instance.</span></span>  
  
- <span data-ttu-id="c4284-107">**Configuración de nivel de grupo**: el nivel de grupo, puede usar el [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] para establecer propiedades como el intervalo de actualización de configuración, tamaño de lote máximo del mensaje, seguimiento de nivel de grupo, etcetera. Esta configuración se aplica a todas las máquinas en un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c4284-107">**Group-level settings**: At the group level, you can use the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] to set properties like the configuration refresh interval, maximum message batch size, group level tracking, etc. These settings are applied to all machines in a BizTalk Group.</span></span>  
  
- <span data-ttu-id="c4284-108">**Configuración de nivel de host**: en el nivel de host, puede modificar la configuración, como el seguimiento de host, las propiedades relacionadas con la limitación basada en recursos, las propiedades relacionadas con la limitación del proceso de mensaje y propiedades relacionadas con la limitación de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="c4284-108">**Host-level settings**: At the host level, you can modify settings like host tracking, properties related to resource based throttling, properties related to message process throttling, and properties related to orchestrations throttling.</span></span> <span data-ttu-id="c4284-109">Estas opciones se aplican a todas las instancias del host seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c4284-109">These settings are applied to all instances of the selected host.</span></span>  
  
- <span data-ttu-id="c4284-110">**Configuración del nivel de instancia de host**: en el nivel de instancia de host, puede modificar la configuración de .NET CLR y propiedades relacionadas con la limitación de memoria de orquestación.</span><span class="sxs-lookup"><span data-stu-id="c4284-110">**Host instance level settings**: At the host instance level, you can modify .NET CLR settings and properties related to orchestration memory throttling.</span></span> <span data-ttu-id="c4284-111">Estas opciones se aplican solo a la instancia de host seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c4284-111">These settings are applied to only the selected host instance.</span></span>  
  
  <span data-ttu-id="c4284-112">Para obtener más información sobre el grupo de BizTalk, el BizTalk Host y configuración de la instancia de Host de BizTalk, consulte [cómo modificar la configuración del grupo](../core/how-to-modify-group-settings.md), [cómo modificar la configuración del Host](../core/how-to-modify-host-settings.md), y [cómo modificar el Host Configuración de instancia](../core/how-to-modify-host-instance-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c4284-112">For more information about BizTalk Group, BizTalk Host, and BizTalk Host Instance settings, see [How to Modify Group Settings](../core/how-to-modify-group-settings.md), [How to Modify Host Settings](../core/how-to-modify-host-settings.md), and [How to Modify Host Instance Settings](../core/how-to-modify-host-instance-settings.md).</span></span>  
  
  <span data-ttu-id="c4284-113">El panel de configuración le permite importar y exportar la configuración de BizTalk a través de implementaciones que no es necesario que sean idénticas.</span><span class="sxs-lookup"><span data-stu-id="c4284-113">The Settings Dashboard enables you to import/export BizTalk settings across deployments that need not be identical.</span></span> <span data-ttu-id="c4284-114">Mediante el uso de la interfaz de usuario, puede asignar los hosts y las instancias de hosts desde implementaciones de destino hasta implementaciones de origen.</span><span class="sxs-lookup"><span data-stu-id="c4284-114">Using the user interface, you can map the hosts and host instances from destination to source deployments.</span></span> <span data-ttu-id="c4284-115">Esto le ayudará a aplicar la configuración a un entorno donde los nombres de host y equipo, o sus respectivos números, son diferentes.</span><span class="sxs-lookup"><span data-stu-id="c4284-115">This helps you apply settings to an environment where host and machine names, or their respective counts, are different.</span></span> <span data-ttu-id="c4284-116">Para obtener más información acerca de la importación/exportación de configuración de BizTalk, consulte [importación o exportación usando configuración de panel de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="c4284-116">For more details about importing/exporting BizTalk settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4284-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4284-117">See Also</span></span>  
 [<span data-ttu-id="c4284-118">Administrar la configuración de rendimiento de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c4284-118">Manage BizTalk Server Performance Settings</span></span>](../core/managing-biztalk-server-performance-settings.md)