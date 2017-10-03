---
title: Propiedades relacionadas con BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [MQSeries adapters], properties
- CompleteMessage property [MQSeries adapters]
- SSOAffiliateApplication property [MQSeries adapters]
- Ordered property [MQSeries adapters]
- TransactionSupported property [MQSeries adapters]
- BizTalk_CorrelationID property [MQSeries adapters]
- SegmentationAllowed property [MQSeries adapters]
- DynamicReceive property [MQSeries adapters]
- MQSeries adapters, properties
- DataConversion property [MQSeries adapters]
ms.assetid: c27d7f9c-8198-4624-9952-054ba8ea1c7c
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f729e4ab359471e002029efc04c0c8ad21e0d99b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="properties-related-to-biztalk-server"></a>Propiedades relacionadas con BizTalk Server
El adaptador de MQSeries asigna valores a algunas propiedades de contexto que no están directamente relacionadas con MQSeries, pero que siguen siendo útiles en sus aplicaciones.  
  
 Todas las propiedades reciben valores durante el envío y recepción, excepto **BizTalk_CorrelationID**. El **BizTalk_CorrelationID** propiedad tiene un valor solo durante la recepción.  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|**BizTalk_CorrelationID**|string|Utilice esta propiedad para hacer que el servidor de MQSeries genere un identificador de correlación para su uso con el mensaje.<br /><br /> Para obtener más información, consulte [correlación de solicitud y respuesta utilizando mensajes](../core/correlating-messages-using-request-reply.md).|  
|**DataConversion**|string|Convierte el mensaje a la página de códigos ANSI de MQSeries Server para Windows. Durante el envío, si el formato de mensaje no es MQFMT_STRING, no habrá conversión.<br /><br /> Seleccione **Sí** para realizar esta conversión de Unicode a ANSI.<br /><br /> **Valor predeterminado:** n|  
|**Ordenada**|string|Define MQSeries para que ordene los mensajes según han sido recibidos o enviados a la cola de MQSeries.<br /><br /> La propiedad tiene conjuntos de valores distintos para el envío y la recepción. Para obtener información sobre estos valores, vea [Cómo configurar MQSeries adaptador ubicaciones de recepción y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).<br /><br /> **Valor predeterminado:** n|  
|**SegmentationAllowed**|string|Determina si MQSeries debe ensamblar los mensajes segmentados u obtener el mensaje tal como está. La propiedad tiene conjuntos de valores distintos para el envío y la recepción.<br /><br /> Cuando se reciben, use **No Action** para leer los mensajes de la cola de MQSeries sin habilitar la segmentación, usar **mensaje completo** para que MQSeries ensamble mensajes segmentados antes de pasar a la adaptador.<br /><br /> **Valor predeterminado:** ninguna acción<br /><br /> Cuando se envía, seleccione **Sí**, para que MQSeries coloque los mensajes segmentados en la cola.<br /><br /> **Valor predeterminado:** n|  
|**SSOAffiliateApplication**|string|Establece la aplicación afiliada de inicio de sesión único (SSO). Use el Id. de usuario y la contraseña de SSO para el **MQMD_UserIdentifier**y el **MQIIH_Authenticator** (o **MQCIH_Authenticator**) propiedad respectivamente.<br /><br /> Sólo se utiliza para el envío de mensajes.<br /><br /> **Valor predeterminado:** en blanco|  
|**CompleteMessage**|string|Determina si se debe o no recuperar un "mensaje completo" al recuperar los mensajes segmentados de la cola.<br /><br /> Establezca esta propiedad en **Sí** recuperar el "mensaje completo" para los mensajes segmentados de una cola.<br /><br /> **Valor predeterminado:** n|  
|**DynamicReceive**|string|Determina si se debe o no recibir dinámicamente los mensajes procedentes de una cola.<br /><br /> Establezca esta propiedad en **Sí** al recibir mensajes de una cola de forma dinámica. Esta característica se utiliza de forma conjunta con un puerto de envío de petición-respuesta.<br /><br /> Si especifica opciones de coincidencia (MessageID, CorrelationID o Groupid), sólo se recuperarán los mensajes que cumplan los criterios de búsqueda.|  
|**TransactionSupported**|string|El adaptador inicia una transacción del Coordinador de transacciones distribuidas de Microsoft (DTC) entre BizTalk Server y MQSeries Server. Cuando se establece en **n**, no hay ninguna garantía de entrega de mensajes.<br /><br /> **Valor predeterminado:** sí|  
|**WaitInterval**|string|Especifica el tiempo aproximado, expresado en segundos, que el sistema MQ espera a que llegue un mensaje adecuado. Si no llega ningún mensaje adecuado en ese tiempo, la llamada no se realiza correctamente. **Nota:** se puede establecer sólo en una orquestación. <br /><br /> **Valor predeterminado:** 3|  
  
## <a name="see-also"></a>Vea también  
 [Propiedades del adaptador de MQSeries](../core/mqseries-adapter-properties.md)   
 [Conversión de tipos de datos de propiedades](../core/data-type-conversion-of-properties.md)   
 [Propiedades de contexto de MQSeries](../core/mqseries-context-properties.md)