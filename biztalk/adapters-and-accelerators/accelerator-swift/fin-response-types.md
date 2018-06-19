---
title: Tipos de respuesta FIN | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, response types
- deploying, schemas
- FIN Response Reconciliation, message types
- FRR, deploying schemas
- schemas, deploying
- FIN Response Reconciliation, response types
- messages, message types
- response types [FIN Response Reconciliation]
ms.assetid: a6ef2f20-08ab-40d3-a0a5-cc4048ce0987
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54c890a5e0f51207cce1897b10095a87ae438793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208068"
---
# <a name="fin-response-types"></a>Tipos de respuesta FIN
Conciliación de respuesta FIN (FRR) reconcilia las respuestas a los mensajes de SWIFT FINÉS de categoría del 0 al 9. En respuesta a uno de estos mensajes FIN, la aplicación de SWIFT FINÉS siempre envía al menos uno y posiblemente más de una confirmación (ACK) o un valor negativo (NAK) de confirmación. En la tabla siguiente muestra los tipos de mensajes de entrada y la salida (respuesta de) los mensajes procesados por FRR.  
  
|Salida /<br /><br /> de entrada|Tipo de mensaje|Estado del mensaje|  
|----------------------------|------------------|--------------------|  
|Salida|Todos los tipos de mensaje SWIFT FINÉS de categoría del 0 al 9|N/D|  
|Entrada|MQ Series PAN/NAN (confirmación de nivel de transporte MQ Series/NAK)|Confirmación de transporte de MQSeries|  
||MT010 (advertencia de no entrega)|SWIFT enviado correctamente la versión original del mensaje al socio comercial, pero tiene ninguna indicación de que el socio comercial recibió el mensaje. Si [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe varios mensajes de advertencia de no entrega (NDW), se ejecuta un bucle y espera a que el siguiente mensaje esperado.|  
||MT011 (notificación de entrega)|SWIFT enviado correctamente la versión original del mensaje al socio comercial y recibe una indicación de que el socio comercial recibió el mensaje.|  
||MT012 (notificación de remitente)|SWIFT recibe correctamente el mensaje original desde [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].|  
||MT015 (DIN o NAK diferida)|SWIFT no ha enviado el mensaje original al socio comercial.|  
||MT019 (anular la notificación)|Se anuló la transmisión de mensajes en SWIFT.|  
||MTS21_FIN_ACKNAK (confirmación o una confirmación negativa de un mensaje FIN enviado por un LT (confirmación/NAK))|SWIFT correctamente o no ha recibido el mensaje de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. Este mensaje trata ambos casos. Si es una confirmación o un NAK viene determinado por el valor en el campo 451 del mensaje ("0" para ACK) y "1" para NAK. Se trata de la primera respuesta entregada a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].|  
  
## <a name="deployment-of-schemas-for-frr"></a>Implementación de esquemas para FRR  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]el programa de instalación implementa esquemas en FrrSchemas.dll para todos los mensajes de nivel de sistema (tal como se muestra en la tabla anterior). La orquestación FRR requiere estos esquemas para implementarse. Dado que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] el programa de instalación implementa estos esquemas en FrrSchemas.dll, no es necesario y no es así, debe implementar estos esquemas en otro proyecto. Si lo hace, se generará un error.  
  
 FRRSchemas.dll incluye los siguientes esquemas:  
  
-   TransportAck  
  
-   MT010  
  
-   MT011  
  
-   MT012  
  
-   MT015  
  
-   MT019  
  
-   MTS21_FIN_ACKNAK