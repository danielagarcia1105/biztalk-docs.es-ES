---
title: Procesamiento de FRR | Documentos de Microsoft
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
ms.openlocfilehash: f2b0d34ccffd2bf09148bcfc5544b38ea5d0033d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208972"
---
# <a name="frr-processing"></a>Procesamiento de FRR
El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] característica Conciliación de respuesta de FIN (FRR) pone en correlación mensajes FIN de SWIFT Alliance acceso (AAS) con el mensaje original desde [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] que responde el mensaje AAS. Cada vez que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] envía un mensaje original, las cachés FRR una copia de cualquier mensaje enlazado para SWIFT y que no haya dejado de procesamiento. A continuación, supervisa el cuadro de mensajes para los mensajes de respuesta devueltos por AAS a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]y recoge los mensajes de confirmación/NAK que corresponde a la copia del mensaje almacenado en caché.  
  
 FRR establece una correlación entre un mensaje saliente y un mensaje entrante mediante la comparación de las propiedades de Id. de correlación. FRR establece las propiedades promocionadas de la copia del mensaje original según la naturaleza de la respuesta y, a continuación, enruta el mensaje original en el cuadro de mensajes para su posterior procesamiento.  
  
## <a name="frr-components"></a>Componentes FRR  
 FRR incluye un proceso continuo (orquestación) que supervisa los mensajes entrantes y salientes y para cada mensaje entrante o saliente, promociona las propiedades de identificación que va a utilizar para la comparación. Una serie de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] componentes funcionan junto con la orquestación FRR, enrutamiento de mensajes entre los componentes de FRR de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]y entre [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] y AAS. Estos componentes se enumeran a continuación:  
  
-   Un FRR ubicación de recepción que recibe el mensaje original de la aplicación de back-end.  
  
-   La orquestación FRR que supervisa los mensajes entrantes y salientes y establece la correlación entre ellos.  
  
-   Puerto que envía el mensaje original a partir de envío de un FRR [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] a AAS.  
  
-   El adaptador de BizTalk para MQSeries que permite la transmisión de datos entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y aas (que utiliza colas de MQSeries).  
  
-   Un FRR ubicación de recepción que recibe los mensajes de respuesta FIN de AAS.  
  
-   Un conjunto de puertos de envío FRR, cada uno de los cuales envía mensajes correlacionados de un tipo específico de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a una aplicación back-end para el procesamiento personalizado.  
  
 Para los componentes anteriores, puede agregar un controlador personalizado de back-end que procesa el mensaje original se establecieron las propiedades promocionadas de los cuales por FRR.  
  
## <a name="frr-process-flow"></a>Flujo del proceso FRR  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]realiza la conciliación en el proceso siguiente:  
  
1.  La aplicación de back-end enruta el mensaje original a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].  
  
2.  Ubicación de recepción de un FRR recibe el mensaje, lo procesa en la canalización de recepción asociado y lo enruta al BizTalk MessageBox.  
  
    > [!NOTE]
    >  Puede usar FRR junto con el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] característica de reparación de mensajes y nuevo envío, o por separado. Si ha instalado reparar mensajes y nuevo envío, puede configurar el sistema para la reparación de mensaje después del paso 2. La orquestación de reparación de mensajes enruta el mensaje reparado y comprobado/aprobada hacia BizTalk MessageBox para su posterior procesamiento FRR.  
  
3.  Si el mensaje en el cuadro de mensajes está enlazado para SWIFT y ha pasado la validación, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] activa una instancia de la orquestación FRR. La orquestación conserva una copia del mensaje saliente. A continuación, espera una respuesta de AAS, por lo que puede coincidir con el mensaje saliente a cualquier respuesta entrante en un estado activado. Esta instancia de la orquestación sólo procesa ese mensaje saliente específico y las respuestas a ese mensaje correlacionadas. Cualquier otro mensaje, incluso del mismo tipo, se procesa por otra instancia de la orquestación.  
  
4.  Al mismo tiempo que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] activa la instancia de orquestación FRR [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] enruta el mensaje al puerto de envío que envía mensajes a AAS. La canalización de envío promueve una propiedad de identificación del mensaje y las propiedades requeridas para el procesamiento por MQSeries. A continuación, envía el mensaje al adaptador de BizTalk para MQSeries.  
  
5.  El adaptador de BizTalk para MQSeries transporta el mensaje a la cola de MQSeries adecuada en AAS.  
  
6.  AAS genera una respuesta inmediata para el enrutamiento directamente a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. AAS, a continuación, enruta el mensaje a la red SWIFT. La red SWIFT genera otras respuestas, que se envía a AAS para el enrutamiento a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. AAS establece la propiedad de token de correlación para el mensaje de respuesta FIN en el valor de identificación del mensaje del mensaje original.  
  
7.  Transportes AAS realizar copia de la respuesta FIN a través del adaptador de BizTalk para MQSeries en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].  
  
8.  Ubicación de recepción de la FRR recibe la respuesta y enruta el mensaje a través de la FRR canalización de recepción que procesa el token de correlación de la respuesta. A continuación, coloca la respuesta en el BizTalk MessageBox.  
  
9. La instancia de orquestación FRR recoge cualquier mensaje del cuadro de mensajes que tiene un token de correlación igual a la propiedad de Id. de mensaje de la copia del mensaje original.  
  
10. Si la respuesta indica que el mensaje original se ha procesado correctamente por AAS/SWIFT, la instancia de orquestación FRR establece la propiedad A4SWIFT_Failed que se promocionan de la copia del mensaje original en False y establece el BTS. El valor adecuado para la propiedad de operación.  
  
11. Si el mensaje original no se ha procesado correctamente por AAS/SWIFT, la instancia de orquestación FRR establece el BTS. El valor adecuado, para la propiedad de operación y, a continuación, se designa el mensaje para su reparación estableciendo A4SWIFT_Failed en True y establecer la propiedad A4SWIFT_FRRFailedReason promocionadas en el motivo del error.  
  
12. La instancia de orquestación FRR descarta los mensajes de respuesta y, a continuación, enruta la copia del mensaje original (con propiedades promocionadas que indica la respuesta) en el cuadro de mensajes.  
  
13. Uno de los puertos de envío FRR configurado para enrutar las respuestas en uno o varios controladores personalizados recoge la copia del mensaje original con las propiedades promocionadas.  
  
14. El controlador personalizado o controladores se suscribe a, recupera y procesa la copia del mensaje original según sea necesario para la aplicación de back-end.