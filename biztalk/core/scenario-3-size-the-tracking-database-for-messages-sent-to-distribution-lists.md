---
title: "Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para mensajes envían fuera a listas de distribución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Tracking database, database size
ms.assetid: bc6e0da0-46d1-42d6-8ec9-29a28719fbb3
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dca1722e24e0c76c85699ea00fcf6ffc120b2e14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-3-sizing-the-tracking-database--for-messages-sent-out-to-distribution-lists"></a>Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución
En la siguiente ilustración, tiene un mensaje que procede a través de una orquestación, se cambia dentro de la orquestación y se envía a varios puertos de envío a través de una lista de distribución.  
  
 ![Mensaje a través de una orquestación a varios puertos](../core/media/biztalk-server-message-orch-multiple-ports.gif "BizTalk_Server_message_orch_multiple_ports")  
  
 **Mensaje de BizTalk Server que se realiza a través de una orquestación y se envía a varios puertos**  
  
 Éstos son algunos de los datos utilizados en este escenario:  
  
-   El tamaño del mensaje es de 10 KB.  
  
-   No se promueven propiedades.  
  
-   Se reciben 3,5 millones de mensajes al año.  
  
-   El seguimiento está activado para todos los eventos. Hay cinco eventos en este escenario.  
  
    -   Recepción del mensaje M0  
  
    -   Salida del mensaje M1 del puerto de recepción  
  
    -   Salida del mensaje M3 por el puerto de envío  
  
    -   Salida del mensaje M4 por el puerto de envío  
  
    -   Salida del mensaje M5 por el puerto de envío  
  
 Si se aplica esta información a la ecuación, se obtiene el siguiente resultado:  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-a-single-promoted-property"></a>Mensajes de una orquestación que se envían a una lista de distribución con una sola propiedad promovida  
 En este ejemplo, vamos a promover una sola propiedad con un tamaño aproximado de 10 bytes, como hicimos en un escenario anterior. La ecuación tiene ahora el siguiente aspecto:  
  
```  
[((5*150 bytes) + (10*230 bytes) + (1*5(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 260) * 3,500,000]/1024/1024 = 11048 MB ~ 10.79 GB per year  
```  
  
 Si promovemos otra propiedad que tenga un tamaño de 20 bytes, la ecuación sería:  
  
```  
[((5*150 bytes) + (10*230 bytes) + ((1*5(52 bytes + 10 bytes) + (1*5(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 670) * 3,500,000]/1024/1024 = 12417 MB ~ 12.13 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-message-body-tracking-activated"></a>Mensajes de una orquestación que se envían a una lista de distribución con el seguimiento del cuerpo de los mensajes activado  
 Si desea utilizar el seguimiento del cuerpo de los mensajes, la ecuación sería la siguiente para este ejemplo:  
  
```  
[3,500,000 * 6 * 5KB]/1024 = 102539.06 MB ~ 100.14 GB per year  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento](../core/using-message-variables-to-size-the-tracking-database.md)   
 [Ajustar el tamaño de la base de datos de seguimiento para realizar el seguimiento de cuerpos de mensaje](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)