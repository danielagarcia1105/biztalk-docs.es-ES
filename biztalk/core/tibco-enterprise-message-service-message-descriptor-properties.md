---
title: Propiedades de Descriptor de mensajes TIBCO Enterprise Message Service | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message descriptor properties
ms.assetid: fc164c12-6dc3-4b74-9aa9-024e18faf80a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80c75875c44c4d082089fc9394fef390a0f91571
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a>Propiedades del descriptor de mensajes de TIBCO Enterprise Message Service
En la tabla siguiente se muestra el conjunto completo de propiedades disponibles del descriptor de mensajes (estructura TibcoEMSMD), así como los valores y tipos correspondientes.  
  
|Nombre|Tipo|Value|Notas|  
|----------|----------|-----------|-----------|  
|TibcoEMS .CorrelationID|string|||  
|TibcoEMS .DelieveryMode|string|Uno PERSISTENT o NON-PERSISTENT||  
|TibcoEMS .Destination|string||Solo lectura|  
|TibcoEMS .Expiration|long|||  
|TibcoEMS .MessageID|string||Solo lectura|  
|TibcoEMS .Priority|integer|De 0 a 9||  
|TibcoEMS .Redelivered|boolean||Solo lectura|  
|TibcoEMS .ReplyTo|string|Similar al destino||  
|TibcoEMS .Timestamp|long||Solo lectura|  
  
 Las propiedades de solo lectura son aquellas que TIBCO Enterprise Message Service establece cuando el mensaje se entrega al adaptador de Microsoft BizTalk para TIBCO EMS. Cambiar el valor, aunque es posible en la expresión de la forma de asignación del mensaje, no afecta al mensaje.  
  
 Para otras propiedades que se deben mover del mensaje de EMS al mensaje de BizTalk Server, se debe crear un DLL de propiedades y usarlo en el proyecto.  
  
 El siguiente ejemplo de esquema de propiedades permite que la orquestación use la propiedad de mensaje `JMSXDeliveryCount`.  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://schemas.microsoft.com/BizTalk/TibcoEMS-properties" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
        <xs:appinfo>  
            <b:schemaInfo schema_type="property" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="JMSXDeliveryCount" type="xs:long">  
        <xs:annotation>  
            <xs:appinfo>  
                <b:fieldInfo propertyGuid="f62f1a4b-a528-45fb-b1f8-bd880e9f46db" />  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
</xs:schema>   
```  
  
 Asegúrese de que se usa el espacio de nombres de destino; únicamente la propiedades que usan este espacio de nombres se copian al mensaje de BizTalk Server o de EMS. Consulte la documentación de BizTalk Server para obtener más información acerca de las propiedades de contexto del mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Propiedades de contexto de mensaje](../core/message-context-properties2.md)