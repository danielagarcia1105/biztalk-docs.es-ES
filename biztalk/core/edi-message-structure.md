---
title: Estructura de mensaje EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c9a0447-447f-483c-825d-547c06ad691e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9395ed5e0b03bda48e19d6413f95ca2e74a3f1e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-message-structure"></a>Estructura de los mensajes EDI
Los mensajes EDI constan de un sobre y series jerárquicas de elementos estructurales. El sobre contiene un conjunto de encabezados y finalizadores, cada conjunto de éstos describe y contiene un elemento estructural. Estos elementos estructurales son los siguientes:  
  
```  
Interchange  
   Group  
      Transaction set/message  
         Segment  
            Data Element  
               Sub Element  
```  
  
 La estructura jerárquica de un mensaje EDI habilita los conjuntos de transacciones/mensajes y grupos que se van a procesar por lotes. Incluso si un intercambio contiene sólo un conjunto de transacciones/mensaje y sólo un grupo, ese intercambio se estructura con los mismos elementos estructurales básicos que tendría si se procesara por lotes, con la excepción de que no sería un conjunto de varias transacciones/mensajes o elementos de grupo.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Encabezados y finalizadores EDI](../core/edi-headers-and-trailers.md)  
  
-   [Elemento estructural de intercambio EDI](../core/edi-interchange-structural-element.md)  
  
-   [Elemento estructural de grupo EDI](../core/edi-group-structural-element.md)  
  
-   [Elemento estructural de mensajes de conjunto de transacciones de EDI](../core/edi-transaction-set-message-structural-element.md)  
  
-   [Elemento estructural de segmento EDI](../core/edi-segment-structural-element.md)  
  
-   [Elemento estructural de elemento de datos EDI](../core/edi-data-element-structural-element.md)