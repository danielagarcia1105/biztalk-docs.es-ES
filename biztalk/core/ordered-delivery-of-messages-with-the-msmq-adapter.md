---
title: Entrega ordenada de mensajes con el adaptador de MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MSMQ adapters, ordered delivery
ms.assetid: e8dafc76-e894-4120-9cea-d014d635850e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac842fcd1e9b386fa885844f3a797504ed7c4c3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263588"
---
# <a name="ordered-delivery-of-messages-with-the-msmq-adapter"></a>Entrega ordenada de mensajes con el adaptador de MSMQ
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Proporciona un **entrega ordenada** puertos de envío de la opción para estático. Establecer el **entrega ordenada** opción en un puerto de envío a **True** garantiza que BizTalk Server entrega mensajes al puerto de envío en el mismo orden que se publican en la base de datos de cuadro de mensajes. Para proporcionar una entrega ordenada de extremo a extremo, deben cumplirse las siguientes condiciones:  
  
-   Los mensajes se tienen que recibir con un adaptador que conserve el orden de los mensajes cuando se envíen al servidor BizTalk Server.  
  
-   Debe suscribirse a estos mensajes con un puerto de envío que tiene la **entrega ordenada** opción **True**.  
  
-   Si una orquestación se utiliza para procesar los mensajes, una sola instancia de la orquestación deben usarse, la orquestación debe estar configurada para utilizar un convoy secuencial y la **entrega ordenada** propiedad de la puerto de recepción de la orquestación debe establecerse en **True**.  
  
## <a name="using-the-msmq-adapter-for-ordered-delivery-of-messages"></a>Utilizar el adaptador de MSMQ para la entrega ordenada de los mensajes  
 El adaptador de recepción MSMQ proporciona compatibilidad para preservar el orden de los mensajes cuando se envíen a BizTalk Server. To-end ordenada puede conseguir la entrega de mensajes a través de BizTalk Server cuando se reciben mensajes con el adaptador de MSMQ si los mensajes se procesan por un puerto de envío que se configura con el **entrega ordenada** opción establecida en  **True**.  
  
## <a name="see-also"></a>Vea también  
 [Entrega ordenada de mensajes](../core/ordered-delivery-of-messages.md)   
 [Cómo configurar ubicación de recepción de MSMQ](../core/how-to-configure-an-msmq-receive-location.md)