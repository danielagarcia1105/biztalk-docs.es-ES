---
title: "AS2 Arquitectura de la solución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41e493ba-919b-4520-9c12-92d6757984ef
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c22557059bd13dd99e0b24a2291b7f121d561bbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="as2-solution-architecture"></a>Arquitectura de solución AS2
El procesamiento AS2 se realiza de forma independiente al procesamiento EDI. Se reciben los mensajes AS2, se procesan y se envía una confirmación además del procesamiento de la carga EDI. Como resultado, el procesamiento AS2 se diseña y configura además del procesamiento EDI. Además, puede usar AS2 para transportar mensajes que sean o no EDI.  
  
 En esta sección se describe la arquitectura de soluciones AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], incluidos el procesamiento de envío, de recepción y de un extremo a otro.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Mensajería AS2](../core/as2-messaging.md)  
  
-   [Rol de los acuerdos de AS2 de procesamiento](../core/the-role-of-agreements-in-as2-processing.md)  
  
-   [Cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md)  
  
-   [Cómo BizTalk Server envía mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md)