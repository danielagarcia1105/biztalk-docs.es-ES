---
title: Separar tipo de transporte y procesamiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transport types, decoupling processing
- processing, decoupling transport types
- transport types
- transport types, service solutions
- service solution tutorial, MQSeries adapters
- processing, service solutions
- service solution tutorial, decoupling transport type and processing
- correlations, MQSeries adapters
- MQSeries adapters, correlations
- MQSeries adapters, service solutions
ms.assetid: 0b2c733a-e2c7-42ff-a733-f712fde38f7e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b14522c6bbf9393bc22f632c4db5eeb5e4a22a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238604"
---
# <a name="decoupling-transport-type-and-processing"></a>Separar tipo de transporte y procesamiento
En una solución orientada a servicios, existe a menudo una línea que delimita claramente el procesamiento empresarial y los detalles de la transmisión y recepción de mensajes. Esto le permite cambiar por separado el proceso empresarial o la parte de mensajería de la solución.  
  
 La solución orientada a servicios infringe este principio de diseño en un lugar. En esta sección se describen la situación, las alternativas posibles y la estructura seleccionada.  
  
## <a name="correlation-and-the-mqseries-adapter"></a>Correlación y adaptador de MQSeries  
 Para utilizar el adaptador de MQSeries, no puede utilizar los identificadores de correlación estándar de servidor BizTalk Server. Ello se debe a que el identificador de correlación va a un sistema de servidor IBM que tiene su propio sistema de identificadores de correlación. En su lugar, debe utilizar el **MQSeries.MQMD Correlid** y **MQSeries.MQMD MSGID** propiedades. Al utilizar estas propiedades, puede incluir información específica de transporte en la orquestación y, por tanto, en el proceso empresarial.  
  
 Una forma de controlar esta dependencia sería utilizar el identificador de correlación del servidor BizTalk Server y utilizar un componente de canalización personalizado para traducir el identificador de correlación para MQSeries. Esto agrega complejidad al escenario. Además, si cambia el transporte, se deben cambiar dos componentes de canalización. Y, en última instancia, reubica la dependencia (en el componente de canalización) en vez de resolverla.  
  
 Otra opción sería aislar el control de la correlación específica de MQSeries en una orquestación independiente y llamar a esa orquestación. Esto conservaría la independencia del proceso empresarial. Sin embargo, esto incluye una dependencia en tiempo de compilación entre las orquestaciones. Modificar el transporte requiere volver a compilar ambas orquestaciones (como, por ejemplo, al pasar del código auxiliar a la versión del adaptador de la solución). La llamada también agrega a la respuesta tiempo para la solución.  
  
 Dadas la complejidad adicional y la posible disminución del rendimiento, parece que lo más fácil es utilizar la correlación de MQSeries directamente en la orquestación.  
  
 Para obtener más información acerca del adaptador y correlaciones en orquestaciones, consulte [MQSCorrelationSetOrchestration (ejemplo de BizTalk Server)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md).  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación del servicio en la solución orientada a servicios](../core/implementation-highlights-of-the-service-oriented-solution.md)   
 [MQSCorrelationSetOrchestration (ejemplo de BizTalk Server)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)