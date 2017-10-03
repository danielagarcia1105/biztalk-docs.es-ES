---
title: "Parámetros de configuración para el envío y adaptadores de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters
- send adapters
- configuration parameters [adapters]
- receive adapters
ms.assetid: f24ca8ae-feaf-4e5f-b434-76bc3c1c8ccf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c33e49e82f9ebbf8856dd447989d7557558c0e4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-parameters-for-send-and-receive-adapters"></a>Parámetros de configuración para el envío y adaptadores de recepción
Esta sección proporciona los parámetros de configuración para envían y reciban los adaptadores de protocolo de nivel inferior mínimo (MLLP). Estos parámetros se dividen en dos tipos: bloquear caracteres y parámetros de conexión de red.  
  
 Establecer el bloque de caracteres de la configuración en las propiedades de transporte de MLLP para un puerto de envío mediante el tipo de transporte MLLP.  
  
 Puede definir los parámetros de conexión de red en las propiedades de transporte de MLLP para un puerto de envío o ubicación de recepción mediante el tipo de transporte MLLP. Para ello, abra la consola de administración de BizTalk Server, vaya a la carpeta puertos de envío o ubicaciones de recepción, según corresponda, haga clic en el puerto de envío específico o ubicación de recepción, haga clic en **propiedades**y, a continuación, haga clic en  **Configurar**.  
  
## <a name="block-characters"></a>Caracteres de bloque  
 Estos parámetros son caracteres especiales que deben incluir HL7 mensajes recibidos o enviados a través de adaptadores MLLP. Estos caracteres forman un bloque en el siguiente formato: \<SB >*DDD*\<EB >\<CR >, donde *DDD* los datos del mensaje, el acrónimo \<SB > es el carácter de bloque inicial, \<EB > es el carácter de bloque final, y \<CR > es el transporte devuelto.  
  
|Parámetro|Utilice|  
|---------------|---------|  
|**\<CR > retorno de carro**|Valor de bytes (en formato hexadecimal) que usa para el retorno de carro (el segundo contenedor de bytes tras el byte final). Opcional.|  
|**\<EB > caracteres de bloque final**|Valor de bytes que usa para el byte final (contenedor de finalizador de mensaje). ASCII \<FS >, por ejemplo, \<1C >.|  
|**\<SB > caracteres de bloque inicial**|Valor de bytes que use para el byte inicial (contenedor de encabezado de mensaje). ASCII \<VT >, por ejemplo, \<0b >.|  
  
## <a name="deliverymode"></a>DeliveryMode  
 Utilice el parámetro de modo de entrega para controlar si los archivos de la instancia se entregan de manera secuencial o fuera de la secuencia (en orden, fuera de servicio). Cada ubicación de recepción tiene su propio entrega para la instancia de secuencia de archivos.  
  
|Use|Para|  
|--------------|----------------|  
|Entrega ordenada|**Recepción de MLLP**:<br /><br /> Establecer el **entrega ordenada** propiedad **TRUE**, para especificar que se deben procesar los mensajes en un orden especificado. La entrega ordenada es importante para los mensajes que se deben procesar como un convoy, tal y como lo ha especificado un proceso empresarial de socio.<br /><br /> Si establece la **entrega ordenada** propiedad **FALSE** (el valor predeterminado), el puerto no fuerza la entrega ordenada.|  
  
## <a name="network-connection-parameters"></a>Parámetros de conexión de red  
 Use estos parámetros para establecer una conexión a través de la red, incluidos los comentarios, el nombre de la conexión, el nombre de host, Id. de puerto, tiempo de espera de recepción y envío de tiempo de espera.  
  
|Parámetro|Utilice|  
|---------------|---------|  
|**Comentarios**|Descripción de conexión. Opcional.|  
|**Nombre de conexión**|Nombre de conexión supervisada. Se recomienda que el nombre sea único. El nombre se incluye en el nombre de instancias de contador de rendimiento para esta conexión.|  
|**Host**|**Recepción de MLLP**:<br /><br /> Opcional. Especifica una interfaz local en el que se va a escuchar las conexiones entrantes. Por predeterminada escucha en todas las interfaces locales.<br /><br /> **Envío MLLP**:<br /><br /> Especifique el nombre NetBIOS o la dirección IP del equipo de línea de negocio (LOB) a la que desea conectarse.|  
|**Conexión persistente**|**Recepción de MLLP**:<br /><br /> Establecer el **conexión persistente** propiedad **FALSE** (el valor predeterminado), para cerrar la conexión después de que la conexión está inactiva durante el período de tiempo de espera. Establecer el **conexión persistente** propiedad **True**, para mantener abierta la conexión.<br /><br /> La siguiente tabla muestra los resultados de los valores posibles de la **conexión persistente** y **tiempo de espera de recepción** valores.<br /><br /> **FALSE**<br /><br /> - >0<br /><br /> -La conexión se cierra cuando se recibe un mensaje o transcurre el período de tiempo de espera.<br /><br /> **FALSE**<br /><br /> - 0<br /><br /> -Provoca una condición de error: "el valor de tiempo de espera de recepción no debe ser cero en el caso de conexión persistente FALSE".<br /><br /> **ES TRUE**<br /><br /> - 0<br /><br /> -La conexión nunca se interrumpe.<br /><br /> **ES TRUE**<br /><br /> - <>0<br /><br /> -Provoca una condición de error: "el valor de tiempo de espera de recepción debe ser cero en el caso de conexión persistente TRUE".<br /><br /> **Envío MLLP**:<br /><br /> Establecer el **conexión persistente** propiedad **FALSE**para cerrar la conexión si se recibe una respuesta dentro del período de tiempo de espera, o si transcurre el período de tiempo de espera. Establecer el **conexión persistente** propiedad **True** (el valor predeterminado), para mantener abierta la conexión.<br /><br /> La siguiente tabla muestra los resultados de los valores posibles de la **conexión persistente** y **tiempo de espera de recepción** valores.<br /><br /> **FALSE**<br /><br /> -O o > 0<br /><br /> -La conexión se cierra cuando se recibe una respuesta o transcurre el período de tiempo de espera.<br /><br /> **ES TRUE**<br /><br /> -0 ó <> 0<br /><br /> -La conexión nunca se interrumpe. El **tiempo de espera de envío** valor no afectan al estado de la conexión.<br /><br /> La siguiente tabla se muestra el estado de conexión de puerto de envío diferentes tipos cuando la configuración de la conexión persistente y respuesta de petición se cambian.<br /><br /> Unidireccional estático<br /><br /> -TRUE<br /><br /> -N<br /><br /> -Permanece abierto<br /><br /> Unidireccional estático<br /><br /> -TRUE<br /><br /> -Sí<br /><br /> -Permanece abierto<br /><br /> Unidireccional estático<br /><br /> -FALSE<br /><br /> -N<br /><br /> -Cierre<br /><br /> Unidireccional estático<br /><br /> -FALSE<br /><br /> -Sí<br /><br /> -Cierre<br /><br /> Respuesta de petición-respuesta estático<br /><br /> -TRUE<br /><br /> -N<br /><br /> -Permanece abierto<br /><br /> Respuesta de petición-respuesta estático<br /><br /> -TRUE<br /><br /> -Sí<br /><br /> -Permanece abierto<br /><br /> Respuesta de petición-respuesta estático<br /><br /> -FALSE<br /><br /> -N<br /><br /> -Cierre<br /><br /> Respuesta de petición-respuesta estático<br /><br /> -FALSE<br /><br /> -Sí<br /><br /> -Cierre|  
|**Puerto**|**Recepción de MLLP**:<br /><br /> Id. de puerto local para que escuche en.<br /><br /> **Envío MLLP**:<br /><br /> Id. de puerto remoto al que desea conectarse.|  
|**Tiempo de espera de envío**|**Envío MLLP**:<br /><br /> El tiempo máximo que esperará el adaptador de envío al enviar un mensaje, después del cual el socket emisor agotará el tiempo. Una vez concluido, el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se volverá a intentar el mensaje.<br /><br /> Además, en el caso de operación sincrónica del puerto de envío, el tiempo máximo para recibir la confirmación (ACK) de la unidad de negocio.|  
|**Tiempo de espera de recepción**|**Recepción de MLLP**:<br /><br /> El tiempo máximo que esperará el adaptador de recepción al recibir un mensaje, después del cual el socket de recepción agotará el tiempo. Una vez concluido, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se cerrará la conexión.<br /><br /> Además, en caso de funcionamiento sincrónico de la ubicación de recepción, el tiempo máximo para enviar la confirmación a la unidad de negocio.|  
|**Petición respuesta habilitado**|**Envío MLLP**:<br /><br /> Sí/no. Habilita la recepción de mensajes de confirmación en la misma conexión TCP.|  
|**Enviar ubicación URI para la confirmación de recepción**|**Envío MLLP**:<br /><br /> URI de la ubicación de recepción en la que reciben las confirmaciones en la misma conexión TCP se entregará a la base de datos de cuadro de mensajes.|  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes con codificación MLLP](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [Cómo procesa el adaptador de recepción de MLLP](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [Cómo procesa el adaptador MLLP envío](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [Cómo configurar un puerto de envío para recibir mensajes de confirmación](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)