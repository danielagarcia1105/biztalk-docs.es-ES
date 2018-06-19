---
title: Usar encabezados SOAP en componentes de canalización | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, code samples
- SOAP headers, creating
- SOAP headers, pipelines
- SOAP headers, properties
- pipelines, SOAP headers
- Web services, SOAP headers
- creating, SOAP headers
ms.assetid: 5b4a8902-e8f5-44a4-88f7-17f47a9deecd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c11b74aafe53150ced42d0c53a2e19a2c5080fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287276"
---
# <a name="using-soap-headers-in-pipeline-components"></a><span data-ttu-id="bf046-102">Usar encabezados SOAP en componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="bf046-102">Using SOAP Headers in Pipeline Components</span></span>
<span data-ttu-id="bf046-103">Para obtener acceso a las propiedades de contexto del encabezado SOAP en componentes de canalización, utilice una combinación del contexto propiedad nombre y destino de espacio de nombres como se describe en [utilizar encabezados SOAP en orquestaciones](../core/using-soap-headers-in-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="bf046-103">To access the SOAP header context properties in pipeline components, you use a combination of the context property name and target namespace as discussed in [Using SOAP Headers in Orchestrations](../core/using-soap-headers-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="bf046-104">En el ejemplo de código siguiente se establece el encabezado SOAP de solicitud en un componente de canalización de envío para un nombre de propiedad **OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="bf046-104">The following code example sets the request SOAP header in a send pipeline component for a property name **OrigDest**:</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
      {  
       string stringVar = "<?xml version=\"1.0\"?>  
          <OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
             <Origination>Home</Origination>  
             <Destination>Work</Destination>  
          </OrigDest>";  
inmsg.Context.Write("OrigDest","http://schemas.microsoft.com/BizTalk/2003/SOAPHeader", stringVar);  
      }  
   catch (Exception ex)  
      {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
      }  
return inmsg;  
}  
```  
  
 <span data-ttu-id="bf046-105">Para obtener más información acerca de los componentes de canalización, consulte [desarrollar componentes de canalización personalizados](../core/developing-custom-pipeline-components.md).</span><span class="sxs-lookup"><span data-stu-id="bf046-105">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf046-106">Cuando consume servicios Web (llamada) de una orquestación, el adaptador de SOAP sólo admite canalizaciones de envío y de recepción de estilo de paso a través.</span><span class="sxs-lookup"><span data-stu-id="bf046-106">When you consume (call) Web services from an orchestration, the SOAP adapter only supports pass-through style receive and send pipelines.</span></span> <span data-ttu-id="bf046-107">Se puede usar una canalización personalizada, pero no puede contener componentes que modifican las partes del cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="bf046-107">You can use a custom pipeline, but it cannot contain components that modify the body parts of the message.</span></span> <span data-ttu-id="bf046-108">Estos componentes incluyen el ensamblador de XML, desensamblador de XML y validador de XML.</span><span class="sxs-lookup"><span data-stu-id="bf046-108">These components include the XML Assembler, XML Disassembler, and XML Validator components.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf046-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf046-109">See Also</span></span>  
 <span data-ttu-id="bf046-110">[Canalizaciones predeterminadas](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="bf046-110">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 [<span data-ttu-id="bf046-111">Encabezados SOAP con servicios Web consumidos</span><span class="sxs-lookup"><span data-stu-id="bf046-111">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)