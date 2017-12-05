---
title: Itinerario basado en Enrutamiento y procesamiento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8354538-e45c-487d-a380-59f497ea060f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7600408837ed2ef40e11bc179bf0739fb15c5a61
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="itinerary-based-routing-and-processing"></a><span data-ttu-id="5342e-102">Enrutamiento basado en itinerario y procesamiento</span><span class="sxs-lookup"><span data-stu-id="5342e-102">Itinerary-Based Routing and Processing</span></span>
<span data-ttu-id="5342e-103">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implementa un patrón de slip enrutamiento mediante el uso de componentes de canalización personalizados.</span><span class="sxs-lookup"><span data-stu-id="5342e-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implements a routing slip pattern through the use of custom pipeline components.</span></span> <span data-ttu-id="5342e-104">Metadatos de mensajes y otros factores se usan para determinar la lista de distribución adecuada, también conocido como un itinerario, que se utilizará para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="5342e-104">Message metadata and other factors are used to determine the appropriate routing slip, also known as an itinerary, to be used for each message.</span></span> <span data-ttu-id="5342e-105">Esta lista de distribución puede realizar la transformación del mensaje, invocar los servicios de orquestación y definir mensaje enrutamiento pasos que ejecutará el servidor BizTalk Server, desacoplamiento eficazmente las instrucciones de procesamiento de mensajes del núcleo del motor de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5342e-105">This routing slip can perform message transformation, invoke orchestration services, and define message routing steps that BizTalk Server will execute, effectively decoupling message processing instructions from the core BizTalk Server engine.</span></span>  
  
 <span data-ttu-id="5342e-106">Para obtener más información sobre cómo se procesan los itinerarios, consulte [escenarios clave y las tareas de desarrollo](../esb-toolkit/key-scenarios-and-development-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="5342e-106">For more information on how itineraries are processed, see [Key Scenarios and Development Tasks](../esb-toolkit/key-scenarios-and-development-tasks.md).</span></span>