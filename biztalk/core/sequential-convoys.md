---
title: Convoyes secuenciales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- convoy sets
- correlation sets, sequential receive tasks
ms.assetid: f05ff42c-2236-42a3-8166-19700e0c3d97
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 329d0f56d9f092cd146a900c42ed48d5206a6393
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sequential-convoys"></a>Convoyes secuenciales
Un convoy secuencial permite unir varios mensajes individuales para obtener un resultado necesario. Un convoy secuencial es un conjunto de mensajes relacionados que tienen un orden predefinido. Aunque los mensajes no tienen que ser exactamente iguales, BizTalk Server debe recibirlos en orden secuencial.  
  
 Por ejemplo, supongamos el caso de una empresa de venta directa en Internet que recibe pedidos nuevos de clientes directos y distribuidores durante el transcurso del día. Todos los pedidos recibidos antes de las 2:00 p.m. deben enviarse al almacén en un único lote, y la secuencia de recepción de los pedidos se debe mantener. De este modo, los pedidos recibidos con anterioridad tendrán prioridad en el caso de que se agoten las existencias de un artículo en el almacén. Para crear este lote de pedidos, se ensamblan todos los pedidos del día en un único archivo que contiene información de encabezado sobre el lote. A las 2:00 p.m., todos los pedidos del día se envían al almacén para su procesamiento. Todos los pedidos recibidos después de las 2:00 p.m. se colocan en un lote nuevo para procesarlos el día siguiente.  
  
 El escenario anterior es un ejemplo de proceso empresarial en el que se necesita un procesamiento de convoy secuencial para los mensajes entrantes. Según las normas de la empresa, todos los pedidos individuales recibidos antes de las 2:00 p.m. de un día concreto, se deben procesar a la vez como un lote. Para ello, es necesario que el primer mensaje recibido inicie una nueva instancia de orquestación e inicialice un conjunto de correlaciones. A partir de ese momento, los demás pedidos recibidos que sean de ese mismo tipo de mensaje se enrutan a la instancia de orquestación que ya hay en ejecución. Para lograr esto, se coloca un **escuchar** forma (que contiene un **recepción** forma y un **retraso** forma) dentro de un **bucle** forma. Tras alcanzarse la forma Retraso, termina la forma Bucle. Esto permite la recepción de un número desconocido de pedidos en el mismo proceso empresarial.  
  
## <a name="implementing-sequential-convoys"></a>Implementar convoyes secuenciales  
 Para implementar los convoyes secuenciales se utiliza el patrón de diseño de mensajería de "recepciones correlacionadas secuenciales" de BizTalk Server. Las recepciones correlacionadas secuenciales son recepciones que guardan correlación con recepciones anteriores.  
  
 El procesamiento de convoy se usa en los casos en los que los conjuntos de correlaciones de una recepción los inicializa otra recepción.  
  
 Hay una serie de restricciones aplicables a las recepciones que requieren un procesamiento de convoy. Estas restricciones son las siguientes:  
  
-   Los conjuntos de correlaciones que constituyen un conjunto de convoy secuencial para una determinada recepción los debe inicializar una recepción anterior.  
  
-   El puerto de una recepción que requiere un procesamiento de convoy secuencial debe ser el mismo que el puerto de la recepción que inicializa el conjunto de convoy. No se admiten convoyes entre puertos.  
  
-   Los tipos de mensaje de una recepción que requiere un procesamiento de convoy deben coincidir con el tipo de mensaje de la recepción que inicializa el conjunto de convoy, excepto si hay activa una instrucción de recepción en un puerto de entrega ordenada.  
  
-   Todas las recepciones que participan en un convoy secuencial deben ejecutarse con posterioridad a todos los conjuntos de correlaciones inicializados (o posteriores) por la recepción originadora de la inicialización, salvo si se procesan en un puerto de entrega ordenada.  
  
-   Si una instrucción de recepción de activación inicializa un convoy secuencial, la recepción de activación no puede tener una expresión de filtro, salvo si se procesa en un puerto de entrega ordenada.  
  
-   Si una instrucción de recepción de activación inicializa un convoy secuencial, las siguientes recepciones no pueden estar dentro de una orquestación anidada.  
  
 Para obtener un ejemplo de implementación de convoy secuencial, consulte [agregador (ejemplo de BizTalk Server)](../core/aggregator-biztalk-server-sample.md).  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con escenarios de convoyes](../core/working-with-convoy-scenarios.md)   
 [Convoyes paralelos](../core/parallel-convoys.md)