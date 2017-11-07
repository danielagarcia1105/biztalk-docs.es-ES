---
title: "Implementar modelos de diseño en orquestaciones | Documentos de Microsoft"
description: "El agregador, enrutamiento por contenidos, enrutador dinámico, control de errores, agente de mensajes y varios patrones de diseño en BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f62ba955-018a-40e7-b303-497acc906019
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 290b31e8d5494c7a00eb02517e910fc877da9124
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="implement-design-patterns-in-orchestrations"></a>Implementar modelos de diseño en orquestaciones
En esta sección se describen los patrones comunes para programar BizTalk Server, así como los patrones de integración empresarial. Se puede aprovechar un solo patrón o combinar varios patrones para diseñar su proceso empresarial y, posteriormente, implementar el diseño mediante el uso de las formas del Diseñador de orquestaciones de BizTalk.  
  
## <a name="design-patterns"></a>Patrones de diseño  
 A continuación se describe brevemente cada patrón y se incluyen vínculos a otros temas o ejemplos en los que se muestra cómo implementar los patrones mediante el Diseñador de orquestaciones de BizTalk.  
  
### <a name="aggregator"></a>Agregador  
 El patrón de agregación es el patrón para recibir información de varios orígenes y consolidarla en un solo mensaje. Para obtener un ejemplo de este patrón, vea Aggregate.odx en [agregador (ejemplo de BizTalk Server)](../core/aggregator-biztalk-server-sample.md).  
  
### <a name="calling-pipelines-from-an-orchestration"></a>Llamar a canalizaciones desde una orquestación.  
 Ahora puede llamar a canalizaciones de envío y recepción desde sus orquestaciones. Esto permite reutilizar las canalizaciones y contribuye a mantener una orquestación desacoplada desde las fases de canalización. Para obtener un ejemplo de este patrón, vea Aggregate.odx en [agregador (ejemplo de BizTalk Server)](../core/aggregator-biztalk-server-sample.md). Otro ejemplo es CMP.odx en [compuesto por el procesador de mensajes (ejemplo de BizTalk Server)](../core/composed-message-processor-biztalk-server-sample.md). Vea también [cómo usar expresiones para ejecutar canalizaciones](../core/how-to-use-expressions-to-execute-pipelines.md).  
  
### <a name="composed-message-processor"></a>Procesador de mensaje compuesto  
 Procesador de mensaje compuesto es el patrón para procesar elementos individuales desde un mensaje de intercambio agregado o por lotes. Para obtener un ejemplo de este patrón, vea CMP.odx en [compuesto por el procesador de mensajes (ejemplo de BizTalk Server)](../core/composed-message-processor-biztalk-server-sample.md).  
  
### <a name="content-based-router"></a>Enrutador basado en contenido  
 El enrutador basado en contenido es el patrón para determinar el destinatario de un mensaje basado en parte del contenido del mensaje. Para obtener un ejemplo de este patrón, vea [CBRSample (ejemplo de BizTalk Server)](../core/cbrsample-biztalk-server-sample.md).  
  
### <a name="dynamic-router"></a>Enrutador dinámico  
 El enrutador dinámico es un patrón para determinar la dirección de destino y el protocolo de transporte basado en el resultado del procesamiento de mensajes. Puede utilizar un puerto de envío dinámico o un **vínculo de función** forma para implementar este patrón. Para obtener un ejemplo de este patrón, vea ReceiveSend.odx en [SendMail](../core/sendmail.md). Otro ejemplo es SupplierProcess.odx en [PartyResolution (ejemplo de BizTalk Server)](../core/partyresolution-biztalk-server-sample.md).  
  
### <a name="error-handling"></a>Tratamiento de errores  
 BizTalk Server permite designar un control automatizado de los mensajes con errores como alternativa al comportamiento predeterminado de colocar los mensajes con errores en la cola de suspensión. Puede enrutar los mensajes con error a un puerto de suscripción para elaborar un informe o procesarlos. Para obtener un ejemplo de este patrón, vea ResubmitLogic.odx en [Error Handling (carpeta de ejemplos de BizTalk Server)](../core/error-handling-biztalk-server-samples-folder.md).  
  
### <a name="exception-handling-and-compensation"></a>Controlador de excepciones y compensación  
 Puede usar un controlador de excepciones y un **Iniciar excepción** forma o un **expresión** forma para el control de excepciones. Por ejemplo, puede colocar el siguiente código en el **expresión** forma que se va a producir la excepción:,  
  
```  
excp = new System.Exception();  
throw(excp);  
```  
  
 Puede usar un bloque de compensación y una **compensar** forma que se va a realizar la compensación en las transacciones que se han confirmado. Para obtener un ejemplo de este patrón, vea UpdateContact.odx en [compensación (ejemplo de BizTalk Server)](../core/compensation-biztalk-server-sample.md). Otro ejemplo es de [personalizado excepciones](../core/custom-exceptions.md).  
  
### <a name="message-broker"></a>Agente de mensajes  
 El patrón de agente de mensajes determina el destino de un mensaje y controla el flujo de mensajes. Para obtener más información, consulte [de procesamiento en la orquestación OrderBroker](../core/processing-in-the-orderbroker-orchestration.md).  
  
### <a name="message-filter"></a>Filtro de mensajes  
 El patrón de filtro de mensajes selecciona los mensajes que cumplen criterios concretos de procesamiento. Puede implementar este patrón mediante la adición de la expresión de filtro para un activado **recepción** forma. Para obtener más información, consulte [utilizando filtros con el mensaje de forma recepción](../core/using-filters-with-the-receive-message-shape.md).  
  
### <a name="message-translator"></a>Traductor de mensajes  
 El patrón traductor de mensajes convierte un mensaje de un formato a otro. Puede implementar este patrón mediante el uso de una asignación de BizTalk con un **transformar** forma de una orquestación. Para obtener un ejemplo de este patrón, vea HelloOrchestration.odx en [HelloWorld (ejemplo de BizTalk Server)](../core/helloworld-biztalk-server-sample.md).  
  
### <a name="parallel-convoy"></a>Convoy paralelo  
 El patrón de convoy paralelo permite agrupar varios elementos individuales para obtener algo que un elemento individual no puede obtener por sí solo. El conjunto de elementos relacionados puede llegar en cualquier orden, pero BizTalk Server debe recibir todos ellos antes de empezar el proceso. 
  
### <a name="scatter-and-gather"></a>Dispersión y recopilación  
 El patrón de dispersión y recopilación permite enviar mensajes a varios destinatarios y recibir los mensajes de cada destinatario. Para implementar este patrón, puede usar el patrón divisor y de agregación. Usar el patrón de agregación para ensamblar los resultados del patrón divisor y colocarlos bajo un **acciones paralelas** forma. 
  
### <a name="sequential-convoy"></a>Convoy secuencial  
 El patrón de convoy secuencial permite agrupar varios elementos individuales para obtener algo que un elemento individual no puede obtener por sí solo. Un convoy secuencial es un conjunto de elementos relacionados que tienen un orden predefinido. Aunque los elementos no tienen que ser exactamente iguales, BizTalk Server debe recibir los elementos en un orden secuencial. 
  
### <a name="splitter"></a>Divisor  
 El patrón divisor toma un único mensaje y lo divide en varios mensajes.  
  
### <a name="suspend-with-retry"></a>Suspensión con reintento  
 El patrón de suspensión con reintento permite a la orquestación suspender un mensaje cuando hay un error. La suspensión ocurre dentro de un bucle, de modo que la orquestación se suspende, se solicita intervención y, a continuación, se vuelve a intentar repetir la operación un número fijo de veces.  
  
## <a name="see-also"></a>Vea también  
 [Diseño del flujo de las orquestaciones](../core/designing-orchestration-flow.md)