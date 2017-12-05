---
title: "Obtener acceso a los encabezados SOAP en mensajes WCF con componentes de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, WCF services
- WCF services, pipeline components
- pipeline components, SOAP headers
- SOAP headers, pipeline components
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: 5e24afa3-b2e6-472e-8890-a47b59573304
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8bc9c2c17172cb29ee75bfbfc4aaee841848fa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="accessing-soap-headers-in-wcf-messages-with-pipeline-components"></a><span data-ttu-id="95177-102">Obtener acceso a encabezados SOAP en mensajes WCF con componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="95177-102">Accessing SOAP Headers in WCF Messages with Pipeline Components</span></span>
<span data-ttu-id="95177-103">Para obtener acceso a los encabezados SOAP con los adaptadores de WCF en componentes de canalización, use una combinación del nombre de la propiedad de contexto, **InboundHeaders**y el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2006/ 01 / / WCF-propiedades de adaptadores de**.</span><span class="sxs-lookup"><span data-stu-id="95177-103">To access the SOAP headers with the WCF adapters in pipeline components, you use a combination of the context property name, **InboundHeaders**, and the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**.</span></span> <span data-ttu-id="95177-104">Los adaptadores WCF copian encabezados SOAP personalizados y encabezados SOAP estándar en los mensajes entrantes en el **InboundHeaders** propiedad.</span><span class="sxs-lookup"><span data-stu-id="95177-104">The WCF adapters copy custom SOAP headers and standard SOAP headers in the inbound messages to the **InboundHeaders** property.</span></span> <span data-ttu-id="95177-105">Los adaptadores de WCF también le permiten seleccionar mediante programación las propiedades que desea promocionar o escribir en las propiedades de contexto mediante programación.</span><span class="sxs-lookup"><span data-stu-id="95177-105">The WCF adapters also allow you to programmatically select the properties you would like to promote or write to the context properties programmatically.</span></span> <span data-ttu-id="95177-106">Vea [encabezados SOAP con servicios de WCF publican](../core/soap-headers-with-published-wcf-services.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="95177-106">See [SOAP Headers with Published WCF Services](../core/soap-headers-with-published-wcf-services.md) for more details.</span></span>  
  
 <span data-ttu-id="95177-107">El valor contenido en la propiedad de contexto es una cadena que contiene los datos XML con la \< **encabezados** \> elemento raíz y los encabezados SOAP entrantes se copian como elementos secundarios de la \< **encabezados** \> elemento.</span><span class="sxs-lookup"><span data-stu-id="95177-107">The value contained in the context property is a string containing XML data with the \<**headers**\> root element, and the incoming SOAP headers are copied as child elements of the \<**headers**\> element.</span></span> <span data-ttu-id="95177-108">Para obtener más información acerca de cómo los encabezados SOAP de acceso con los adaptadores de WCF, consulte el ejemplo SDK "Usando Custom SOAP encabezados con los adaptadores de WCF" en [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span><span class="sxs-lookup"><span data-stu-id="95177-108">For more information about how to access SOAP headers with the WCF adapters, see the SDK sample "Using Custom SOAP Headers with the WCF Adapters" at [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
 <span data-ttu-id="95177-109">El siguiente código de un componente de canalización personalizado Obtiene el encabezado SOAP de solicitud en un componente de canalización de recepción para el **InboundHeaders** propiedad:</span><span class="sxs-lookup"><span data-stu-id="95177-109">The following code from a custom pipeline component gets the request SOAP header in a receive pipeline component for the **InboundHeaders** property:</span></span>  
  
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
  
 <span data-ttu-id="95177-110">Para obtener más información acerca de los componentes de canalización, consulte [desarrollar componentes de canalización personalizados](../core/developing-custom-pipeline-components.md).</span><span class="sxs-lookup"><span data-stu-id="95177-110">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95177-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="95177-111">See Also</span></span>  
 <span data-ttu-id="95177-112">[Obtener acceso a los encabezados SOAP en mensajes WCF con orquestaciones](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="95177-112">[Accessing SOAP Headers in WCF Messages with Orchestrations](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md) </span></span>  
 <span data-ttu-id="95177-113">[Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="95177-113">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="95177-114">Encabezados SOAP con servicios WCF consumidos</span><span class="sxs-lookup"><span data-stu-id="95177-114">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)