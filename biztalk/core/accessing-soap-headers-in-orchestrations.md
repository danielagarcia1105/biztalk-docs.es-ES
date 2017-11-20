---
title: Obtener acceso a los encabezados SOAP en orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, properties
- orchestrations, SOAP headers
ms.assetid: 91fe053a-3f16-497c-b4bb-5fb54bec62e5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 516b2bcc57bef507a028f30c61fd329a5fd7a598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="accessing-soap-headers-in-orchestrations"></a><span data-ttu-id="95606-102">Obtener acceso a los encabezados SOAP en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="95606-102">Accessing SOAP Headers in Orchestrations</span></span>
<span data-ttu-id="95606-103">Puede obtener acceso a las propiedades de contexto de encabezados SOAP en orquestaciones para encabezados SOAP definidos y desconocidos.</span><span class="sxs-lookup"><span data-stu-id="95606-103">You can access the SOAP header context properties in orchestrations for defined and unknown SOAP headers.</span></span> <span data-ttu-id="95606-104">Para obtener más información sobre propiedades de contexto y esquemas de propiedades, vea [esquemas de propiedades](../core/property-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="95606-104">For more information about property schemas and context properties, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
## <a name="defined-soap-header-context-properties"></a><span data-ttu-id="95606-105">Propiedades de contexto de encabezado SOAP definidas</span><span class="sxs-lookup"><span data-stu-id="95606-105">Defined SOAP header context properties</span></span>  
 <span data-ttu-id="95606-106">Las propiedades de contexto de encabezado SOAP definidas en orquestaciones requieren un esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="95606-106">The defined SOAP header context properties in orchestrations require a property schema.</span></span> <span data-ttu-id="95606-107">El esquema de propiedad debe tener el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**y el **Property Schema Base** propiedad establecida en  **MessageContextPropertyBase**.</span><span class="sxs-lookup"><span data-stu-id="95606-107">The property schema must have the target namespace **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**, and the **Property Schema Base** property set to **MessageContextPropertyBase**.</span></span> <span data-ttu-id="95606-108">Cada nombre de elemento raíz en el esquema de propiedad debe coincidir con el nombre del elemento raíz del encabezado SOAP definido.</span><span class="sxs-lookup"><span data-stu-id="95606-108">Each root element name in the property schema must match the root element name of the defined SOAP header.</span></span> <span data-ttu-id="95606-109">A continuación, puede tener acceso a los valores de las propiedades de contexto mediante el espacio de nombres del esquema de propiedad y el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="95606-109">You can then access the values of the context properties using the namespace of the property schema and the property name.</span></span> <span data-ttu-id="95606-110">El espacio de nombres del esquema de propiedad es diferente del espacio de nombres de destino mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="95606-110">The namespace of the property schema is different from the target namespace listed above.</span></span> <span data-ttu-id="95606-111">Aunque el espacio de nombres del esquema de propiedad puede ser cualquier cadena, normalmente es el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="95606-111">Although the namespace of the property schema can be any string, it usually defaults to the name of the project.</span></span>  
  
 <span data-ttu-id="95606-112">En el ejemplo siguiente se muestra el acceso a la propiedad de contexto del encabezado SOAP para un espacio de nombres del esquema de propiedad **SOAPHeader**y el nombre de propiedad **OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="95606-112">The following example shows accessing the SOAP header context property for a property schema namespace, **SOAPHeader**, and the property name **OrigDest**:</span></span>  
  
```  
stringVar = requestMessageInstance(SOAPHeader.OrigDest);  
```  
  
> [!NOTE]
>  <span data-ttu-id="95606-113">Los encabezados SOAP definidos se tratan como encabezados "in" o "out".</span><span class="sxs-lookup"><span data-stu-id="95606-113">Defined SOAP headers are treated either as "in" or "out" headers.</span></span> <span data-ttu-id="95606-114">Si el asistente define el mismo encabezado SOAP para el mensaje de solicitud y de respuesta, el asistente no devolverá automáticamente el valor entrante en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="95606-114">If the wizard defines the same SOAP header for the request and response message, the wizard does not automatically return the incoming value in the response.</span></span> <span data-ttu-id="95606-115">Debe copiar explícitamente la propiedad de contexto del encabezado SOAP del mensaje de solicitud en la propiedad de contexto del encabezado SOAP del mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="95606-115">You must explicity copy the SOAP header context property of the request message to the SOAP header context property of the response message.</span></span>  
  
## <a name="copying-soap-header-context-property-of-incoming-message"></a><span data-ttu-id="95606-116">Copiar la propiedad de contexto del encabezado SOAP del mensaje entrante</span><span class="sxs-lookup"><span data-stu-id="95606-116">Copying SOAP header context property of incoming message</span></span>  
 <span data-ttu-id="95606-117">Puede copiar la propiedad de contexto del encabezado SOAP de un mensaje entrante en la misma propiedad de contexto del encabezado SOAP del mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="95606-117">You can copy the SOAP header context property of an incoming message to the same SOAP header context property of the response message.</span></span>  
  
 <span data-ttu-id="95606-118">El siguiente ejemplo muestra cómo copiar la propiedad de contexto del encabezado SOAP:</span><span class="sxs-lookup"><span data-stu-id="95606-118">The following example shows copying the SOAP header context property:</span></span>  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = RequestMessageInstance(SOAPHeader.OrigDest);  
```  
  
 <span data-ttu-id="95606-119">Cuando se crean encabezados SOAP para la respuesta SOAP, asegúrese de que crea los encabezados SOAP correctamente.</span><span class="sxs-lookup"><span data-stu-id="95606-119">When you create SOAP headers for the SOAP response, you ensure that you create your SOAP headers correctly.</span></span> <span data-ttu-id="95606-120">El adaptador de SOAP no comprueba el contenido de las propiedades de contexto del encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="95606-120">The SOAP adapter does not verify the contents of the SOAP header context properties.</span></span> <span data-ttu-id="95606-121">Si los valores de los encabezados SOAP de respuesta son incorrectos, el adaptador de SOAP no podrá enviar el mensaje de respuesta al consumidor del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="95606-121">If the values of the response SOAP headers are incorrect, the SOAP adapter cannot send the response message to the consumer of your Web service.</span></span>  
  
## <a name="unknown-soap-header-context-property"></a><span data-ttu-id="95606-122">Propiedad de contexto de encabezado SOAP desconocida</span><span class="sxs-lookup"><span data-stu-id="95606-122">Unknown SOAP header context property</span></span>  
 <span data-ttu-id="95606-123">La propiedad de contexto de encabezado SOAP desconocida no requiere un esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="95606-123">The unknown SOAP header context property does not require a property schema.</span></span> <span data-ttu-id="95606-124">Puede tener acceso a esta propiedad de contexto global **SOAP. UnknownHeaders**.</span><span class="sxs-lookup"><span data-stu-id="95606-124">You can access this global context property **SOAP.UnknownHeaders**.</span></span>  
  
 <span data-ttu-id="95606-125">En el ejemplo siguiente se muestra el acceso a la propiedad de contexto de encabezado SOAP desconocida **SOAP. UnknownHeaders**:</span><span class="sxs-lookup"><span data-stu-id="95606-125">The following example shows accessing the unknown SOAP header context property **SOAP.UnknownHeaders**:</span></span>  
  
```  
stringVar = RequestMessageInstance(SOAP.UnknownHeaders);  
```  
  
 <span data-ttu-id="95606-126">Los valores contenidos en las propiedades de contexto son cadenas que contienen datos XML.</span><span class="sxs-lookup"><span data-stu-id="95606-126">The values contained in the context properties are strings containing XML data.</span></span> <span data-ttu-id="95606-127">La manera más sencilla de obtener acceso a estos datos consiste en usar el Editor de expresiones de BizTalk en un **asignación de mensajes** o **expresión** y dar forma a cargar la cadena en un **XmlDocument** y usar Consultas XPATH para tener acceso a campos específicos.</span><span class="sxs-lookup"><span data-stu-id="95606-127">The simplest way to access this data is to use the BizTalk Expression Editor in a **Message Assignment** or **Expression** shape and load the string in an **XmlDocument** and use XPATH queries to access specific fields.</span></span> <span data-ttu-id="95606-128">Para obtener más información, creación de documentos XML en el Editor de expresiones de BizTalk, consulte [lenguaje XLANG s](../core/xlang-s-language.md).</span><span class="sxs-lookup"><span data-stu-id="95606-128">For more information creating XML documents in the BizTalk Expression Editor, see [XLANG-s Language](../core/xlang-s-language.md).</span></span>  
  
 <span data-ttu-id="95606-129">Las propiedades de contexto están asociadas con un mensaje concreto.</span><span class="sxs-lookup"><span data-stu-id="95606-129">Context properties are associated with a particular message.</span></span> <span data-ttu-id="95606-130">El motor de mensajería no asigna automáticamente los valores de los encabezados SOAP desconocidos desde el mensaje de solicitud al mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="95606-130">The Messaging Engine does not automatically map the values of known SOAP headers from the request message to the response message.</span></span> <span data-ttu-id="95606-131">Al crear el mensaje de respuesta para un servicio Web, debe establecer específicamente los valores del encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="95606-131">When creating the response message for a Web service, you must specifically set the SOAP header values.</span></span> <span data-ttu-id="95606-132">El comando siguiente es el método más sencillo de establecer una propiedad de contexto del encabezado SOAP:</span><span class="sxs-lookup"><span data-stu-id="95606-132">The following command is the simplest method of setting a SOAP header context property:</span></span>  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = "<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination xmlns=\"\">Home</Origination><Destination xmlns=\"\">Work</Destination> </OrigDest>"  
```  
  
 <span data-ttu-id="95606-133">También puede conseguirlo mediante la creación de un **XmlDocument** y escribir el valor de cadena de la **XmlDocument** a la propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="95606-133">You can also achieve this by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95606-134">Si el **SOAP. UnknownHeaders** propiedad es nula, BizTalk devuelve automáticamente los encabezados desconocidos recibidos en la solicitud SOAP en la respuesta SOAP.</span><span class="sxs-lookup"><span data-stu-id="95606-134">If the **SOAP.UnknownHeaders** property is null, BizTalk automatically returns the unknown headers received in the SOAP request to the SOAP response.</span></span> <span data-ttu-id="95606-135">Si el **SOAP. UnknownHeaders** propiedad de contexto del mensaje de respuesta no es null, a continuación, BizTalk devuelve ese valor a la respuesta SOAP.</span><span class="sxs-lookup"><span data-stu-id="95606-135">If the **SOAP.UnknownHeaders** context property on the response message is not null, then BizTalk returns that value to the SOAP response.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95606-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="95606-136">See Also</span></span>  
 [<span data-ttu-id="95606-137">Encabezados SOAP con servicios Web publicados</span><span class="sxs-lookup"><span data-stu-id="95606-137">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)