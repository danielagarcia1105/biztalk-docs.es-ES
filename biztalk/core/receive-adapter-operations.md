---
title: "Operaciones del adaptador de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b61ea356-f2a1-4604-8e52-13d2961399d0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804a136841c33977b350b8d59dfbf18c7108cc79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-adapter-operations"></a>Operaciones del adaptador de recepción
Los adaptadores de recepción pueden realizar las siguientes operaciones:  
  
-   **Envío unidireccional: void SubmitMessage (IBaseMessage msg).** Después de recibir un mensaje de un puerto de recepción, el adaptador lo envía a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para ser procesados por suscripción de una orquestación o puerto de envío.  
  
-   **Suspender: void MoveToSuspendQ (IBaseMessage msg).** Cuando el adaptador determina un análisis, una transmisión, una serialización o se ha producido otro error de aplicación tras el envío, el mensaje se mueve a la cola de suspensión.  
  
-   **Enviar solicitud: void SubmitRequestMessage (IBaseMessage requestMsg, cadena correlationToken, [MarshalAs (UnmanagedType.bool)] bool firstResponseOnly, expirationTime de fecha y hora, IBTTransmitter responseCallback).** Un adaptador de recepción envía un mensaje entrante a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un par de solicitud-respuesta. Después de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa correctamente este mensaje de solicitud, envía la respuesta al adaptador para transmitirla a un extremo específico.