---
title: "Medir el rendimiento máximo sostenible del motor | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maximum sustainable throughput (MST)
- maximum sustainable throughput (MST), about maximum sustainable throughput (MST)
- performance, maximum sustainable thoughput (MST)
ms.assetid: d83f734f-1a44-4da0-a755-45ba204cadaf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5507aca58669ed5c81034ba91e16d1183e07188
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="measuring-maximum-sustainable-engine-throughput"></a>Medir el rendimiento máximo sostenible del motor
Una de las consideraciones principales al planear un sistema de BizTalk Server debería consistir en determinar el rendimiento máximo sostenible del sistema. El rendimiento máximo sostenible de un sistema de BizTalk Server representa la carga más elevada del tráfico de mensajes que el sistema de BizTalk puede controlar sin límites en la producción. La importancia de este rendimiento radica en el hecho de que si la carga supera el rendimiento máximo sostenible, los mensajes se acumulan en la base de datos de cuadro de mensajes y es posible que se retrase la entrega del mensaje. Si realiza el cálculo del rendimiento máximo sostenible del sistema de BizTalk Server durante la comprobación habitual, puede escalar el sistema para evitar que se produzcan escenarios extendidos de sobrecarga en la producción.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Factores que afectan al rendimiento sostenible máximo](../core/factors-that-affect-maximum-sustainable-performance.md)  
  
-   [Escenarios de prueba para medir MST del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md)  
  
-   [Recomendaciones al probar el rendimiento del motor](../core/recommendations-when-testing-engine-performance.md)