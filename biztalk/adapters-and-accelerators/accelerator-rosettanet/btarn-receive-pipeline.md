---
title: "Canalización de recepción de BTARN | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTARN, receive pipelines
- RNMimeDecoder component
- ReceiveMessageNonRepudiate component
- RNDAsm component
- receive pipelines, message flow
- RNPartyRes component
- receive pipelines, BTARN
- MessageUpdater component
- messages, message flow
ms.assetid: 811f2a6a-ddd2-49cc-a00b-4c9d0110a0d1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db4bc69348cfb99b5e7cebb07c65e05a0513cd0e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="btarn-receive-pipeline"></a>Canalización de recepción de BTARN
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] realiza la recepción de mensajes de RosettaNet Implementation Framework (RNIF) con la canalización de RNIFReceive (RNIFReceive.btp). La canalización de recepción incluye los siguientes componentes:  
  
-   ReceiveMessageNonRepudiate  
  
-   RNMimeDecoder (preprocesador y descodificador MIME)  
  
-   RNDAsm (desensamblador XML)  
  
-   RNPartyRes (componente de resolución de entidades)  
  
-   MessageUpdater  
  
## <a name="receivemessagenonrepudiate"></a>ReceiveMessageNonRepudiate  
 Este componente almacena el mensaje recibido en la tabla MessageStorageIn. Este componente realiza el procesamiento sin repudio requerido por los estándares RNIF.  
  
## <a name="rnmimedecoder"></a>RNMimeDecoder  
 Este componente se basa en el nativo BizTalk Server preprocesador y descodificador MIME. RNMimeDecoder agrega la siguiente funcionalidad para el procesamiento de RNIF:  
  
-   Para RNIF 2.01, descifra el contenido del servicio y los datos adjuntos, si están presentes.  
  
-   Para RNIF 1.1, controla el encabezado de 8 bytes y el encabezado de firma desasociada al final de la carga.  
  
 Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] preprocesador y descodificador, consulte "Componente de canalización de descodificador MIME/SMIME" en la Ayuda de BizTalk Server.  
  
## <a name="rndasm"></a>RNDAsm  
 Este componente se basa en el Desensamblador de XML de servidor nativa de BizTalk. RNDAsm agrega la siguiente funcionalidad para el procesamiento de RNIF:  
  
-   Si un documento entrante tiene un encabezado de tipo de documento, este componente genera un espacio de nombres del mismo y mueve todos los nodos del documento entrante a ese espacio de nombres.  
  
-   Realiza la correlación de mensajes para determinar si un mensaje entrante es un duplicado y genera un mensaje de error si el mensaje es un duplicado.  
  
-   Almacena los datos adjuntos como partes adicionales del mensaje.  
  
-   Promociona las propiedades de mensaje.  
  
 Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Desensamblador, consulte "Componente de canalización de desensamblador XML" en la Ayuda de BizTalk Server.  
  
## <a name="rnpartyres"></a>RNPartyRes  
 Este componente se basa en el componente de resolución de entidades de BizTalk Server nativo. RNPartyRes agrega la siguiente funcionalidad para el procesamiento de RNIF:  
  
-   Si el mensaje entrante está firmado a una entidad de BizTalk se asigna el certificado del remitente. Si el mensaje entrante no está firmado y permite el acuerdo de socio comercial, este componente recupera la entidad del remitente del encabezado de entrega para RNIF 2.01 o el encabezado de servicio para RNIF 1.1.  
  
-   Valida que el remitente existe y que el remitente tiene un acuerdo de socio comercial con la organización principal.  
  
 Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] componente de resolución de terceros, consulte "Componente de canalización de resolución de entidad" en la Ayuda de BizTalk Server.  
  
## <a name="messageupdater"></a>MessageUpdater  
 Este componente agrega la siguiente funcionalidad para el procesamiento de RNIF:  
  
-   Actualiza la tabla MessageStorageIn con detalles sobre el código PIP, PIP versión, entidad de origen, entidad de destino e Id. de seguimiento de mensaje del mensaje de conexión que se almacenó el componente ReceiveMessageNonRepudiate.  
  
-   Si el PIP no requiere sin repudio, marca el registro para su eliminación, establecer `ToBePurged = True`.  
  
## <a name="message-flow"></a>Flujo de mensajes  
 El flujo de mensajes a través de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] recibir canalización es como sigue:  
  
1.  El adaptador de HTTP recibe un objeto de RNIF 1.1 o un mensaje de negocio de RNIF 2.01 a través de HTTP POST.  
  
2.  Si el adaptador recibe correctamente el mensaje, el adaptador extrae los mensajes de RosettaNet objeto o business y lo enruta a la canalización de recepción.  
  
3.  Si el mensaje de objeto o el negocio está firmado, el preprocesador y descodificador de MIME quita la firma.  
  
4.  Si la firma es válida, el Desensamblador lee el preámbulo.  
  
5.  Si el mensaje es un mensaje de acción y sin repudio es necesario (la **sin repudio del origen y del contenido** configuración de las opciones de configuración de proceso es `True`), el descodificador calcula y almacena el resumen.  
  
6.  El Desensamblador valida el preámbulo (con instrucciones de mensaje (MSG) y el esquema de preámbulo en las variables globales).  
  
7.  Para RNIF 2.01, el Desensamblador lee el encabezado de entrega y valida el encabezado mediante las instrucciones del mensaje y el esquema de encabezado de entrega en las variables globales.  
  
8.  Para RNIF 2.01, el Desensamblador extrae la información de socio en el encabezado de entrega y examina la firma para comprobar que pertenece al socio comercial.  
  
9. Para RNIF 2.01, si la carga se cifra, el decodificador descifra el contenedor de carga.  
  
10. El Desensamblador lee el encabezado de servicio y valida el encabezado mediante las instrucciones del mensaje y el esquema de encabezado de servicio en las variables globales.  
  
11. Para RNIF 1.1, el Desensamblador extrae la información del asociado de la cabecera de servicio y examina la firma para comprobar que pertenece al socio comercial.  
  
12. El Desensamblador comprueba si el socio está autorizado para el PIP. Si no es así, el Desensamblador vaya a responder a un HTTP POST con un mensaje de estado 403 de HTTP, si es necesario y enviar un error.  
  
13. Si el mensaje es un mensaje de acción firmado y **sin repudio del origen y del contenido** se establece en `True`, el componente ReceiveMessageNonRepudiate envía el mensaje original en la tabla MessageStorageIn.  
  
14. Si el mensaje es un mensaje de señal firmado y **sin repudio necesario** se establece en `True`, el componente ReceiveMessageNonRepudiate envía el mensaje de señal en la tabla MessageStorageIn.  
  
15. Si el mensaje se almacena en la tabla MessageStorageIn para sin repudio, el MessageUpdater actualiza la tabla MessageStorageIn con propiedades de la configuración del proceso del mensaje.  
  
16. Si el mensaje es un mensaje de acción que es un duplicado de un mensaje de acción procesados previamente, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] registrará un error.  
  
17. Para RNIF 2.01, el descodificador descifrará la carga si se cifra el mensaje de acción y no hay una correspondencia entre los requisitos de sincronización PIP y sincronización HTTP.  
  
18. El Desensamblador lee el contenido del servicio y lo valida con las instrucciones del mensaje y el esquema.  
  
19. Para RNIF 2.01, el Desensamblador comprueba que el manifiesto es válido y el identificador de contenido está presente.  
  
20. Para RNIF 2.01, el Desensamblador leerá los datos adjuntos.  
  
21. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]enruta los encabezados de RosettaNet, contenido del servicio y los datos adjuntos para el proceso público.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)