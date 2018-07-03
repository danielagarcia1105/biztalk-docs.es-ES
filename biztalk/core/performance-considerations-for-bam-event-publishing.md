---
title: Consideraciones de rendimiento para la publicación de eventos BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- publishing, BAM
- BAM, publishing
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 5a99e61a-a3d9-47fd-a933-2297f79817a5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c031f9a3325eda9cbcf865eaf72d1d9e100616c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997541"
---
# <a name="performance-considerations-for-bam-event-publishing"></a>Consideraciones de rendimiento para la publicación de eventos BAM
BAM admite dos formas de publicación de eventos empresariales:  
  
- Sincrónica  
  
- Asincrónica  
  
  En el siguiente diagrama se ilustran los dos modelos.  
  
  ![](../core/media/bam-topologies.gif "bam_topologies")  
  Topologías de BAM  
  
  El enfoque sincrónico es mucho más sencillo para la administración y utilización del código, mientras que el enfoque asíncrono le permite un rendimiento mejor.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Seguimiento sincrónico de eventos empresariales](../core/synchronous-business-event-tracking.md)  
  
-   [Seguimiento asincrónico de eventos empresariales](../core/asynchronous-business-event-tracking.md)