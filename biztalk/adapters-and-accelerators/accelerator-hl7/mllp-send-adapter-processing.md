---
title: Cómo procesa el adaptador de envío de MLLP | Documentos de Microsoft
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
ms.openlocfilehash: 1644d699014f23ce90568034c4bd90f6f0c7b099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207532"
---
# <a name="mllp-send-adapter-processing"></a>Cómo procesa el adaptador MLLP envío
El adaptador de envío del protocolo de nivel inferior mínimo (MLLP) admite los modos de transporte unidireccionales y bidireccionales en las siguientes configuraciones:  
  
-   Adaptador de envío de petición-respuesta bidireccional  
  
-   Adaptador de envío unidireccional configurado para recibir confirmaciones (ACK)  
  
-   Adaptador de envío unidireccional configurado para ningún mensaje devuelto  
  
## <a name="two-way-solicit-response-send-mllp-adapter"></a>Adaptador MLLP de envío de petición-respuesta bidireccional  
 Utilizar este adaptador en un escenario sincrónico de extremo a true. Por lo tanto, sólo puede utilizar este adaptador con parte de un destino. El adaptador de envío continuamente mantendrá una conexión abierta con la parte remota (URL) hasta que enruta un mensaje de vuelta a la respuesta de solicitud de puerto de recepción. Consulte el diagrama siguiente para la arquitectura de procesamiento de la respuesta de solicitud respuesta o petición.  
  
 Cuando se usa este adaptador, puede dirigir el sistema para devolver una confirmación o un mensaje de respuesta a la aplicación de línea de negocio. Hace esto con la confirmación de la ruta a la canalización de envío en la configuración de puerto de recepción de solicitud-respuesta en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración del explorador. Selecciona esta propiedad para devolver una confirmación o anule la selección para devolver una reunión de respuesta.  
  
 Una vez que un puerto de envío con este adaptador ha enviado correctamente el mensaje original, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] elimina ese mensaje. La canalización de recepción asociada con este puerto de envío no generará una confirmación. BizTalk reenvía la respuesta de consulta a la aplicación de origen sin tener en cuenta el valor del campo MSA2 de esa respuesta.  
  
## <a name="one-way-send-mllp-adapter-configured-to-receive-acks"></a>Adaptador de envío unidireccional MLLP configurado para recibir mensajes de confirmación  
 Este adaptador recibe mensajes de confirmación en la misma conexión de socket que se envía el mensaje original y entrega los mensajes de confirmación a la ubicación de recepción. El adaptador de envío continuamente mantiene una conexión abierta con la parte remota (URL), incluso si no está esperando recibir ningún mensaje [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enviarlos a él. Si varios puertos que apuntan a la misma entidad remota, el adaptador de envío mantiene una conexión para cada puerto de envío.  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) el programa de instalación instala una predeterminada ubicación de recepción, TwoWayAckReceiveLocation. Puede utilizar esta ubicación de recepción con el adaptador de envío MLLP para recibir los mensajes de confirmación. Esta configuración del puerto de envío con este adaptador requiere que asocie una ubicación de recepción con el puerto de envío.  
  
 Utilice este puerto de envío si se configuran para recibir un mensaje de respuesta con un campo MSA, o a varios destinos. El adaptador de petición-respuesta bidireccional no funciona con el campo MSA o con varios destinos.  
  
### <a name="acknowledgments-received-by-the-one-way-mllp-send-adapter"></a>Adaptador de envío de confirmaciones recibidas por el MLLP unidireccional  
 Cuando un adaptador de envío unidireccional de MLLP configurado para confirmaciones recibe uno, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elimina el mensaje original de la base de datos de cuadro de mensajes, lo reintenta o se suspende, según el tipo de la confirmación. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]analiza la confirmación en dos fases:  
  
-   La primera fase se realiza en el adaptador de envío donde [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analiza el campo MSA1 para determinar el tipo de la confirmación.  
  
-   En la segunda fase, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] lleva a cabo un análisis completo de la confirmación y, a continuación, envía la confirmación para la base de datos de cuadro de mensajes.  
  
 Configurar la confirmación que espera el adaptador de envío bidireccional en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración.  
  
 En la tabla siguiente muestra los mensajes de confirmación de que un adaptador de envío MLLP puede recibir y la acción resultante en el mensaje original.  
  
|Ha recibido ACK|Acción en el mensaje original|  
|------------------|------------------------------------|  
|Aceptar confirmación o Aceptar de aplicación|Eliminar de la base de datos de cuadro de mensajes|  
|Confirmación o aplicación, confirmación de rechazo o confirmación no válido|Suspender|  
|Error de confirmación/aplicación|Vuelva a intentar o mover a la copia de seguridad de transporte/Suspend|  
|Confirmación estático correcto|Eliminar de la base de datos de cuadro de mensajes|  
|Error de confirmación estático|Suspender|  
  
 La siguiente tabla muestra las condiciones de confirmación que no son válidas.  
  
|Instancia|Condición|  
|--------------|---------------|  
|HL7 (Original, mejorado, diferida)|1.  No contiene XML.<br />2.  No tiene la estructura por lo que no se puede recuperar el campo MSA1; o bien, el campo MSA1 no contiene uno de los valores permitidos (entidad de certificación, AA, CR, AR, CE, AE).|  
|Estático|No coincide con uno de los valores permitidos para el éxito o se producirá un error de confirmación.|  
|Contiene código XML|Trata como una confirmación de aceptación (independientemente del contenido) y eliminar el mensaje original.|  
  
### <a name="error-conditions"></a>Condiciones de error  
 Puede ocurrir lo siguiente cuando se produce una condición de error o de inactividad:  
  
-   Si se produce un error en el mensaje saliente en la serialización, el adaptador de envío no enviará el mensaje, a menos que sea un lote de mensajes que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] transmite por secuencias. Si es así, y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] detecta un error de serialización medio camino en el mensaje, el adaptador no enviará EB/CR desde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] no se ha enviado el mensaje completo. La canalización registra un error y el adaptador intente volver a enviar el mensaje por lotes.  
  
-   Si se produce un error en una operación de envío, el adaptador intenta enviar el mensaje nuevo, hasta el número de reintentos especificado en las opciones de configuración de puerto de envío. Después de agotar los reintentos, el mensaje se mueve al transporte de reserva, si existe alguno. Si todo lo demás falla, se suspende el mensaje. El mensaje suspendido será el original () en forma de XML.  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]puede generar los siguientes eventos para describir las condiciones de error:  
  
|Evento|ID|Condición de error|  
|-----------|--------|---------------------|  
|ErrorSendingMessage|8450|No se pudo enviar un mensaje a la parte remota. Los motivos más habituales son errores de red o tiempos de espera. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]puede informar de este error si se produce un error en la canalización de envío mientras se serializa un mensaje grande.|  
|ErrorReceivingAck|8451|No se pudo recibir una confirmación, debido a error de red o el tiempo de espera.|  
|ErrorConnecting|8453|No se puede establecer un TCP conectarse a la parte remota: no se ha podido resolver el nombre de host o la parte remota no está escuchando en el puerto o está rechazando las conexiones.|  
  
> [!NOTE]
>  La configuración de la entidad de destino (en MSH5 del mensaje original) determina si [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] espera un HL7 o estático confirmación. En el caso de un error de coincidencia, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] trata la confirmación como no válido.  
  
 Una vez el MLLP envíe una confirmación de procesos de adaptador, la confirmación se envía a la ubicación de recepción como un mensaje por sí mismo. El Desensamblador no realiza un análisis completo de la confirmación, lo que puede conllevar la canalización de recepción que informan de errores de análisis o la confirmación está suspendiendo.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes con codificación MLLP](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [Parámetros de configuración para el envío y adaptadores de recepción](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [Cómo procesa el adaptador de recepción de MLLP](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [Cómo configurar un puerto de envío para recibir mensajes de confirmación](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)