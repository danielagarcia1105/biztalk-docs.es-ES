---
title: "Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Tracking database, database size
ms.assetid: d1cfb8b9-d4e2-4069-8db3-18f72358652b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62ea6e463dfb3a44e2628f57b632634d7a9bd212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-2-sizing-the-tracking-database--for-messages-in-orchestrations"></a>Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones
Veamos un ejemplo que incluye una orquestación. La siguiente ilustración muestra todo el proceso empresarial. En este escenario, entra un mensaje en BizTalk Server, se envía a través de una orquestación, se cambia dentro de la orquestación y se envía a un puerto de envío.  
  
 ![Proceso de mensaje de BizTalk Server](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")  
  
 **El proceso de mensaje de BizTalk Server**  
  
 Éstos son algunos de los datos utilizados en este escenario:  
  
-   El tamaño del mensaje es 5 K.  
  
-   No nos estamos promocionar las propiedades.  
  
-   El número de mensajes que recibimos año es 3,5 millones.  
  
-   El seguimiento está activado para todos los eventos. Hay seis eventos en este escenario.  
  
    -   Recepción del mensaje M0  
  
    -   Salida del mensaje M1 del puerto de recepción  
  
    -   Recepción del mensaje M1 por la orquestación  
  
    -   Salida del mensaje M2 de la orquestación  
  
    -   Recepción del mensaje M2 por el puerto de envío  
  
    -   Salida del mensaje M3 por la canalización de envío  
  
-   Se crean tres mensajes adicionales en este escenario. El mensaje M0 es el mensaje entrante y, por tanto, no lo crea BizTalk Server. El mensaje M1 es el mensaje saliente del puerto de recepción, M2 es el mensaje saliente de la orquestación y M3 es el mensaje saliente del puerto de transmisión.  
  
 Si se aplica esta información a la fórmula le ofrece el siguiente resultado:  
  
```  
[(3*150 bytes) + (6*230 bytes) + (0*0(52 bytes + 0) * 3,500,000]/1024/1024  
[(450 + 1380 + 0) * 3,500,000]/1024/1024 = 6108 MB ~ 5.96 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-a-single-promoted-property"></a>Mensajes de orquestaciones con una sola propiedad promovida  
 Ahora vamos a promover un solo campo en este escenario, como en el ejemplo anterior. La propiedad promovida tiene un tamaño aproximado de 10 bytes. La ecuación tiene ahora el siguiente aspecto:  
  
```  
[((3*150 bytes) + (6*230 bytes) + (1*3*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 186) * 3,500,000]/1024/1024 = 6729 MB ~ 6.57 GB per year  
```  
  
 Si tiene que promover otra propiedad que tenga un tamaño de 20 bytes, la formula sería:  
  
```  
[(3*150 bytes) + (6*230 bytes) + ((1*3*(52 bytes + 10 bytes) + (1*3*(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 372) * 3,500,000]/1024/1024 = 7350 MB ~ 7.18 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-message-body-tracking-activated"></a>Mensajes de orquestaciones con el seguimiento del cuerpo de los mensajes activado  
 Si desea utilizar seguimiento del cuerpo de los mensajes, el resultado de calcular el espacio adicional necesario es idéntico al resultado del escenario anterior, o 50,1 GB por año.  
  
## <a name="see-also"></a>Vea también  
 [Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento](../core/using-message-variables-to-size-the-tracking-database.md)   
 [Ajustar el tamaño de la base de datos de seguimiento para realizar el seguimiento de cuerpos de mensaje](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)