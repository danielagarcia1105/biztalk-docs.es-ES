---
title: Consumir servicios Web con encabezados SOAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers, consuming
- Web services, consuming
- Web services, SOAP headers
- SOAP headers, Web services
ms.assetid: c2dfe7d8-e2f0-4bc6-b79c-354d06a7ffd6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45a3efa628e435092505fdc3884704baa15be34c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="consuming-web-services-with-soap-headers"></a><span data-ttu-id="2e600-102">Consumir servicios Web con encabezados SOAP</span><span class="sxs-lookup"><span data-stu-id="2e600-102">Consuming Web Services with SOAP Headers</span></span>
<span data-ttu-id="2e600-103">Después de consumir un servicio Web con encabezados SOAP definidos, éstos pasan a estar disponibles para las orquestaciones y los componentes de canalización como propiedades de contexto.</span><span class="sxs-lookup"><span data-stu-id="2e600-103">After you consume a Web service with defined SOAP headers, these headers become available to your orchestrations and pipeline components as context properties.</span></span> <span data-ttu-id="2e600-104">Estas propiedades de contexto contienen representaciones de cadenas de los encabezados SOAP.</span><span class="sxs-lookup"><span data-stu-id="2e600-104">These context properties contain string representations of the SOAP headers.</span></span> <span data-ttu-id="2e600-105">Para cada encabezado SOAP definido en el servicio Web, puede crear una propiedad de contexto mediante el nombre que corresponde al elemento raíz del encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="2e600-105">For each defined SOAP header in the Web service, you can create a context property by using the name that corresponds to the root element of the SOAP header.</span></span> <span data-ttu-id="2e600-106">Todas las propiedades de contexto de encabezado SOAP definidas están en el **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader** espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2e600-106">All defined SOAP header context properties are in the **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader** namespace.</span></span>  
  
 <span data-ttu-id="2e600-107">En el ejemplo siguiente se muestra cómo crear una propiedad de contexto del encabezado SOAP **OrigDest** en el ejemplo de encabezado SOAP en [encabezados SOAP con los servicios Web consumidos](../core/soap-headers-with-consumed-web-services.md):</span><span class="sxs-lookup"><span data-stu-id="2e600-107">The following example shows how to create a SOAP header context property **OrigDest** using the SOAP header example in [SOAP Headers with Consumed Web Services](../core/soap-headers-with-consumed-web-services.md):</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<OrigDest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns=" http://SOAPHeaderWS.ItemAvailability">  
   <Origination xmlns="">Home</Origination>  
      <Destination xmlns="">Work</Destination>  
</OrigDest>  
```  
  
 <span data-ttu-id="2e600-108">Los encabezados SOAP de respuesta también contienen representaciones de cadena del encabezado SOAP definido.</span><span class="sxs-lookup"><span data-stu-id="2e600-108">Response SOAP headers also contain string representations of the defined SOAP header.</span></span> <span data-ttu-id="2e600-109">Los valores son parecidos a la creación de un encabezado SOAP de solicitud.</span><span class="sxs-lookup"><span data-stu-id="2e600-109">The values are similar to creating a request SOAP header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e600-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e600-110">See Also</span></span>  
 [<span data-ttu-id="2e600-111">Encabezados SOAP con servicios Web consumidos</span><span class="sxs-lookup"><span data-stu-id="2e600-111">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)