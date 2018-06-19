---
title: Obtener acceso a los encabezados SOAP en componentes de canalización | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, pipelines
- SOAP headers, properties
- pipelines, SOAP headers
ms.assetid: a2fb074e-0fde-487e-a6ec-7e2b543b7c8b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e484b221df54f00b02f20ef89466fed6b99cd69d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225100"
---
# <a name="accessing-soap-headers-in-pipeline-components"></a><span data-ttu-id="4c333-102">Obtener acceso a los encabezados SOAP en componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="4c333-102">Accessing SOAP Headers in Pipeline Components</span></span>
<span data-ttu-id="4c333-103">Puede obtener acceso a las propiedades de contexto de encabezados SOAP en componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="4c333-103">You can access SOAP header context properties in pipeline components.</span></span> <span data-ttu-id="4c333-104">Usar una combinación de nombre de la propiedad de contexto y el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**.</span><span class="sxs-lookup"><span data-stu-id="4c333-104">You use a combination of the context property name and the target namespace **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**.</span></span>  
  
 <span data-ttu-id="4c333-105">En el ejemplo de código siguiente se obtiene el encabezado SOAP de solicitud en un componente de canalización de recepción para la propiedad **OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="4c333-105">The following code example gets the request SOAP header in a receive pipeline component for the property **OrigDest**:</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
   {  
   string stringVar = inmsg.Context.Read("OrigDest",    "http://schemas.microsoft.com/BizTalk/2003/SOAPHeader").ToString();  
   }  
   catch (Exception ex)  
   {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
   }  
return inmsg;  
}  
```  
  
 <span data-ttu-id="4c333-106">Para obtener más información acerca de los componentes de canalización, consulte [desarrollar componentes de canalización personalizados](../core/developing-custom-pipeline-components.md).</span><span class="sxs-lookup"><span data-stu-id="4c333-106">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c333-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c333-107">See Also</span></span>  
 [<span data-ttu-id="4c333-108">Encabezados SOAP con servicios Web publicados</span><span class="sxs-lookup"><span data-stu-id="4c333-108">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)