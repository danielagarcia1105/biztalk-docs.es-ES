---
title: "La inclusión de Back-end invocación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MessageBox database, performance
- service solution tutorial, performance
- performance, in-line invocation
- Inline Invocation of Back-End Processes [service solutions], performance
- performance, MessageBox database
ms.assetid: 991d080f-a4cc-4f14-bab3-3b8b74636daf
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7300429e9f74abc7bc10569c653bdaa0a4c13b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="inlining-back-end-invocation"></a>La inclusión de Back-end invocación
La versión de llamada en línea de las soluciones completas proporciona los tiempos más rápidos de procesamiento. La versión en línea elimina la sobrecarga que se deriva de guardar los mensajes de solicitud y respuesta entre los sistemas servidor y la base de datos de cuadro de mensajes. En la versión de adaptador, el mensaje pasa de la orquestación de envío al cuadro de mensajes. El host que ejecuta el adaptador recoge el mensaje y lo envía al proceso de servidor al enviarlo de nuevo al cuadro de mensajes.  
  
 La eficacia de la versión en línea implica enlazar la orquestación directamente con los protocolos de transporte de los sistemas servidor. En la versión en línea, en vez de establecerse la comunicación mediante puertos lógicos, la orquestación llama a los sistemas servidor mediante tres ensamblados personalizados. Si se cambia un transporte de sistema servidor, debe volver a escribir y compilarse un ensamblado. En la tabla siguiente se describen los ensamblados y su función:  
  
|Nombre de ensamblado|Conexión de servidor|  
|-------------------|--------------------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall|Utiliza MQSeries **obtener** y **colocar** las funciones de mensaje.|  
|Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall|Invoca el servicio Web para el sistema de transacciones.|  
|Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall|Llama a los servicios Web que simulan SAP.|  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación del servicio en la solución orientada a servicios](../core/implementation-highlights-of-the-service-oriented-solution.md)   
 [Desarrollar un servicio en la solución orientada a servicios](../core/developing-a-service-oriented-solution.md)   
 [Traducir los patrones del servicio en la solución orientada a servicios](../core/translating-the-patterns-of-the-service-oriented-solution.md)   
 [El servicio de supervisión orientada a servicios solución con BAM](../core/monitoring-the-service-oriented-solution-with-bam.md)