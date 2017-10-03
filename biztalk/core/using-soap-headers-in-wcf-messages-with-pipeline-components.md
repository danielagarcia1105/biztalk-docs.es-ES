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
ms.openlocfilehash: bf40cf5a81188dae0174199f16229daf61115796
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-wcf-messages-with-pipeline-components"></a><span data-ttu-id="323a7-102">Usar encabezados SOAP en mensajes WCF con componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="323a7-102">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>
<span data-ttu-id="323a7-103">Se pueden establecer los encabezados SOAP personalizados con los adaptadores de WCF en componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="323a7-103">You can set the custom SOAP headers with the WCF adapters in pipeline components.</span></span> <span data-ttu-id="323a7-104">Usar una combinación del nombre de la propiedad de contexto, **OutboundCustomHeaders**y el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**.</span><span class="sxs-lookup"><span data-stu-id="323a7-104">You use a combination of the context property name, **OutboundCustomHeaders**, and the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**.</span></span> <span data-ttu-id="323a7-105">Cuando se usa el **OutboundCustomHeaders** propiedad, la propiedad debe tener la \< **encabezados**> elemento como el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="323a7-105">When you use the **OutboundCustomHeaders** property, the property must have the \<**headers**> element as the root element.</span></span> <span data-ttu-id="323a7-106">Todos los encabezados SOAP personalizados deben colocarse dentro de la \< **encabezados**> elemento.</span><span class="sxs-lookup"><span data-stu-id="323a7-106">All of the custom SOAP headers must be placed inside the \<**headers**> element.</span></span> <span data-ttu-id="323a7-107">Si el valor del encabezado SOAP personalizado es una cadena vacía, debe asignar \< **encabezados**>\</**encabezados**> o \< **encabezados**/ > a la **OutboundCustomHeaders** propiedad.</span><span class="sxs-lookup"><span data-stu-id="323a7-107">If the custom SOAP header value is an empty string, you must assign \<**headers**>\</**headers**> or \<**headers**/> to the **OutboundCustomHeaders** property.</span></span> <span data-ttu-id="323a7-108">Para obtener más información acerca de cómo usar encabezados SOAP con los adaptadores WCF, vea el ejemplo de SDK Using Custom SOAP Headers with the WCF Adapters de [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span><span class="sxs-lookup"><span data-stu-id="323a7-108">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
 <span data-ttu-id="323a7-109">El ejemplo de código siguiente establece los encabezados SOAP personalizados en un componente de canalización de envío para una propiedad denominada **OutboundCustomHeaders**:</span><span class="sxs-lookup"><span data-stu-id="323a7-109">The following code example sets custom SOAP headers in a send pipeline component for a property named **OutboundCustomHeaders**:</span></span>  
  
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
  
 <span data-ttu-id="323a7-110">Para obtener más información acerca de los componentes de canalización, consulte [desarrollar componentes de canalización personalizados](../core/developing-custom-pipeline-components.md).</span><span class="sxs-lookup"><span data-stu-id="323a7-110">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="323a7-111">No debe establecer los encabezados SOAP estándar que utiliza la infraestructura de WCF para estándares de servicios Web como, por ejemplo, WS-Addressing, WS-Security y WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="323a7-111">You must not set the standard SOAP headers that the WCF infrastructure uses for Web services standards such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="323a7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="323a7-112">See Also</span></span>  
 <span data-ttu-id="323a7-113">[Usar encabezados SOAP en mensajes WCF con orquestaciones](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="323a7-113">[Using SOAP Headers in WCF Messages with Orchestrations](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md) </span></span>  
 <span data-ttu-id="323a7-114">[Encabezados SOAP con servicios WCF consumidos](../core/soap-headers-with-consumed-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="323a7-114">[SOAP Headers with Consumed WCF Services](../core/soap-headers-with-consumed-wcf-services.md) </span></span>  
 <span data-ttu-id="323a7-115">[Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="323a7-115">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="323a7-116">Encabezados SOAP con servicios WCF publicados</span><span class="sxs-lookup"><span data-stu-id="323a7-116">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)