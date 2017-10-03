---
title: "Consideraciones de rendimiento para la publicación de eventos BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, BAM
- publishing, BAM
- BAM, publishing
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 5a99e61a-a3d9-47fd-a933-2297f79817a5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebab873c94c0ae17abf9938883662ca8777cef36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="performance-considerations-for-bam-event-publishing"></a>Consideraciones de rendimiento para la publicación de eventos BAM
BAM admite dos formas de publicación de eventos empresariales:  
  
-   Sincrónica  
  
-   Asincrónica  
  
 En el siguiente diagrama se ilustran los dos modelos.  
  
 ![](../core/media/bam-topologies.gif "bam_topologies")  
Topologías de BAM  
  
 El enfoque sincrónico es mucho más sencillo para la administración y utilización del código, mientras que el enfoque asíncrono le permite un rendimiento mejor.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Seguimiento de eventos empresariales sincrónico](../core/synchronous-business-event-tracking.md)  
  
-   [Seguimiento de eventos empresariales asíncronos](../core/asynchronous-business-event-tracking.md)