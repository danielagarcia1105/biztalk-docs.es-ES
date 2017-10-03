---
title: Propiedades y esquema de BizTalk Framework | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8986e4a7-0c0a-415f-8a74-4fca71d3f1b5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 992f0fb9c66ee00cf425609db4231a57bf5782c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-framework-schema-and-properties"></a>Propiedades y esquema de BizTalk Framework
El **http://schemas.microsoft.com/BizTalk/2003/btf2-properties** espacio de nombres contiene propiedades que puede utilizar para establecer propiedades de contexto de mensajes y partes para el componente de canalización de desensamblador de BizTalk Framework. El componente de canalización de desensamblador de BizTalk Framework utiliza estas propiedades para generar los encabezados apropiados en el mensaje que se crea. La tabla siguiente describe las propiedades de BizTalk Framework.  

## <a name="properties-list"></a>Lista Propiedades  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|**IsReliable**|xs:boolean|Indica si el mensaje de BizTalk Framework tiene que volver a enviarse hasta que se reciba una confirmación de un destino. Los componentes de BizTalk Framework establecen internamente esta propiedad y la utiliza el motor. No cambie el valor de esta propiedad en el código.|  
|**PassAckThrough**|xs:boolean|Indica si se debe mandar un mensaje de confirmación mediante el componente de canalización de desensamblador de BizTalk Framework en vez de consumirse.|  
|**eps_to_address**|xs:string|Especifica la dirección de destino.|  
|**eps_to_address_type**|xs:string|Especifica el tipo de dirección de destino.|  
|**eps_from_address**|xs:string|Especifica la dirección de origen.|  
|**eps_from_address_type**|xs:string|Especifica el tipo de dirección de origen.|  
|**prop_identity**|xs:string|Referencia de URI que identifica de forma exclusiva el documento de BizTalk Framework a efectos de registro, seguimiento, control de errores u otros requisitos de correlación y procesamiento de documentos.|  
|**prop_sentAt**|xs:string|Marca de hora de envío del documento de BizTalk Framework.|  
|**prop_topic**|xs:string|Referencia de URI que identifica de forma exclusiva el propósito general del documento de BizTalk Framework.|  
|**svc_deliveryRctRqt_sendTo_address**|xs:string|Especifica la dirección a la que se enviará la notificación de entrega del documento de BizTalk Framework.|  
|**svc_deliveryRctRqt_sendTo_address_type**|xs:string|Especifica el tipo de dirección a la que se enviará la notificación de entrega del documento de BizTalk Framework.|  
|**svc_deliveryRctRqt_sendBy**|xs:dateTime|Especifica el tiempo (en minutos) en el que se deberá haber recibido la notificación de entrega del documento de BizTalk Framework.|  
|**svc_commitmentRctRqt_sendTo_address**|xs:string|Especifica la dirección a la se debe enviar la notificación de la decisión del destinatario sobre el procesamiento de la solicitud del remitente.|  
|**svc_commitmentRctRqt_sendTo_address_type**|xs:string|Especifica el tipo de dirección a la se debe enviar la notificación de la decisión del destinatario sobre el procesamiento de la solicitud del remitente.|  
|**svc_commitmentRctRqt_sendBy**|xs:dateTime|Especifica el tiempo (en minutos) en el que el remitente deberá haber recibido el acuse de recibo del documento de BizTalk Framework.|  
|**prc_type**|xs:string|Proporciona una referencia de URI que especifica el tipo de proceso empresarial implicado en el procesamiento de los mensajes de BizTalk Framework.|  
|**prc_instance**|xs:string|Proporciona una referencia de URI que identifica de forma exclusiva una instancia específica del proceso empresarial con la que está asociado el documento de BizTalk Framework.|  
|**deliveryRct_receivedAt**|xs:dateTime|Especifica la marca de hora de recepción en que se confirma la recepción del documento. La marca de hora de recepción puede reflejar tanto la hora a la que se recibió la primera copia como la hora a la que se recibió la copia cuya recepción se está confirmando.|  
|**deliveryRct_identity**|xs:string|Especifica una identidad del documento de BizTalk Framework cuya notificación de entrega se ha recibido.|  
|**commitmentRct_identity**|xs:string|Especifica la identidad de un documento de BizTalk Framework cuyo acuse de recibo se ha recibido.|  
|**commitmentRct_decidedAt**|xs:string|Especifica la marca de hora de la decisión de procesamiento en que se confirma la recepción del documento.|  
|**commitmentRct_decision**|xs:string|Especifica la decisión real, con valores posibles positivos o negativos.|  
|**commitmentRct_commitmentCode**|xs:QName|Especifica el nombre completo (en XSD) que establece un estado más específico en relación con la decisión de procesamiento.|  
  
## <a name="see-also"></a>Vea también  
-  **Propiedades de contexto del mensaje**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
-  [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)