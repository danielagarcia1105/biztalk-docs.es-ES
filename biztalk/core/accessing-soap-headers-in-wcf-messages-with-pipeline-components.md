---
title: Obtener acceso a los encabezados SOAP en mensajes WCF con componentes de canalización | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, WCF services
- WCF services, pipeline components
- pipeline components, SOAP headers
- SOAP headers, pipeline components
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: 5e24afa3-b2e6-472e-8890-a47b59573304
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8bc9c2c17172cb29ee75bfbfc4aaee841848fa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965106"
---
# <a name="accessing-soap-headers-in-wcf-messages-with-pipeline-components"></a>Obtener acceso a encabezados SOAP en mensajes WCF con componentes de canalización
Para obtener acceso a los encabezados SOAP con los adaptadores de WCF en componentes de canalización, use una combinación del nombre de la propiedad de contexto, **InboundHeaders**y el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2006/ 01 / / WCF-propiedades de adaptadores de**. Los adaptadores WCF copian encabezados SOAP personalizados y encabezados SOAP estándar en los mensajes entrantes en el **InboundHeaders** propiedad. Los adaptadores de WCF también le permiten seleccionar mediante programación las propiedades que desea promocionar o escribir en las propiedades de contexto mediante programación. Vea [encabezados SOAP con servicios de WCF publican](../core/soap-headers-with-published-wcf-services.md) para obtener más detalles.  
  
 El valor contenido en la propiedad de contexto es una cadena que contiene los datos XML con la \< **encabezados** \> elemento raíz y los encabezados SOAP entrantes se copian como elementos secundarios de la \< **encabezados** \> elemento. Para obtener más información acerca de cómo los encabezados SOAP de acceso con los adaptadores de WCF, consulte el ejemplo SDK "Usando Custom SOAP encabezados con los adaptadores de WCF" en [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).  
  
 El siguiente código de un componente de canalización personalizado Obtiene el encabezado SOAP de solicitud en un componente de canalización de recepción para el **InboundHeaders** propiedad:  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
   {  
   string stringVar = inmsg.Context.Read("InboundHeaders",    "http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties").ToString();  
   }  
   catch (Exception ex)  
   {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
   }  
return inmsg;  
}  
```  
  
 Para obtener más información acerca de los componentes de canalización, consulte [desarrollar componentes de canalización personalizados](../core/developing-custom-pipeline-components.md).  
  
## <a name="see-also"></a>Vea también  
 [Obtener acceso a los encabezados SOAP en mensajes WCF con orquestaciones](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md)   
 [Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md)   
 [Encabezados SOAP con servicios WCF consumidos](../core/soap-headers-with-consumed-wcf-services.md)