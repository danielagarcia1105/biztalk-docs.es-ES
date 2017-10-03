---
title: "Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Tracking database, database size
ms.assetid: 5b8fed48-d9c9-4d1f-a320-d3e23b8b1ec9
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b9c99c99485e34f95c6f6a75b86170d73678518
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-1-sizing-the-tracking-database--for-simple-biztalk-messages"></a>Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk
En la ilustración siguiente, un mensaje sencillo del servidor BizTalk Server entra y sale de éste sin sufrir ninguna transformación.  
  
 ![Mensaje de BizTalk Server simple &#45; ninguna transformación](../core/media/simple-bts-message.gif "Simple_BTS_Message")  
  
 **Un simple mensaje de BizTalk Server: sin transformación**  
  
 Antes de aplicar la fórmula de la sección anterior, necesitará algunos datos acerca de este escenario. En este ejemplo, se usan los siguientes parámetros:  
  
-   El tamaño del mensaje es 5 K.  
  
-   No se promoverá ninguna propiedad.  
  
-   Se reciben 3,5 millones de mensajes al año.  
  
-   El seguimiento está activado para todos los eventos. Hay cuatro eventos en este escenario. Estos eventos son:  
  
    -   Recepción del mensaje M0  
  
    -   Salida del mensaje M1 del puerto de recepción  
  
    -   Recepción del mensaje M1 por la canalización de transmisión  
  
    -   Salida del mensaje M2 por la canalización de envío  
  
-   Se crean dos mensajes adicionales en este escenario. El mensaje M0 es el mensaje entrante y, por tanto, no lo crea BizTalk Server. M1 es el mensaje de salida del puerto de recepción y M2 es el mensaje de salida del puerto de transmisión. BizTalk Server crea los mensajes M1 y M2.  
  
 Si se aplica esta información a la fórmula, se obtiene el siguiente resultado:  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-with-a-single-promoted-property"></a>Mensajes con una única propiedad promovida  
 Volvamos al ejemplo y agreguemos un dato adicional al escenario. Desea promover un único campo, con un tamaño aproximado de 10 bytes, del mensaje original. El tamaño máximo de un campo promovido es 256 caracteres, o aproximadamente 256 bytes (516 bytes si los caracteres son Unicode).  
  
 Con este dato adicional, la ecuación produce el siguiente resultado:  
  
```  
[(2*150 bytes) + (4*230 bytes) + (1*2(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 124) * 3,500,000]/1024/1024 = 4486 MB ~ 4.38 GB per year  
```  
  
 Si quisiera promover un campo adicional cuyo tamaño fuese superior a 10 bytes, la ecuación sería la siguiente:  
  
```  
[(2*150 bytes) + (4*230 bytes) + ((1*2*(52 bytes + 10 bytes) + (1*2*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 248) * 3,500,000]/1024/1024 = 4899 MB ~ 4.78 GB per year  
```  
  
 Como puede ver, si promociona una sola propiedad de 10 bytes en este escenario, agregará 333,79 MB (0,33 GB) adicionales por año al tamaño de la base de datos de seguimiento de BizTalk.  
  
 Promocionar dos propiedades de 10 bytes agregará 667,58 MB (0,65 GB) de espacio adicional por año al tamaño de la base de datos de seguimiento de BizTalk.  
  
## <a name="messages-with-message-body-tracking-activated"></a>Mensajes con seguimiento del cuerpo de los mensajes activado  
 En este ejemplo, supongamos además que planeamos activar el seguimiento del cuerpo de los mensajes. Tendremos que agregar la segunda ecuación para el seguimiento de mensajes de la sección anterior. Para este ejemplo, la ecuación tendrá el siguiente aspecto:  
  
```  
[3,500,000 * 4 * 5KB]/1024 = 68359.375 MB ~ 66.75 GB per year  
  
```  
  
 Sumar los resultados de las dos ecuaciones permite estimar que la base de datos de seguimiento de BizTalk aumentará, aproximadamente, de 54,48 GB a 54,88 GB por año.  
  
## <a name="see-also"></a>Vea también  
 [Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento](../core/using-message-variables-to-size-the-tracking-database.md)   
 [Ajustar el tamaño de la base de datos de seguimiento para realizar el seguimiento de cuerpos de mensaje](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)