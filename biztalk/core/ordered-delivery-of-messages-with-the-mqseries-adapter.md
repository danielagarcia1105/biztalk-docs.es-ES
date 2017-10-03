---
title: Entrega ordenada de mensajes con el adaptador de MQSeries | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MQSeries adapters, ordered delivery
ms.assetid: 517ff2a4-7315-43b5-8d4b-7494adf141e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f8b602adf93152f6af1e5dbbc576180d570a4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ordered-delivery-of-messages-with-the-mqseries-adapter"></a>Entrega ordenada de mensajes con el adaptador de MQSeries
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Proporciona un **entrega ordenada** puertos de envío de la opción para estático. Establecer el **entrega ordenada** opción en un puerto de envío a **True** garantiza que BizTalk Server entrega mensajes al puerto de envío en el mismo orden que se publican en la base de datos de BizTalk MessageBox. Para proporcionar una entrega ordenada de extremo a extremo, deben cumplirse las siguientes condiciones:  
  
-   Los mensajes se tienen que recibir con un adaptador que conserve el orden de los mensajes cuando se envíen al servidor BizTalk Server. Por ejemplo, al recibir mensajes con el adaptador de recepción de MQSeries, la ubicación de recepción debe configurarse con la opción **orden con pausa** o **orden con suspensión**.  
  
-   Debe suscribirse a estos mensajes con un puerto de envío que tiene la **entrega ordenada** opción **True**.  
  
-   Si una orquestación se utiliza para procesar los mensajes, una sola instancia de la orquestación deben usarse, la orquestación debe estar configurada para utilizar un convoy secuencial y la **entrega ordenada** propiedad de la puerto de recepción de la orquestación debe establecerse en **True**.  
  
## <a name="using-the-mqseries-adapter-for-ordered-delivery-of-messages"></a>Utilizar el adaptador de MQSeries para la entrega ordenada de los mensajes  
 El adaptador de recepción de MQSeries proporciona compatibilidad para conservar el orden de los mensajes cuando se envían a BizTalk Server. To-end ordenada puede conseguir la entrega de mensajes a través de BizTalk Server cuando se reciben mensajes con el adaptador de MQSeries si los mensajes se procesan por un puerto de envío que se configura con el **entrega ordenada** opción establecida en **True**.  
  
## <a name="see-also"></a>Vea también  
 [Entrega ordenada de mensajes](../core/ordered-delivery-of-messages.md)   
 [Cómo configurar MQSeries adaptador ubicaciones de recepción y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)