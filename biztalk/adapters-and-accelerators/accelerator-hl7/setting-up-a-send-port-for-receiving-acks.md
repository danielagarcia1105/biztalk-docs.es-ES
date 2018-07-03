---
title: Configurar un puerto de envío para recibir confirmaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: bb683e72-36e2-4a8f-acc2-8b37ed23746f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f70be6d66d0ba8aa3385760bfc17b4b19f50351a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984749"
---
# <a name="setting-up-a-send-port-for-receiving-acks"></a>Configurar un puerto de envío para recibir confirmaciones
Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) puede recibir confirmaciones (ACK) en un puerto de envío unidireccional. Al configurar un puerto de envío unidireccional para recibir confirmaciones en la misma conexión, debe asociar ese envío Puerto unidireccional con el puerto de recepción.  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] programa de instalación crea un unidireccional puerto de recepción (llamado **TwoWayAckReceivePort**) y la ubicación de recepción (llamado **TwoWayAckReceiveLocation**). La ubicación de recepción utiliza el tipo de transporte de protocolo de nivel inferior mínimo (MLLP), tiene un identificador URI de "127.0.0.1:65535" y utiliza el **BTAHL72XReceivePipeline**. Se trata de la configuración necesaria para la recepción y procesamiento de confirmación recibida un mensaje enviado por el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] enviar adaptador, en modo bidireccional. Esta ubicación de recepción no deberían eliminarse o usar para otros fines. Nunca se envían datos a esta ubicación de recepción. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] permite que esta ubicación de recepción de forma predeterminada.  
  
 **TwoWayAckReceiveLocation**, que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Asistente para configuración crea, utiliza el **BizTalkServerApplication** como el controlador de recepción. Sin embargo, si decide crear un nuevo host y usarlo como el controlador de recepción de MLLP, a continuación, debe hacer lo siguiente para crear un nuevo **TwoWayAckReceiveLocation**:  
  
1.  Crear un sentido puerto de recepción.  
  
2.  Crear un sentido ubicación de recepción de MLLP.  
  
3.  Especifique los valores adecuados para las propiedades de transporte MLLP.  
  
4.  Especifique el que controlador de recepción adecuado.  
  
5.  Habilitar la ubicación de recepción.  
  
### <a name="to-create-a-send-port-enabled-to-receive-an-ack-on-the-same-socket"></a>Para crear un puerto de envío habilitado para recibir una confirmación en el mismo socket  
  
1.  Abra la consola de administración de BizTalk y, a continuación, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **BizTalk Aplicación 1**. Haga clic en **puertos de envío**, elija Nuevo y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el **nombre** , escriba el nombre del puerto de envío.  
  
3.  En el **transporte** sección, para **tipo**, seleccione **MLLP**.  
  
4.  Haga clic en **configurar**.  
  
5.  En el cuadro de diálogo Propiedades de transporte de MLLP, escriba un nombre de la conexión y un host (por ejemplo, **localhost**).  
  
6.  Para **de petición respuesta habilitado**, seleccione **Sí**. Deje **enviar recibir ubicación (URI) para la confirmación** en blanco y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si se deja **ubicación de recepción envíe** en blanco, BTAHL7 entra en el URI para el valor predeterminado **TwoWayAckReceiveLocation**. Puede comprobar que una vez al hacer clic **Aceptar** en el paso 6, al hacer clic en **configuración** nuevo. El URI para **TwoWayAckReceiveLocation** (127.0.0.1:65535) se escribirán en **enviar recibir ubicación (URI) para la confirmación**.  
  
    > [!NOTE]
    >  Debe crear un puerto de envío para suscribirse a ha recibido la confirmación o la confirmación se verán en un estado suspendido, porque no se encontraron suscripciones. Para suscribirse a las Confirmaciones recibidas por el puerto de envío, use los filtros, por ejemplo, **BTS. MessageType == \< *MessageType* \>**  y **BTS. ReceivePortName == \< *puertoRecepción*\>**. Para confirmaciones estáticas, es el tipo de mensaje **StaticAck**.  
  
7.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Tipos de esquema de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [Segmento de confirmación del mensaje](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [Condiciones de error de confirmación](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)