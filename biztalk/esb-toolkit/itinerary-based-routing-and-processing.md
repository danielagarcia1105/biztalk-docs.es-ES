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
ms.openlocfilehash: 5405e1e37834071bb4a1295b5e99bde3bf6ec846
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="itinerary-based-routing-and-processing"></a>Enrutamiento basado en itinerario y procesamiento
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implementa un patrón de slip enrutamiento mediante el uso de componentes de canalización personalizados. Metadatos de mensajes y otros factores se usan para determinar la lista de distribución adecuada, también conocido como un itinerario, que se utilizará para cada mensaje. Esta lista de distribución puede realizar la transformación del mensaje, invocar los servicios de orquestación y definir pasos de enrutamiento de mensajes que se [!INCLUDE[prague](../includes/prague-md.md)] se ejecutará, desacoplamiento eficazmente las instrucciones de procesamiento de mensajes del núcleo del motor de BizTalk Server.  
  
 Para obtener más información sobre cómo se procesan los itinerarios, consulte [escenarios clave y las tareas de desarrollo](../esb-toolkit/key-scenarios-and-development-tasks.md).