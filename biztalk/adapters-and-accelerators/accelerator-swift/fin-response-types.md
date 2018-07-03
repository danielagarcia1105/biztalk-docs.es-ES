---
title: Tipos de respuesta FIN | Microsoft Docs
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
ms.openlocfilehash: 382e0e628d01903a6274dd3f0321379f71fc7a15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995405"
---
# <a name="fin-response-types"></a>Tipos de respuesta FIN
Conciliación de respuesta FIN (FRR) reconcilia las respuestas a cualquier mensaje de FIN de SWIFT categoría 0 al 9. En respuesta a uno de estos mensajes FIN, la aplicación SWIFT FIN siempre envía al menos uno y posiblemente más de una confirmación (ACK) o negativo (NAK) de confirmación. En la tabla siguiente se muestra los tipos de mensaje de entrada y la salida (respuesta) los mensajes procesados por FRR.  


| Salida /<br /><br /> de entrada |                                             Tipo de mensaje                                              |                                                                                                                                                                                                                             Estado del mensaje                                                                                                                                                                                                                              |
|-------------------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           Saliente            |                              Todos los tipos de mensaje de FIN de SWIFT categoría 0 a 9                              |                                                                                                                                                                                                                                   N/D                                                                                                                                                                                                                                   |
|            Entrada            |                         MQ Series PAN/NAN (confirmación de nivel de transporte MQ Series/NAK)                         |                                                                                                                                                                                                                    Confirmación de transporte de MQSeries                                                                                                                                                                                                                    |
|                               |                                     MT010 (advertencia de no entrega)                                      |                                                                     SWIFT original ha enviado correctamente mensajes al socio comercial, pero no tiene ninguna indicación de que el socio comercial recibió el mensaje. Si [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe varios mensajes de advertencia de no entrega (NDW), se repite y espera a que el siguiente mensaje esperado.                                                                     |
|                               |                                     MT011 (notificación de entrega)                                     |                                                                                                                                                                     SWIFT original ha enviado correctamente mensajes al socio comercial y reciba una indicación de que el socio comercial recibió el mensaje.                                                                                                                                                                      |
|                               |                                      MT012 (notificación de remitente)                                      |                                                                                                                                                            SWIFT recibe correctamente el mensaje original desde [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].                                                                                                                                                             |
|                               |                                      MT015 (DIN o NAK retrasada)                                      |                                                                                                                                                                                                  SWIFT no ha enviado el mensaje original al socio comercial.                                                                                                                                                                                                   |
|                               |                                      MT019 (anular la notificación)                                       |                                                                                                                                                                                                                 Se anuló la transmisión del mensaje en SWIFT.                                                                                                                                                                                                                  |
|                               | MTS21_FIN_ACKNAK (confirmación o una confirmación negativa de un mensaje FIN enviado por un LT (ACK/NAK)) | SWIFT correctamente o no recibió el mensaje de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. Este mensaje trata ambos casos. Si es una confirmación o un NAK viene determinada por el valor del campo 451 del mensaje ("0" para la confirmación) y "1" para NAK. Se trata de la primera respuesta entregada a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. |

## <a name="deployment-of-schemas-for-frr"></a>Implementación de esquemas de FRR  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] programa de instalación implementa esquemas en FrrSchemas.dll para todos los mensajes de nivel de sistema (como se muestra en la tabla anterior). La orquestación de FRR requiere estos esquemas para implementarse. Dado que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] programa de instalación implementa estos esquemas en FrrSchemas.dll, no es necesario y no, debe implementar estos esquemas en otro proyecto. Si lo hace, se generará un error.  

 FRRSchemas.dll incluye los siguientes esquemas:  

-   TransportAck  

-   MT010  

-   MT011  

-   MT012  

-   MT015  

-   MT019  

-   MTS21_FIN_ACKNAK