---
title: "Escalar la solución orientada a servicios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling, service solutions
- service solution tutorial, scaling
ms.assetid: 6c22a68d-03e7-4174-b612-0e2246aa9413
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3026664d3a365630c93bf1c61d7cf635fdd9dc31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-the-service-oriented-solution"></a>Escalar la solución orientada a servicios
Para escalar la solución de modo que admita un mayor rendimiento a la vez que mantiene un baja latencia de mensajes, debe usar la versión en línea de la solución. La solución en línea no tiene en cuenta la base de datos Cuadro de mensajes al interactuar con los sistemas servidor.  
  
 También puede agregar servidores de procesamiento BizTalk Server para ejecutar orquestaciones. De esta forma se reduce la utilización de cada servidor de modo que las solicitudes nuevas se puedan procesar rápidamente. También puede escalar verticalmente el servidor Cuadro de mensajes para que tenga capacidad adicional para controlar el rendimiento de mensajes.  
  
 No obstante, la solución de arquitectura orientada a servicios no obtiene ventajas de tener varias bases de datos cuadro de mensajes. Varios cuadros de mensajes requieren transacciones de coordinador de transacciones distribuidas (DTC). Las transacciones aumentan la latencia de mensajes general.  
  
 Puede reducir el tiempo de respuesta mediante la eliminación del componente de canalización que agrega información de encabezado MQSeries. Para obtener más información, consulte [pone de manifiesto de implementación de la solución orientada a servicios](../core/implementation-highlights-of-the-service-oriented-solution.md).  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar un servicio en la solución orientada a servicios](../core/developing-a-service-oriented-solution.md)