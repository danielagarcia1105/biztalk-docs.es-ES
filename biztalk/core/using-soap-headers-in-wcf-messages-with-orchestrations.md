---
title: Usar encabezados SOAP en mensajes WCF con orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- WCF services, orchestrations
- WCF services, SOAP headers
ms.assetid: 31c01e35-a2a6-4ea9-bdf4-6d4311268dbe
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e8248ec62e75a058566eefef1942e1f82061dbb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="using-soap-headers-in-wcf-messages-with-orchestrations"></a>Usar encabezados SOAP en mensajes WCF con orquestaciones
Para enviar los encabezados SOAP personalizados con mensajes WCF salientes en orquestaciones, use la propiedad de contexto **WCF. OutboundCustomHeaders**. Los adaptadores de WCF envían encabezados SOAP personalizados combinados con los encabezados SOAP estándar que utiliza la infraestructura de WCF para estándares de servicios Web, por ejemplo, WS-Addressing, WS-Security y WS-AtomicTransaction. Cuando se usa el **OutboundCustomHeaders** propiedad, la propiedad debe tener la \< **encabezados** \> elemento como el elemento raíz. Todos los encabezados SOAP personalizados deben colocarse dentro de la \< **encabezados** \> elemento. Si el valor del encabezado SOAP personalizado es una cadena vacía, debe asignar \< **encabezados**\>\</**encabezados** \> o \< **encabezados** / \> a la **OutboundCustomHeaders** propiedad.  
  
 Respecto a las orquestaciones, las propiedades de contexto del encabezado SOAP están establecidas como cadenas que contienen datos XML. Establezca estas cadenas utilizando el Editor de expresiones de BizTalk en un **asignación de mensajes** o **expresión** forma. Para obtener más información acerca de cómo usar encabezados SOAP con los adaptadores WCF, vea el ejemplo de SDK Using Custom SOAP Headers with the WCF Adapters de [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).  
  
 El siguiente ejemplo (de una forma Asignación de mensajes o Expresión) muestra la configuración de la cadena de la propiedad de contexto:  
  
```  
outboundMessageInstance(WCF.OutboundCustomHeaders) = "<headers><Origination>Home</Origination><Destination>Work</Destination></headers>"  
```  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a>Crear un XmlDocument para establecer propiedades de contexto  
 Puede establecer el **WCF. OutboundCustomHeaders** propiedad de contexto mediante la creación de un **XmlDocument** y escribir el valor de cadena de la **XmlDocument** a la propiedad de contexto. Declare una variable de tipo **XMLDocument** y asigne los datos XML.  
  
 En el ejemplo siguiente se muestra la declaración de una variable de tipo **XMLDocument** y asignar los datos XML:  
  
```  
xmlDoc.LoadXml("<headers><Origination>Home</Origination><Destination>Work</Destination></headers>");  
```  
  
 El siguiente ejemplo muestra la configuración de la propiedad de contexto:  
  
```  
RequestMessageInstance(WCF.OutboundCustomHeaders) = xmlDoc.OuterXml;  
```  
  
 Para obtener más información acerca de cómo utilizar el Editor de expresiones de BizTalk, consulte [requisitos y limitaciones para las expresiones](../core/requirements-and-limitations-for-expressions.md). Para obtener más información acerca de las llamadas [!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)] clases, vea el artículo [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).  
  
## <a name="see-also"></a>Vea también  
 [Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md)   
 [Encabezados SOAP con servicios WCF consumidos](../core/soap-headers-with-consumed-wcf-services.md)   
 [Encabezados SOAP con servicios WCF publicados](../core/soap-headers-with-published-wcf-services.md)