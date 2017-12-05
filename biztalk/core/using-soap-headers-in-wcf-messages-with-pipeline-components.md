---
title: "Usar encabezados SOAP en mensajes WCF con componentes de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, SOAP headers
- SOAP headers, pipeline components
- SOAP headers, WCF services
- WCF services, SOAP headers
ms.assetid: b02f2913-4948-4de9-bc59-73bab40aa1a0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce166c5d05b8ce48f513420e247e8f35ca1d509
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="using-soap-headers-in-wcf-messages-with-pipeline-components"></a>Usar encabezados SOAP en mensajes WCF con componentes de canalización
Se pueden establecer los encabezados SOAP personalizados con los adaptadores de WCF en componentes de canalización. Usar una combinación del nombre de la propiedad de contexto, **OutboundCustomHeaders**y el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**. Cuando se usa el **OutboundCustomHeaders** propiedad, la propiedad debe tener la \< **encabezados** \> elemento como el elemento raíz. Todos los encabezados SOAP personalizados deben colocarse dentro de la \< **encabezados** \> elemento. Si el valor del encabezado SOAP personalizado es una cadena vacía, debe asignar \< **encabezados**\>\</**encabezados** \> o \< **encabezados** / \> a la **OutboundCustomHeaders** propiedad. Para obtener más información acerca de cómo usar encabezados SOAP con los adaptadores WCF, vea el ejemplo de SDK Using Custom SOAP Headers with the WCF Adapters de [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).  
  
 El ejemplo de código siguiente establece los encabezados SOAP personalizados en un componente de canalización de envío para una propiedad denominada **OutboundCustomHeaders**:  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
      {  
       string stringVar = "<headers>  
             <Origination>Home</Origination>  
             <Destination>Work</Destination>  
          </headers>";  
inmsg.Context.Write("OutboundCustomHeaders","http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties", stringVar);  
      }  
   catch (Exception ex)  
      {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
      }  
return inmsg;  
}  
```  
  
 Para obtener más información acerca de los componentes de canalización, consulte [desarrollar componentes de canalización personalizados](../core/developing-custom-pipeline-components.md).  
  
> [!NOTE]
>  No debe establecer los encabezados SOAP estándar que utiliza la infraestructura de WCF para estándares de servicios Web como, por ejemplo, WS-Addressing, WS-Security y WS-AtomicTransaction.  
  
## <a name="see-also"></a>Vea también  
 [Usar encabezados SOAP en mensajes WCF con orquestaciones](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md)   
 [Encabezados SOAP con servicios WCF consumidos](../core/soap-headers-with-consumed-wcf-services.md)   
 [Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md)   
 [Encabezados SOAP con servicios WCF publicados](../core/soap-headers-with-published-wcf-services.md)