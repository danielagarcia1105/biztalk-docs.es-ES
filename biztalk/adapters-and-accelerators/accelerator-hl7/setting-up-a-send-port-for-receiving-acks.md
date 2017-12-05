---
title: "Configurar un puerto de envío para recibir confirmaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: bb683e72-36e2-4a8f-acc2-8b37ed23746f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df0988a9edc2af81970237aad363315a778f821b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="setting-up-a-send-port-for-receiving-acks"></a>Cómo configurar un puerto de envío para recibir mensajes de confirmación
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) puede recibir confirmaciones (ACK) en un puerto de envío unidireccional. Cuando configura un nuevo puerto de envío unidireccional para recibir mensajes de confirmación en la misma conexión, debe asociar ese envío puerto de recepción del puerto con un unidireccional.  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]el programa de instalación crea un unidireccional puerto de recepción (denominado **TwoWayAckReceivePort**) y ubicación de recepción (denominado **TwoWayAckReceiveLocation**). La ubicación de recepción utiliza el tipo de transporte de protocolo de nivel inferior mínimo (MLLP), tiene un URI de "127.0.0.1:65535" y usa el **BTAHL72XReceivePipeline**. Se trata de la configuración necesaria para recibir y procesar una confirmación recibida un mensaje enviado por el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] en modo bidireccional del adaptador, de envío. Esta ubicación de recepción no se deberían eliminar o utiliza para otros fines. Nunca enviar datos a esta ubicación de recepción. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]permite que esta ubicación de recepción de forma predeterminada.  
  
 **TwoWayAckReceiveLocation**, que la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Asistente para la instalación crea, utiliza el **BizTalkServerApplication** como el controlador de recepción. Sin embargo, si decide crear un nuevo host y usarlo como el controlador de recepción para MLLP, a continuación, debe hacer lo siguiente para crear una nueva **TwoWayAckReceiveLocation**:  
  
1.  Crear un unidireccional puerto de recepción.  
  
2.  Crear un unidireccional MLLP ubicación de recepción.  
  
3.  Especifique los valores adecuados para las propiedades de transporte MLLP.  
  
4.  Especifique el controlador de recepción.  
  
5.  Habilitar la ubicación de recepción.  
  
### <a name="to-create-a-send-port-enabled-to-receive-an-ack-on-the-same-socket"></a>Para crear un puerto de envío habilitado para recibir una confirmación en el mismo socket  
  
1.  Abra la consola de administración de BizTalk y, a continuación, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **BizTalk Aplicación 1**. Haga clic en **puertos de envío**, elija Nuevo y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el **nombre** , escriba el nombre del puerto de envío.  
  
3.  En el **transporte** sección, para **tipo**, seleccione **MLLP**.  
  
4.  Haga clic en **configurar**.  
  
5.  En el cuadro de diálogo Propiedades de transporte de MLLP, escriba un nombre de conexión y el host (por ejemplo, **localhost**).  
  
6.  Para **de petición respuesta habilitado**, seleccione **Sí**. Deje **enviar recibir ubicación (URI) para la confirmación** en blanco y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Cuando sale de **ubicación de recepción envíe** en blanco, BTAHL7 entra en el URI para el valor predeterminado **TwoWayAckReceiveLocation**. Puede comprobar que después al hacer clic **Aceptar** en el paso 6, haciendo clic en **configuración** nuevo. El URI para **TwoWayAckReceiveLocation** (127.0.0.1:65535) se escribirán en **enviar recibir ubicación (URI) para la confirmación**.  
  
    > [!NOTE]
    >  Debe crear un puerto de envío para suscribirse a la confirmación recibida o la confirmación se verá en un estado suspendido, porque no se encontró ninguna suscripción. Para suscribirse a las Confirmaciones recibidas por el puerto de envío, utilice filtros, por ejemplo,  **BTS. MessageType == \<* MessageType*\>** y  **BTS. ReceivePortName == \<* puertoRecepción*\>**. Para confirmaciones estáticos, el tipo de mensaje es **StaticAck**.  
  
7.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Tipos de esquema de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [Segmento de confirmación del mensaje](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [Condiciones de error de confirmación](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)