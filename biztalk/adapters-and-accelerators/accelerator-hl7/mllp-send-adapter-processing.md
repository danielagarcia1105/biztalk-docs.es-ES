---
title: Procesamiento de adaptador de envío de MLLP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- send adapters
- MLLP adapters, send adapters
ms.assetid: b8e47c7f-4a69-4f0c-86b4-26ed9c70613c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 396905f9b4cc8c1ebb0dbd1d3051b6f40566662a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971917"
---
# <a name="mllp-send-adapter-processing"></a>Procesamiento de adaptadores de envío MLLP
El adaptador de envío del protocolo de nivel inferior mínimo (MLLP) admite los modos de transporte unidireccionales y bidireccionales en las siguientes configuraciones:  
  
-   Adaptador de envío de petición-respuesta bidireccional  
  
-   Adaptador de envío unidireccional configurada para recibir la confirmación (ACK)  
  
-   Adaptador de envío unidireccional configurado para ningún mensaje de retorno  
  
## <a name="two-way-solicit-response-send-mllp-adapter"></a>Adaptador de MLLP de envío de petición-respuesta bidireccional  
 Utilice este adaptador en un escenario de extremo a otro sincrónico es true. Por lo tanto, sólo puede utilizar este adaptador con la entidad de un destino. El adaptador de envío continuamente mantendrá una conexión abierta en la parte remota (URL) hasta que enruta un mensaje de vuelta a la respuesta de solicitud de puerto de recepción. Consulte el siguiente diagrama de la arquitectura de procesamiento de solicitudes de respuesta o petición respuesta.  
  
 Cuando se usa este adaptador, puede dirigir el sistema para devolver una confirmación o un mensaje de respuesta a la aplicación de línea de negocio. Puede hacerlo con la confirmación de la ruta a la canalización de envío en la configuración de puerto de recepción de solicitud-respuesta en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración. Seleccione esta propiedad para devolver una confirmación o anule la selección para devolver una reunión de respuesta.  
  
 Una vez que un puerto de envío con este adaptador ha enviado correctamente el mensaje original, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] elimina ese mensaje. La canalización de recepción asociada con este puerto de envío no generará una confirmación. BizTalk reenvía la respuesta de consulta a la aplicación de origen, independientemente del valor del campo MSA2 de esa respuesta.  
  
## <a name="one-way-send-mllp-adapter-configured-to-receive-acks"></a>Adaptador de envío unidireccional MLLP configurado para recibir mensajes de confirmación  
 Este adaptador recibe mensajes de confirmación en la misma conexión de socket que se envía el mensaje original y entrega los mensajes de confirmación a la ubicación de recepción. El adaptador de envío continuamente mantiene una conexión abierta en la parte remota (URL), incluso si no hay mensajes están esperando [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enviarlos a él. Si varios puertos llevan a la misma entidad remota, el adaptador de envío mantiene una conexión para cada puerto de envío.  
  
 Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) el programa de instalación instala una predeterminada ubicación de recepción, TwoWayAckReceiveLocation. Puede usar esta ubicación de recepción con el adaptador de envío MLLP para recibir confirmaciones. Esta configuración del puerto de envío con este adaptador, deberá asociar el puerto de envío en una ubicación de recepción.  
  
 Utilice este puerto de envío si se ha configurado para recibir un mensaje de respuesta con un campo de MSA, o para admitir varios destinos. El adaptador de petición-respuesta bidireccional no funciona con el campo MSA o con varios destinos.  
  
### <a name="acknowledgments-received-by-the-one-way-mllp-send-adapter"></a>Las confirmaciones recibidas por el MLLP unidireccional del adaptador de envío  
 Cuando recibe un adaptador de envío MLLP unidireccional configurado para confirmaciones, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elimina el mensaje original de la base de datos de cuadro de mensajes, lo reintenta o se suspende, según el tipo de la confirmación. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analiza la confirmación en dos fases:  
  
- La primera fase se realiza en el adaptador de envío donde [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analiza el campo MSA1 para determinar el tipo de la confirmación.  
  
- En la segunda fase, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] realiza un análisis completo de la confirmación y, a continuación, envía la confirmación a la base de datos de cuadro de mensajes.  
  
  Configurar la confirmación que espera el adaptador de envío bidireccional en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.  
  
  La siguiente tabla muestra las confirmaciones que pueda recibir un adaptador de envío MLLP y la acción resultante en el mensaje original.  
  
|Se ha recibido confirmación|Acción del mensaje original|  
|------------------|------------------------------------|  
|Acepte la confirmación o acepte la aplicación|Eliminar de la base de datos de cuadro de mensajes|  
|Confirmación o aplicación, Reject ACK o confirmación no válido|Suspender|  
|Error de confirmación/aplicación|Vuelva a intentarlo o mover a la copia de seguridad de transporte/Suspend|  
|Confirmación estático correcto|Eliminar de la base de datos de cuadro de mensajes|  
|Error de confirmación estático|Suspender|  
  
 La siguiente tabla muestra las condiciones de confirmación que no son válidas.  
  
|Instancia|Condición|  
|--------------|---------------|  
|HL7 (Original, mejorado, diferido)|1.  No contiene XML.<br />2.  No tiene la estructura, por lo que no se puede recuperar el campo MSA1; o bien, el campo MSA1 no contiene uno de los valores permitidos (entidad de certificación, AA, CR, AR, CE, AE).|  
|Estático|No coincide con uno de los valores permitidos para el éxito o se producirá un error en la confirmación.|  
|Contiene el XML|Se trata como una confirmación de aceptación (independientemente del contenido) y eliminar el mensaje original.|  
  
### <a name="error-conditions"></a>Condiciones de error  
 Puede ocurrir lo siguiente cuando hay una condición de error o de inactividad:  
  
- Si se produce un error en el mensaje saliente en la serialización, el adaptador de envío no enviará el mensaje, a menos que sea un lote de mensajes que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] transmite por secuencias. Si es así, y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] detecta un error de serialización a la mitad el mensaje, el adaptador no enviará EB/CR desde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] no se ha enviado el mensaje completo. La canalización registra un error y el adaptador intente volver a enviar el mensaje por lotes.  
  
- Si se produce un error en una operación de envío, el adaptador intenta volver a enviar el mensaje, hasta el número de reintentos especificado en las opciones de configuración de puerto de envío. Después de agotar los reintentos, el mensaje se mueve al transporte de reserva, si existe alguno. Si todo lo demás falla, se suspende el mensaje. El mensaje suspendido tendrá el formato (XML) original.  
  
  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede generar los eventos para describir las condiciones de error siguientes:  
  
|        Evento        |  Id.  |                                                                                                                                   Condición de error                                                                                                                                   |
|---------------------|------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ErrorSendingMessage | 8450 | No se pudo enviar un mensaje a la parte remota. Los motivos más habituales son errores de red o los tiempos de espera. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] es posible que informan de este error si se produce un error en la canalización de envío al serializar un mensaje grande. |
|  ErrorReceivingAck  | 8451 |                                                                                                       No se pudo recibir una confirmación, debido a un error de red o el tiempo de espera.                                                                                                       |
|   ErrorConnecting   | 8453 |                                                    No se pudo establecer la conexión TCP para la parte remota: no se pudo resolver el nombre de host o la parte remota no está escuchando en el puerto o está rechazando las conexiones.                                                     |
  
> [!NOTE]
>  La configuración de la entidad de destino (en MSH5 del mensaje original) determina si [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] espera un HL7 o confirmación de estático. En el caso de un error de coincidencia, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] trata la confirmación como no válido.  
  
 Después de que el MLLP envíe una confirmación de los procesos de adaptador, la confirmación se entrega a la ubicación de recepción como un mensaje por sí mismo. El Desensamblador realiza un análisis completo de la confirmación, lo que puede provocar errores que notifica la canalización de recepción de análisis o la confirmación ha suspendido.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes con codificación MLLP](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [Parámetros de configuración de envío y recepción de adaptadores](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [Procesamiento de adaptadores de recepción de MLLP](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [Configurar un puerto de envío para recibir confirmaciones](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)