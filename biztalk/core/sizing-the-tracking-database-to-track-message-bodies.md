---
title: Ajustar el tamaño de la base de datos de seguimiento de cuerpos de mensaje de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
- message variables [Tracking database], MsgNum
- HAT, ports
- Tracking database, messages
- tracking, orchestrations
- tracking, messages
- HAT, orchestrations
- tracking, ports
ms.assetid: ee75e530-f15d-4ceb-ba67-0b0b24d9df6b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b5abc3f2a48f2baea5d158e1a0268a7eede51c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277924"
---
# <a name="sizing-the-tracking-database-to-track-message-bodies"></a>Ajustar el tamaño de la base de datos de seguimiento para realizar un seguimiento de los cuerpos de mensaje
Si planea realizar un seguimiento de los cuerpos de mensaje en la base de datos de seguimiento de BizTalk, tendrá que tener en cuenta el tamaño de éstos al realizar los cálculos. Use la siguiente ecuación:  
  
```  
[Msgs * MsgNum * (MsgSize)]/1024 = Data size in MB  
```  
  
 Considere la posibilidad de agregar el tamaño medio del contexto de mensaje en el valor MsgSize anterior si resulta significativo en relación con el tamaño del mensaje.  
  
 La variable MsgNum se determina al activar las características de seguimiento en el nivel de puerto o en el nivel de orquestación mediante el seguimiento de instancias de servicios y eventos de mensajes en la página Concentrador de grupo. Asimismo, deberá aplicar esta fórmula a cada proceso de mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento](../core/using-message-variables-to-size-the-tracking-database.md)   
 [Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)