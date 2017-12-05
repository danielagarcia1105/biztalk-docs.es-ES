---
title: "Ayuda de interfaz de usuario de cuadro de cuadro de diálogo Propiedades de transporte MLLP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: btahl7.mllp.transportproperties
ms.assetid: 2a41aaeb-a91d-4d89-ac8a-1cfe48ab4cd4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b9856b7fbbac5dd9d6a4f809e369e586d95a31b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="mllp-transport-properties-dialog-box-ui-help"></a>Ayuda de interfaz de usuario de cuadro de cuadro de diálogo Propiedades de transporte MLLP
Usa el **propiedades de transporte de MLLP** cuadro de diálogo para configurar los parámetros de envío y recepción de adaptadores de protocolo de nivel inferior mínimo (MLLP). Puede definir los parámetros de conexión de red en las propiedades de transporte de MLLP para un puerto de envío o ubicación de recepción mediante el tipo de transporte MLLP.  
  
 Para obtener más información acerca de las propiedades MLLP, consulte [parámetros de configuración para los adaptadores de recepción y envío](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md).  
  
## <a name="uielement-list"></a>Lista de UIElement  
 En el **propiedades de transporte de MLLP** diálogo cuadro, realice lo siguiente:  
  
#### <a name="block-characters"></a>Caracteres de bloque  
 Parámetros de caracteres de bloque son caracteres especiales que deben incluir HL7 mensajes recibidos o enviados a través de adaptadores MLLP. Estos caracteres forman un bloque en el siguiente formato: \<SB\>*DDD*\<EB\>\<CR\>, donde *DDD* son las siglas para los datos del mensaje, \<SB\> es el carácter de bloque inicial, \<EB\> es el carácter de bloque final, y \<CR\> es devuelto al transporte.  
  
|Use|Para|  
|--------------|----------------|  
|**\<CR\> retorno de carro**|Valor de bytes (en formato hexadecimal) que usa para el retorno de carro (el segundo contenedor de bytes tras el byte final). Opcional.|  
|**\<EB\> caracteres de bloque final**|Valor de bytes que usa para el byte final (contenedor de finalizador de mensaje). ASCII \<FS\>, por ejemplo, \<1C\>.|  
|**\<SB\> caracteres de bloque inicial**|Valor de bytes que use para el byte inicial (contenedor de encabezado de mensaje). ASCII \<VT\>, por ejemplo, \<0b\>.|  
  
#### <a name="deliverymode"></a>DeliveryMode  
 Utilice el parámetro de modo de entrega para controlar si los archivos de la instancia se entregan de manera secuencial o fuera de la secuencia (en orden, fuera de servicio). Cada ubicación de recepción tiene su propio entrega para la instancia de secuencia de archivos.  
  
|Use|Para|  
|--------------|----------------|  
|Entrega ordenada|**Recepción de MLLP**:<br /><br /> Si establece la **entrega ordenada** propiedad **FALSE** (el valor predeterminado), no se entregará los archivos de la instancia de secuencia. Archivos más pequeños de instancia que se inserta a la cola después de archivos más grandes de instancia, se entregarán en primer lugar. Establecer el **entrega ordenada** propiedad **TRUE**para entregar los archivos de la instancia de secuencia.|  
  
#### <a name="network-connection-parameters"></a>Parámetros de conexión de red  
 Usar parámetros de conexión de red para establecer una conexión a través de la red, incluidos los comentarios, el nombre de la conexión, el nombre de host, Id. de puerto, tiempo de espera de recepción y tiempo de espera de envío.  
  
|Use|Para|  
|--------------|----------------|  
|**Comentarios**|Descripción de conexión. Opcional.|  
|**Nombre de conexión**|Nombre de conexión supervisada. Se recomienda que el nombre sea único. El nombre se incluye en el nombre de instancias de contador de rendimiento para esta conexión.|  
|**Host**|**Recepción de MLLP**:<br /><br /> Opcional. Especifica una interfaz local en el que se va a escuchar las conexiones entrantes. Por predeterminada escucha en todas las interfaces locales.<br /><br /> **Envío MLLP**:<br /><br /> Especifique el nombre NetBIOS o la dirección IP del equipo de línea de negocio (LOB) a la que desea conectarse.|  
|**Conexión persistente**|**Recepción de MLLP**:<br /><br /> Establecer el **conexión persistente** propiedad **FALSE** (el valor predeterminado), para cerrar la conexión después de que la conexión está inactiva durante el período de tiempo de espera. Establecer el **conexión persistente** propiedad **True**, para mantener abierta la conexión.<br /><br /> **Envío MLLP**:<br /><br /> Establecer el **conexión persistente** propiedad **FALSE**para cerrar la conexión si se recibe una respuesta dentro del período de tiempo de espera, o si transcurre el período de tiempo de espera. Establecer el **conexión persistente** propiedad **True** (el valor predeterminado), para mantener abierta la conexión.<br /><br /> Vea [conexión persistente y los valores de tiempo de espera de recepción](../../adapters-and-accelerators/accelerator-hl7/mllp-transport-properties-dialog-box-ui-help.md#persistentConnectionAndReceiveTimeout), y [tipos de puerto y el estado de la conexión](../../adapters-and-accelerators/accelerator-hl7/mllp-transport-properties-dialog-box-ui-help.md#portTypeConnectionStatus) para obtener más información.|  
|**Puerto**|**Recepción de MLLP**:<br /><br /> Id. de puerto local para que escuche en.<br /><br /> **Envío MLLP**:<br /><br /> Id. de puerto remoto al que desea conectarse.|  
|**Tiempo de espera de envío**|**Envío MLLP**:<br /><br /> El tiempo máximo que esperará el adaptador de envío al enviar un mensaje, después del cual el socket emisor agotará el tiempo. Una vez concluido, el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se volverá a intentar el mensaje.<br /><br /> Además, en el caso de operación sincrónica del puerto de envío, el tiempo máximo para recibir la confirmación (ACK) de la unidad de negocio.|  
|**Tiempo de espera de recepción**|**Recepción de MLLP**:<br /><br /> El tiempo máximo que esperará el adaptador de recepción al recibir un mensaje, después del cual el socket de recepción agotará el tiempo. Una vez concluido, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se cerrará la conexión.<br /><br /> Además, en caso de funcionamiento sincrónico de la ubicación de recepción, el tiempo máximo para enviar la confirmación a la unidad de negocio.|  
|**Petición respuesta habilitado**|**Envío MLLP**:<br /><br /> Sí/no. Habilita la recepción de mensajes de confirmación en la misma conexión TCP.|  
|**Enviar ubicación URI para la confirmación de recepción**|**Envío MLLP**:<br /><br /> URI de la ubicación de recepción en la que reciben las confirmaciones en la misma conexión TCP se entregará a la base de datos de cuadro de mensajes.|  
  
#####  <a name="persistentConnectionAndReceiveTimeout"></a>Conexión persistente y recibir valores de tiempo de espera  
 Para **MLLP recibir**, la siguiente tabla muestra los resultados de los valores posibles de la **conexión persistente** y **tiempo de espera de recepción** valores.  
  
|**Conexión persistente**|**Tiempo de espera de recepción**|Resultado|  
|-------------------------------|-------------------------|------------|  
|**FALSE**|>0|La conexión se cierra cuando se recibe un mensaje o transcurre el período de tiempo de espera.|  
|**FALSE**|0|Hace que una condición de error: "el valor de tiempo de espera de recepción no debe ser cero en el caso de conexión persistente FALSE".|  
|**ES TRUE**|0|Interrumpe la conexión nunca.|  
|**ES TRUE**|<>0|Hace que una condición de error: "el valor de tiempo de espera de recepción debe ser cero en el caso de conexión persistente TRUE".|  
  
 Para **MLLP enviar**, la siguiente tabla muestra los resultados de los valores posibles de la **conexión persistente** y **tiempo de espera de recepción** valores.  
  
|**Conexión persistente**|**Tiempo de espera de envío**|Resultado|  
|-------------------------------|----------------------|------------|  
|**FALSE**|0 o > 0|La conexión se cierra cuando se recibe una respuesta o transcurre el período de tiempo de espera.|  
|**ES TRUE**|0 o <> 0|Interrumpe la conexión nunca. El **tiempo de espera de envío** valor no afectan al estado de la conexión.|  
  
#####  <a name="portTypeConnectionStatus"></a>Tipos de puerto y el estado de conexión  
 La siguiente tabla se muestra el estado de conexión de puerto de envío diferentes tipos cuando la configuración de la conexión persistente y respuesta de petición se cambian.  
  
|Tipo de puerto de envío|Conexión persistente|Petición respuesta|Estado de la conexión|  
|--------------------|---------------------------|----------------------|-----------------------|  
|Unidireccional estático|TRUE|No|Permanece abierto|  
|Unidireccional estático|TRUE|Sí|Permanece abierto|  
|Unidireccional estático|FALSE|No|Cerrado|  
|Unidireccional estático|FALSE|Sí|Cerrado|  
|Respuesta de petición-respuesta estático|FALSE|Sí|Permanece abierto|  
|Respuesta de petición-respuesta estático|TRUE|Sí|Permanece abierto|  
|Respuesta de petición-respuesta estático|FALSE|No|Cerrado|  
|Respuesta de petición-respuesta estático|FALSE|Sí|Cerrado|  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes con codificación MLLP](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [Cómo procesa el adaptador de recepción de MLLP](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [Cómo procesa el adaptador MLLP envío](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [Configurar un puerto de envío para recibir confirmaciones](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)