---
title: Mensajes de error | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error messages
- ports, error messages
- Catch Exception block [Orchestration Designer], error messages
- error messages, receiving
- messages, errors
- error messages, sending
ms.assetid: 33d62260-b5e0-4d14-b2d2-996733d588e7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4127fd5718ee910cb298436c0d0f7058ccba55b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="fault-messages"></a>Mensajes de error
Los puertos de solicitud-respuesta pueden tener mensajes de error asociados de modo que si se produce un error después de que se ha enviado una solicitud, el servicio de respuesta puede comunicar el error al solicitante, en vez de la respuesta.  
  
 Cada operación de un puerto de solicitud-respuesta puede controlar un número arbitrario de distintos errores. Un mensaje de error puede tener cualquier tipo de mensaje aunque éste debe ser único para la operación no debe ser el que use la respuesta en esa operación de puerto.  
  
## <a name="receiving-fault-messages"></a>Recibir mensajes de error  
 Si la operación de puerto envía una solicitud y, después, recibe una respuesta, puede usarla para recibir uno o más tipos de mensajes de error diferentes.  
  
 Puede configurar un **excepción de filtrado** bloque para controlar un mensaje de error entrante, seleccione el error adecuado en la operación de puerto de solicitud-respuesta como su tipo de objeto de excepción.  
  
## <a name="sending-fault-messages"></a>Enviar mensajes de error  
 Si la operación de puerto recibe una respuesta y, después, envía una solicitud, puede usarla para enviar uno o más tipos de mensajes de error diferentes.  
  
 Por ejemplo si la orquestación detecta una condición de error y produce una excepción, puede enviar un mensaje de error desde el **excepción de filtrado** bloque que controla la excepción. Construirá un mensaje de error de un tipo adecuado para expresar la situación al servicio que participa y especificará ese mensaje de error en una forma Envío que usará el error correspondiente en la operación de puerto.  
  
## <a name="see-also"></a>Vea también  
 [Excepciones](../core/exceptions.md)