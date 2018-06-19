---
title: Detecciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5350c4b3-ecc5-487e-a75a-16af090ffa06
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 848bf4c2841462adecec749c1254eb9c273e1f31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299460"
---
# <a name="discoveries"></a><span data-ttu-id="15891-102">Detecciones</span><span class="sxs-lookup"><span data-stu-id="15891-102">Discoveries</span></span>
<span data-ttu-id="15891-103">El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración proporciona una administración centralizada y experiencia de supervisión de artefactos relacionados con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="15891-103">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack provides a centralized management and monitoring experience for BizTalk Server related artifacts.</span></span>  
  
## <a name="discovery-of-artifacts"></a><span data-ttu-id="15891-104">Detección de artefactos</span><span class="sxs-lookup"><span data-stu-id="15891-104">Discovery of artifacts</span></span>  
 <span data-ttu-id="15891-105">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración, los agentes de supervisión detectan los artefactos desde un equipo único en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="15891-105">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack, the monitoring agents discover the artifacts from a single runtime machine.</span></span> <span data-ttu-id="15891-106">De forma predeterminada, el módulo de administración detecta los artefactos en el primer equipo que se une al grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="15891-106">By default, the management pack discovers the artifacts on the first machine that is joined to the BizTalk group.</span></span> <span data-ttu-id="15891-107">Sin embargo si desea planear detectar los artefactos en el equipo de su elección, a continuación, debe usar la característica de invalidación para cambiar la configuración para la detección automática.</span><span class="sxs-lookup"><span data-stu-id="15891-107">However if you want plan to discover the artifacts on the machine of your choice then you must use the override feature to change the settings for automatic discovery.</span></span> <span data-ttu-id="15891-108">Para usar una invalidación para cambiar la configuración para la detección automática, consulte [configuraciones opcionales](../technical-guides/optional-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="15891-108">To use an override to change the setting for automatic discovery, see [Optional Configurations](../technical-guides/optional-configurations.md).</span></span>  
  
 <span data-ttu-id="15891-109">Las acciones y tareas que se realizan desde la consola del operador de SCOM son únicas para los artefactos que se detecta y supervisa en todos los equipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="15891-109">The actions and tasks that are carried from the SCOM Operations Console are unique to the artifacts that are discovered and monitored on all runtime machines.</span></span> <span data-ttu-id="15891-110">Para ver todas las tareas que proporciona el módulo de administración de BizTalk Server, haga clic en **tareas** en el panel de supervisión de la consola del operador de Operations Manager 2007 R2/2012.</span><span class="sxs-lookup"><span data-stu-id="15891-110">To see all the tasks the BizTalk Server Management Pack provides, click **Tasks** in the Monitoring pane of the Operations Manager 2007 R2/2012 Operations Console.</span></span>