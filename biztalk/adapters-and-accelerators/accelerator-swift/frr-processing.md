---
title: Procesamiento de FRR | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, processing
- FRR, components
- FRR, process flow
ms.assetid: 8b064d18-5ee7-44fd-95d1-9a0d66f1ad1a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c343d214a97895e90bae2bc3a041180c0cc8e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987013"
---
# <a name="frr-processing"></a>Procesamiento de FRR
El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] característica de conciliación de respuesta de FIN (FRR) pone en correlación los mensajes FIN de la acceso de Alliance SWIFT (AAS) con el mensaje original desde [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] que responde el mensaje AAS. Cada vez que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] envía un mensaje original, las cachés FRR una copia de cualquier mensaje enlazado para SWIFT y que no haya dejado de procesamiento. A continuación, supervisa el cuadro de mensajes para los mensajes de respuesta devueltos por AAS a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]y recoge los mensajes de confirmación/NAK que corresponde a la copia del mensaje almacenado en caché.  

 FRR establece una correlación entre un mensaje saliente y un mensaje entrante mediante la comparación de las propiedades de Id. de correlación. FRR establece las propiedades promocionadas de la copia del mensaje original, según la naturaleza de la respuesta y, a continuación, enruta el mensaje original en el cuadro de mensajes para su posterior procesamiento.  

## <a name="frr-components"></a>Componentes FRR  
 FRR incluye un proceso continuo (orquestación) que supervisa los mensajes entrantes y salientes y para cada mensaje entrante o saliente, promociona las propiedades de identificación que va a usar para la comparación. Una serie de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] componentes funcionan junto con la orquestación de FRR, enrutamiento de mensajes entre los componentes FRR en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]y entre [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] y AAS. Estos componentes se enumeran a continuación:  

- Un FRR ubicación de recepción que recibe el mensaje original de la aplicación de back-end.  

- La orquestación de FRR que supervisa los mensajes entrantes y salientes y establece la correlación entre ellos.  

- Un FRR puerto de envío que envía el mensaje original desde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] a AAS.  

- El adaptador de BizTalk para MQSeries que permite la transmisión de datos entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y aas (que usa colas de MQSeries).  

- Un FRR ubicación de recepción que recibe los mensajes de respuesta FIN de SAA.  

- Un conjunto de puertos de envío FRR, cada uno de ellos envía mensajes correlacionados de un tipo específico de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a una aplicación de back-end para el procesamiento personalizado.  

  Para los componentes anteriores, puede agregar un controlador personalizado de back-end que procesa el mensaje original se establecieron las propiedades promocionadas de los cuales FRR.  

## <a name="frr-process-flow"></a>Flujo del proceso de FRR  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] lleva a cabo la conciliación en el proceso siguiente:  

1. La aplicación back-end enruta el mensaje original a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].  

2. Ubicación de recepción de un FRR recibe el mensaje, lo procesa en la canalización de recepción asociado y lo enruta al BizTalk MessageBox.  

   > [!NOTE]
   >  Puede usar FRR junto con el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] característica de reparación de mensajes y nuevo envío, o por separado. Si ha instalado la reparación de mensajes y nuevo envío, puede configurar el sistema de reparación de mensajes después del paso 2. La orquestación de reparación de mensajes enruta el mensaje reparado y comprobado/aprobada a BizTalk MessageBox para su posterior procesamiento de FRR.  

3. Si el mensaje en el cuadro de mensajes está enlazado para SWIFT y ha pasado la validación, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] activa una instancia de la orquestación de FRR. La orquestación conserva una copia del mensaje saliente. A continuación, se espera una respuesta de SAA, por lo que puede coincidir con el mensaje saliente a cualquier respuesta entrante en un estado activado. Esta instancia de la orquestación solo procesa ese mensaje saliente específico y las respuestas a ese mensaje correlacionadas. Cualquier otro mensaje, incluso del mismo tipo, se procesa por otra instancia de la orquestación.  

4. Al mismo tiempo que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] activa la instancia de orquestación de FRR [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] enruta el mensaje al puerto de envío que envía mensajes a AAS. La canalización de envío promueve una propiedad de identificación del mensaje y las propiedades necesarias para el procesamiento por MQSeries. A continuación, envía el mensaje al adaptador de BizTalk para MQSeries.  

5. El adaptador de BizTalk para MQSeries transporta el mensaje a la cola de MQSeries adecuada en AAS.  

6. AAS genera una respuesta inmediata para el enrutamiento directamente a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. AAS, a continuación, enruta el mensaje a la red SWIFT. La red SWIFT genera otras respuestas, lo envía a AAS para el enrutamiento a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. AAS establece la propiedad del token de correlación para el mensaje de respuesta FIN en el valor de identificación del mensaje del mensaje original.  

7. Los transportes SAA hacer una copia de la respuesta FIN a través del adaptador de BizTalk para MQSeries para [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].  

8. Ubicación de recepción de la FRR recibe la respuesta y enruta el mensaje a través de la FRR canalización de recepción que procesa los token de correlación de la respuesta. A continuación, se coloca la respuesta en el BizTalk MessageBox.  

9. La instancia de orquestación de FRR recoge cualquier mensaje del cuadro de mensajes que tiene un token de correlación igual a la propiedad de Id. de mensaje de la copia del mensaje original.  

10. Si la respuesta indica que el mensaje original se ha procesado correctamente por AAS/SWIFT, la instancia de orquestación de FRR establece la propiedad A4SWIFT_Failed promocionadas de la copia del mensaje original en False y establece el BTS. El valor adecuado para la propiedad de operación.  

11. Si el mensaje original no se ha procesado correctamente por AAS/SWIFT, la instancia de orquestación de FRR establece el BTS. Propiedad de la operación en el valor adecuado y, a continuación, se designa el mensaje para la reparación estableciendo A4SWIFT_Failed en True y la propiedad A4SWIFT_FRRFailedReason promovido a la razón del error.  

12. La instancia de orquestación de FRR descarta los mensajes de respuesta y, a continuación, enruta la copia del mensaje original (con las propiedades promocionadas que indica la respuesta) en el cuadro de mensajes.  

13. Uno de los puertos de envío FRR se configure para enrutar las respuestas en uno o varios controladores personalizados recoge la copia del mensaje original con las propiedades promocionadas.  

14. El controlador personalizado o los controladores se suscribe a, recupera y procesa la copia del mensaje original según sea necesario para la aplicación de back-end.
