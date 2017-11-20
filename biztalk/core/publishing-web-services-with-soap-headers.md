---
title: "Publicación de servicios Web con encabezados SOAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, code samples
- SOAP headers, pipelines
- SOAP headers, BizTalk Web Services Publishing Wizard
- pipelines, SOAP headers
- orchestrations, SOAP headers
ms.assetid: c362caff-b75f-4c1b-9013-d2b9c74f5c65
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7baf6af0e4505e448a854fe6def372614bfdaa49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-web-services-with-soap-headers"></a><span data-ttu-id="da9fa-102">Publicar servicios Web con encabezados SOAP</span><span class="sxs-lookup"><span data-stu-id="da9fa-102">Publishing Web Services with SOAP Headers</span></span>
<span data-ttu-id="da9fa-103">Al ejecutar el Asistente para publicar servicios Web de BizTalk, se agregan encabezados SOAP a los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="da9fa-103">You add SOAP headers to your Web services when you run the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="da9fa-104">Al publicar un servicio Web que admite encabezados SOAP, los encabezados están disponibles para las orquestaciones y los componentes de canalización como propiedades de contexto que contienen representaciones de cadena de los encabezados SOAP.</span><span class="sxs-lookup"><span data-stu-id="da9fa-104">When you publish a Web service that supports SOAP headers, the headers become available to orchestrations and pipeline components as context properties that contain string representations of the SOAP headers.</span></span>  
  
## <a name="defined-soap-headers"></a><span data-ttu-id="da9fa-105">Encabezados SOAP definidos</span><span class="sxs-lookup"><span data-stu-id="da9fa-105">Defined SOAP headers</span></span>  
 <span data-ttu-id="da9fa-106">Al agregar un encabezado SOAP definido mediante el asistente, éste crea una propiedad de contexto con un nombre que se corresponde con el elemento raíz del encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="da9fa-106">When you add a defined SOAP header using the wizard, the wizard creates a context property with a name that corresponds to the root element of the SOAP header.</span></span> <span data-ttu-id="da9fa-107">Todas las propiedades de contexto de encabezado SOAP definidas tienen el espacio de nombres **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**.</span><span class="sxs-lookup"><span data-stu-id="da9fa-107">All defined SOAP header context properties have the namespace **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**.</span></span> <span data-ttu-id="da9fa-108">Cuando el adaptador de SOAP convierte la solicitud SOAP en un mensaje de BizTalk, crea una propiedad de contexto de encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="da9fa-108">When the SOAP adapter converts the SOAP request to a BizTalk message, it creates one SOAP header context property.</span></span>  
  
 <span data-ttu-id="da9fa-109">En el siguiente ejemplo se muestra una solicitud SOAP simple:</span><span class="sxs-lookup"><span data-stu-id="da9fa-109">The following example shows a simple SOAP request:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
       <soap:Header>  
             <OrigDest xmlns="http://SOAPHeaderWS.ItemAvailability">  
                    <Origination>Work</Origination>  
                    <Destination>Home</Destination>  
             </OrigDest>  
       </soap:Header>  
       <soap:Body>  
  
       </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="da9fa-110">Para la solicitud SOAP simple, el adaptador SOAP, cree un mensaje de BizTalk con una propiedad de contexto de encabezado SOAP **OrigDest** y la cadena.</span><span class="sxs-lookup"><span data-stu-id="da9fa-110">For the simple SOAP request, the SOAP adapter created a BizTalk message with one SOAP header context property **OrigDest** and the string.</span></span>  
  
 <span data-ttu-id="da9fa-111">El siguiente ejemplo muestra la cadena creada por el adaptador de SOAP:</span><span class="sxs-lookup"><span data-stu-id="da9fa-111">The following example shows the string created by the SOAP adapter:</span></span>  
  
```  
"<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader"><Origination xmlns="">Home</Origination><Destination xmlns="">Work</Destination> </OrigDest>"  
```  
  
## <a name="unknown-soap-headers"></a><span data-ttu-id="da9fa-112">Encabezados SOAP desconocidos</span><span class="sxs-lookup"><span data-stu-id="da9fa-112">Unknown SOAP headers</span></span>  
 <span data-ttu-id="da9fa-113">Si decide admitir encabezados SOAP desconocidos en el asistente, el asistente crea una propiedad de contexto con el nombre **UnknownHeaders** y el espacio de nombres **http://schemas.microsoft.com/BizTalk/2003/soap-properties**.</span><span class="sxs-lookup"><span data-stu-id="da9fa-113">If you choose to support unknown SOAP headers in the wizard, the wizard creates a context property with the name **UnknownHeaders** and the namespace **http://schemas.microsoft.com/BizTalk/2003/soap-properties**.</span></span> <span data-ttu-id="da9fa-114">El **UnknownHeaders** propiedad de contexto contiene todos los encabezados SOAP desconocidos recibidos.</span><span class="sxs-lookup"><span data-stu-id="da9fa-114">The **UnknownHeaders** context property contains all of the received unknown SOAP headers.</span></span>  
  
 <span data-ttu-id="da9fa-115">Por ejemplo, si recibe un encabezado SOAP desconocido con el nombre del elemento raíz, **CustomerGroup**, **UnknownHeaders** propiedad de contexto contiene la cadena:</span><span class="sxs-lookup"><span data-stu-id="da9fa-115">For example, if you receive an unknown SOAP header with the root element name, **CustomerGroup**, the **UnknownHeaders** context property contains the string:</span></span>  
  
```  
"<?xml version="1.0" encoding="utf-16"?><UnknownHeaders><CustomerGroup xmlns="http://SOAPHeaderWS/CustomerGroup"><Id xmlns="">My Customer</Id>  
</CustomerGroup></UnknownHeaders>"  
```  
  
 <span data-ttu-id="da9fa-116">Para obtener más información acerca de cómo agregar definido encabezados SOAP o admitir encabezados SOAP desconocidos, consulte [publicar una orquestación como un servicio Web](../core/publishing-an-orchestration-as-a-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="da9fa-116">For more information about adding defined SOAP headers or supporting unknown SOAP headers, see [Publishing an Orchestration as a Web Service](../core/publishing-an-orchestration-as-a-web-service.md).</span></span> <span data-ttu-id="da9fa-117">Consulte también [publicar esquemas como servicios Web](../core/publishing-schemas-as-a-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="da9fa-117">Also see [Publishing Schemas as a Web Service](../core/publishing-schemas-as-a-web-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da9fa-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="da9fa-118">See Also</span></span>  
 [<span data-ttu-id="da9fa-119">Encabezados SOAP con servicios Web publicados</span><span class="sxs-lookup"><span data-stu-id="da9fa-119">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)