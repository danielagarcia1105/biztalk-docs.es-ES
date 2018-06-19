---
title: Consideraciones para trabajar con las API BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd8ccf63-6989-4ad6-a193-cf3043e9a466
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b00eb00013fefde42e1972b89a661d0a2ba0de6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237844"
---
# <a name="considerations-for-working-with-bam-apis"></a>Consideraciones para trabajar con API de BAM
Cuando se utiliza un objeto "Microsoft.BizTalk.Bam.EventObservation.EventStream", por ejemplo DirectEventStream, BufferedEventStream, MessagingEventStream u OrchestrationEventStream, BAM captura hitos como los que se registran automáticamente en formato de hora universal coordinada (UTC) (también hace referencia a la hora del meridiano de Greenwich). Cuando envía la fecha y hora a BAM mediante las API, se reciben en el formato enviado sin conversión a formato UTC. Tenga en cuenta las siguientes consideraciones cuando desarrolle sus soluciones de BAM:  
  
-   Los datos de los que se ha realizado un seguimiento desde el servidor BizTalk Server se reciben en formato UTC. Puede ser incoherente con otros datos provenientes de la secuencia de eventos.  
  
-   Si utiliza la secuencia de eventos de API para proporcionar datos de seguimiento de fecha y hora en el formato de hora local, los datos del portal de BAM serán incorrectos, ya que se espera que todas las horas de los datos BAM estén en formato UTC.  
  
 Si tiene aplicaciones existentes que utilicen hora local, que ahora se está actualizando y que planee utilizar el portal de BAM; debe modificar sus datos para que encajen con el formato UTC. También es preciso modificar su aplicación personalizada para convertir el formato a UTC.  
  
## <a name="see-also"></a>Vea también  
 [Implementar soluciones de BAM](../core/implementing-bam-solutions.md)