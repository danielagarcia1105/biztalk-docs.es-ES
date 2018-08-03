---
title: Encabezados SOAP con servicios WCF consumidos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- SOAP headers, WCF services
- consuming, SOAP headers
- WCF services, SOAP headers
- SOAP headers, consuming [WCF services]
ms.assetid: 0582ee26-b549-4b50-b365-36824010dab0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f60e0ae7f9cf2e6a224ce9d919c7c4d5e6f3119c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277492"
---
# <a name="soap-headers-with-consumed-wcf-services"></a><span data-ttu-id="4d512-102">Encabezados SOAP con servicios WCF consumidos</span><span class="sxs-lookup"><span data-stu-id="4d512-102">SOAP Headers with Consumed WCF Services</span></span>
<span data-ttu-id="4d512-103">Para enviar un mensaje a un servicio WCF con encabezados SOAP personalizados, estos encabezados se deben establecer en la orquestación (en forma de expresión, por ejemplo) y los componentes de canalización (en código) como la propiedad de contexto **OutboundCustomHeaders**.</span><span class="sxs-lookup"><span data-stu-id="4d512-103">To send a message to a WCF service with the custom SOAP headers, these headers must be set in your orchestrations (in the Expression shape, for example) and pipeline components (in code) as the context property **OutboundCustomHeaders**.</span></span> <span data-ttu-id="4d512-104">Esta propiedad se encuentra en el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**y contiene representaciones de cadena de los encabezados SOAP personalizados.</span><span class="sxs-lookup"><span data-stu-id="4d512-104">This context property is in the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**, and contains string representations of the custom SOAP headers.</span></span>  
  
 <span data-ttu-id="4d512-105">Los datos en el mensaje saliente de XML siguiente muestran un ejemplo de la representación de cadena de encabezados SOAP personalizados para la **OutboundCustomHeaders** propiedad:</span><span class="sxs-lookup"><span data-stu-id="4d512-105">The data in the following XML outgoing message shows an example of the string representation of custom SOAP headers for the **OutboundCustomHeaders** property:</span></span>  
  
```  
<headers>  
<Origination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Home</Origination>  
<Destination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Work</Destination>  
</headers>  
```  
  
 <span data-ttu-id="4d512-106">Los encabezados SOAP entrantes también contienen representaciones de cadenas de los encabezados SOAP.</span><span class="sxs-lookup"><span data-stu-id="4d512-106">Inbound SOAP headers also contain string representations of the SOAP headers.</span></span> <span data-ttu-id="4d512-107">Los valores son parecidos a la creación de un encabezado SOAP de solicitud.</span><span class="sxs-lookup"><span data-stu-id="4d512-107">The values are similar to creating a request SOAP header.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d512-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4d512-108">In This Section</span></span>  
  
-   [<span data-ttu-id="4d512-109">Usar encabezados SOAP en mensajes WCF con orquestaciones</span><span class="sxs-lookup"><span data-stu-id="4d512-109">Using SOAP Headers in WCF Messages with Orchestrations</span></span>](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [<span data-ttu-id="4d512-110">Usar encabezados SOAP en mensajes WCF con componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="4d512-110">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a><span data-ttu-id="4d512-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d512-111">See Also</span></span>  
 <span data-ttu-id="4d512-112">[Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="4d512-112">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="4d512-113">Encabezados SOAP con servicios WCF publicados</span><span class="sxs-lookup"><span data-stu-id="4d512-113">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)