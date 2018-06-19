---
title: Obtener acceso a los encabezados SOAP en mensajes WCF con orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- orchestrations, WCF services
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: fe02fb02-18d6-4fc6-89e0-b06bdbfa5cb4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bfd1dd4e09071c3d7bcccf28878f19e13acad8a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966842"
---
# <a name="accessing-soap-headers-in-wcf-messages-with-orchestrations"></a><span data-ttu-id="14345-102">Obtener acceso a encabezados SOAP en mensajes WCF con orquestaciones</span><span class="sxs-lookup"><span data-stu-id="14345-102">Accessing SOAP Headers in WCF Messages with Orchestrations</span></span>
<span data-ttu-id="14345-103">Para obtener acceso a los valores del encabezado SOAP de mensajes entrantes de WCF en orquestaciones, use la propiedad de contexto **WCF. InboundHeaders**.</span><span class="sxs-lookup"><span data-stu-id="14345-103">To access the SOAP header values of incoming WCF messages in orchestrations, you use the context property **WCF.InboundHeaders**.</span></span> <span data-ttu-id="14345-104">Los adaptadores WCF copian encabezados SOAP personalizados y encabezados SOAP estándar en los mensajes entrantes en el **WCF. InboundHeaders** propiedad.</span><span class="sxs-lookup"><span data-stu-id="14345-104">The WCF adapters copy custom SOAP headers and standard SOAP headers in the inbound messages to the **WCF.InboundHeaders** property.</span></span> <span data-ttu-id="14345-105">Además, los adaptadores de WCF permiten seleccionar las propiedades que desee promocionar o escribir en las propiedades de contexto mediante programación.</span><span class="sxs-lookup"><span data-stu-id="14345-105">The WCF adapters also allow you to select the properties you would like to promote or write to the context properties programmatically.</span></span> <span data-ttu-id="14345-106">Vea [encabezados SOAP con servicios de WCF publican](../core/soap-headers-with-published-wcf-services.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="14345-106">See [SOAP Headers with Published WCF Services](../core/soap-headers-with-published-wcf-services.md) for more details.</span></span>  
  
 <span data-ttu-id="14345-107">El valor contenido en la propiedad de contexto es una cadena que contiene los datos XML con la \< **encabezados** \> elemento raíz y los encabezados SOAP entrantes se copian como elementos secundarios de la \< **encabezados** \> elemento.</span><span class="sxs-lookup"><span data-stu-id="14345-107">The value contained in the context property is a string containing XML data with the \<**headers**\> root element, and the incoming SOAP headers are copied as child elements of the \<**headers**\> element.</span></span> <span data-ttu-id="14345-108">La manera más sencilla de obtener acceso a estos datos consiste en usar el Editor de expresiones de BizTalk en un **asignación de mensajes** o **expresión** forma, carga la cadena en un **XmlDocument**y usar Consultas de XPath para tener acceso a campos específicos.</span><span class="sxs-lookup"><span data-stu-id="14345-108">The simplest way to access this data is to use the BizTalk Expression Editor in a **Message Assignment** or **Expression** shape, load the string in an **XmlDocument**, and use XPath queries to access specific fields.</span></span> <span data-ttu-id="14345-109">Para obtener más información acerca de cómo crear documentos XML en el Editor de expresiones de BizTalk, consulte [lenguaje XLANG s](../core/xlang-s-language.md).</span><span class="sxs-lookup"><span data-stu-id="14345-109">For more information about creating XML documents in the BizTalk Expression Editor, see [XLANG-s Language](../core/xlang-s-language.md).</span></span>  
  
 <span data-ttu-id="14345-110">En el ejemplo de código siguiente se obtiene el encabezado SOAP de solicitud un **asignación de mensajes** o **expresión** forma para el **WCF. InboundHeaders** propiedad:</span><span class="sxs-lookup"><span data-stu-id="14345-110">The following code example gets the request SOAP header in a **Message Assignment** or **Expression** shape for the **WCF.InboundHeaders** property:</span></span>  
  
```  
stringVar = inboundMessageInstance(WCF.InboundHeaders);  
```  
  
 <span data-ttu-id="14345-111">Las propiedades de contexto están asociadas con un mensaje concreto.</span><span class="sxs-lookup"><span data-stu-id="14345-111">Context properties are associated with a particular message.</span></span> <span data-ttu-id="14345-112">El motor de mensajería no asigna automáticamente los valores de los encabezados SOAP desde el mensaje de solicitud al mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="14345-112">The Messaging Engine does not automatically map the values of the SOAP headers from the request message to the response message.</span></span> <span data-ttu-id="14345-113">Al crear el mensaje de respuesta para un servicio WCF, debe definir específicamente los valores del encabezado SOAP a través de la **WCF. OutboundCustomHeaders** propiedad.</span><span class="sxs-lookup"><span data-stu-id="14345-113">When creating the response message for a WCF service, you must specifically set the SOAP header values through the **WCF.OutboundCustomHeaders** property.</span></span> <span data-ttu-id="14345-114">El comando siguiente es el método más sencillo de establecer una propiedad de contexto del encabezado SOAP:</span><span class="sxs-lookup"><span data-stu-id="14345-114">The following command is the simplest method of setting a SOAP header context property:</span></span>  
  
```  
outboundMessageInstance(WCF.OutbounCustomHeaders) = "<headers><Origination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Home</Origination><Destination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Work</Destination></headers>"  
```  
  
 <span data-ttu-id="14345-115">También puede establecer la propiedad de contexto mediante la creación de un **XmlDocument** y escribir el valor de cadena de la **XmlDocument** a la propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="14345-115">You can also set the context property by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span>  
  
 <span data-ttu-id="14345-116">Para obtener más información acerca de cómo los encabezados SOAP de acceso con los adaptadores de WCF, consulte el ejemplo SDK "Usando Custom SOAP encabezados con los adaptadores de WCF" en [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span><span class="sxs-lookup"><span data-stu-id="14345-116">For more information about how to access SOAP headers with the WCF adapters, see the SDK sample "Using Custom SOAP Headers with the WCF Adapters" at [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14345-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="14345-117">See Also</span></span>  
 <span data-ttu-id="14345-118">[Obtener acceso a los encabezados SOAP en mensajes WCF con componentes de canalización](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="14345-118">[Accessing SOAP Headers in WCF Messages with Pipeline Components](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md) </span></span>  
 <span data-ttu-id="14345-119">[Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="14345-119">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="14345-120">Encabezados SOAP con servicios WCF consumidos</span><span class="sxs-lookup"><span data-stu-id="14345-120">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)