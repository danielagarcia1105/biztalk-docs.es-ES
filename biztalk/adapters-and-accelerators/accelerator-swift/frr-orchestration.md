---
title: Orquestación FRR | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, promoted properties
- orchestrations, message subscriptions
- promoted properties, messages
- FRR, orchestrations
- subscriptions, messages
- orchestrations, reconciliation time-out
- messages, message/response correlation
- message/response correlation
- promoted properties, FIN Response Reconciliation
- orchestrations, FRR
- outbound messages
- FIN Response Reconciliation, promoted properties
- direct bindings
- reconciliation time-out
- bindings, direct
- messages, subscriptions
- subscriptions, orchestrations
- messages, outbound
- MessageBox database
ms.assetid: ea8d31c2-ac3b-44ac-8064-d008da4f7f72
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f56b16f59b967ccd9e57d03d38f86e64795da477
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967892"
---
# <a name="frr-orchestration"></a>Orquestación de FRR
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]implementa FRR a través de la orquestación FRR. La orquestación determina si el Token de correlación de la respuesta FIN coincide con el identificador del mensaje del mensaje original. Procesa el mensaje en paralelo con las funciones de envío realizadas por el puerto de envío que envía el mensaje a AAS y con las funciones de recepción realizadas por la ubicación de recepción que recibe el mensaje de AAS.  
  
 En el nivel más alto, una instancia de la orquestación realiza el siguiente procesamiento:  
  
1.  Las memorias caché una copia del mensaje saliente original enlazado para SAA escuchando en el cuadro de mensajes.  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]crea una instancia de la orquestación cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] enruta el mensaje original en el cuadro de mensajes.  
  
2.  Espera a que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] para publicar una respuesta FIN de SAA en el cuadro de mensajes.  
  
3.  Establece las propiedades de la copia del mensaje original, dependiendo de la naturaleza de la respuesta FIN promocionadas.  
  
4.  Publica el cuadro de mensajes de la copia del mensaje original. Controladores personalizados, a continuación, pueden suscribirse para recuperar y procesar el mensaje según sea necesario.  
  
## <a name="subscription-to-outbound-messages"></a>Suscripción a los mensajes salientes  
 La orquestación FRR se enlaza directamente al cuadro de mensajes. La orquestación FRR se suscribe a todos los mensajes salientes enlazados para la red SWIFT que no contienen errores de validación, si se suscribe a las siguientes propiedades:  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed == false (según lo establecido por el proceso de validación de SWIFT desensamblador)  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Swiftbound == true (según lo establecido por el proceso de configuración de SWIFT desensamblador)  
  
## <a name="messageresponse-correlation"></a>Correlación de mensaje de respuesta  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Correlaciona el mensaje de FIN de salida original al mensaje de respuesta entrante FINÉS comparando las siguientes propiedades:  
  
-   La propiedad de contexto MQMD_CorrelID de la respuesta FIN  
  
-   El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken propiedad MTXYY del mensaje saliente. Esta propiedad se promociona la etapa de resolución de entidades de la canalización de recepción.  
  
 Los valores de estas propiedades deben ser idénticos. La fase de codificador de la canalización de envío para los mensajes enlazados para SWIFT establece la propiedad MQMD_MsgID del mensaje saliente en el valor de la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken propiedad. AAS establece la propiedad MQMD_CorrelID del mensaje de respuesta en el valor de MQMD_MsgID.  
  
## <a name="setting-of-promoted-properties"></a>Configuración de las propiedades promocionadas  
 Después de recibir una respuesta FIN y correlacionar con la copia del mensaje original, la orquestación FRR establece las siguientes propiedades promocionadas de la copia del mensaje original según la naturaleza de la respuesta:  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailed en True si la respuesta fue una confirmación o False si la respuesta fue un NAK  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason a uno de los valores siguientes, si la respuesta fue un NAK:  
  
    -   *\<ErrorCode\>*  (desde el campo 405 del mensaje de confirmación negativo MTS21_FIN_ACKNAK)  
  
    -   TransportError (desde un mensaje de MQ Series PAN/NAN)  
  
    -   DelayedNAK (de un mensaje MT015 (DIN))  
  
    -   AbortReceived (desde un MT019 mensaje (anular la notificación))  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason en tiempo de espera agotado si [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no recibió una respuesta dentro del período de tiempo de espera. Para obtener más información sobre el tiempo de espera de retraso FRR, vea la sección "Tiempo de espera de conciliación" más adelante o [establecer el tiempo de espera de retraso FRR](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md).  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceType a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  
  
-   BTS. Operación para el valor que corresponde al tipo de mensaje de respuesta. Para obtener más información, consulte [crear los puertos de envío FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendTransport para un mensaje de MQ Series PAN/NAN (confirmación de nivel de transporte MQ Series/NAK)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend010NDW para un mensaje de MT010 (advertencia de no entrega)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend011Delivered para un mensaje de MT011 (notificación de entrega)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend012SenderACK para un mensaje de MT012 (notificación de remitente)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend015DNK para un mensaje de MT015 (DIN o retrasado NAK)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend019Abort para un mensaje de MT019 (anular la notificación)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendS21ACK para un mensaje de confirmación de MTS21_FIN_ACKNAK (confirmación de un mensaje FIN enviado por un LT)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendS21NAK para un mensaje de confirmación negativo MTS21_FIN_ACKNAK (NAK de un mensaje FIN enviado por un LT)  
  
## <a name="direct-binding"></a>Enlace directo  
 Recibir entradas para la orquestación se definen mediante las suscripciones que hace que la orquestación en el cuadro de mensajes. Propiedades de contexto y los valores que se promueve la orquestación definen las salidas de envío de un mensaje que la orquestación se publica en el cuadro de mensajes. Debido a este enlace directo en el cuadro de mensajes, la orquestación está desacoplada entre las siguientes opciones:  
  
-   Físico ubicaciones de recepción que reciban mensajes de salida de la aplicación de back-end para el enrutamiento a AAS  
  
-   Mensajes de FIN: los puertos de envío que envía la salida [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] para SWIFT Alliance acceso (AAS)  
  
-   Las ubicaciones de recepción que reciben los mensajes entrantes de respuesta FIN de SAA  
  
-   Las colas de MQSeries físicas donde depositar AAS respuestas FINÉS  
  
## <a name="reconciliation-time-out"></a>Tiempo de espera de conciliación  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] crea una nueva instancia de la orquestación FRR, iniciar la orquestación espera para las respuestas FIN. En tiempo de ejecución, debe configurar la orquestación en tiempo de espera después de algún tiempo, por lo que no esperará la respuesta indefinidamente. Cuando la duración de tiempo de espera expira, la orquestación FRR promociona el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason propiedad y lo establece en tiempo de espera agotado. A continuación, publica mensajes de salida en el cuadro de mensajes y finaliza. Si el tiempo de espera, el identificador de correlación ya no existe.  
  
 Puede crear un controlador personalizado para procesar mensajes que ha superado el tiempo de espera (la copia del mensaje saliente original). [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]hacerlo mediante el uso de una forma escuchar en la orquestación. Para obtener más información, consulte [establecer el tiempo de espera de retraso FRR](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md).