---
title: Usar encabezados SOAP en orquestaciones | Documentos de Microsoft
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
- SOAP headers, creating
- SOAP headers, properties
- Web services, SOAP headers
- orchestrations, SOAP headers
- creating, SOAP headers
ms.assetid: 4754dd23-386b-4093-8ea4-4da6b4d9279c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faae7013c824926adea67feab296e1993f93e326
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-orchestrations"></a><span data-ttu-id="bccee-102">Usar encabezados SOAP en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="bccee-102">Using SOAP Headers in Orchestrations</span></span>
<span data-ttu-id="bccee-103">Las orquestaciones usan esquemas de propiedades para definir las propiedades de contexto de encabezados SOAP.</span><span class="sxs-lookup"><span data-stu-id="bccee-103">Orchestrations use property schemas to define SOAP header context properties.</span></span> <span data-ttu-id="bccee-104">Use el Editor de BizTalk para establecer las propiedades de contexto de encabezados SOAP.</span><span class="sxs-lookup"><span data-stu-id="bccee-104">You use the BizTalk Editor to set SOAP header context properties.</span></span>  
  
## <a name="defining-soap-header-context-properties-with-property-schemas"></a><span data-ttu-id="bccee-105">Definir propiedades de contexto de encabezados SOAP con esquemas de propiedades</span><span class="sxs-lookup"><span data-stu-id="bccee-105">Defining SOAP header context properties with property schemas</span></span>  
 <span data-ttu-id="bccee-106">Necesitará un esquema de propiedades para usar propiedades de contexto de encabezados SOAP definidas en orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="bccee-106">You need a property schema to use defined SOAP header context properties in orchestrations.</span></span> <span data-ttu-id="bccee-107">El esquema de propiedad debe tener el espacio de nombres de destino de **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**y el **Property Schema Base** propiedad establecida en  **MessageContextPropertyBase**.</span><span class="sxs-lookup"><span data-stu-id="bccee-107">The property schema must have the target namespace of **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**, and the **Property Schema Base** property set to **MessageContextPropertyBase**.</span></span> <span data-ttu-id="bccee-108">Cada nombre de elemento raíz del esquema de propiedades debe coincidir con el nombre de elemento raíz del encabezado SOAP definido.</span><span class="sxs-lookup"><span data-stu-id="bccee-108">Each root element name in the property schema must match the root element name in the defined SOAP header.</span></span> <span data-ttu-id="bccee-109">Entonces podrá establecer valores para las propiedades de contexto que usen el espacio de nombres del esquema de propiedades y el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bccee-109">You can then set values for the context properties using the namespace of the property schema and the property name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bccee-110">El espacio de nombres del esquema de propiedad es diferente del espacio de nombres del esquema de destino (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**).</span><span class="sxs-lookup"><span data-stu-id="bccee-110">The namespace of the property schema is different from the namespace of the target schema (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**).</span></span> <span data-ttu-id="bccee-111">Su espacio de nombres puede ser cualquier cadena; no obstante, suele tener de forma predeterminada el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="bccee-111">Your namespace can be any string; however, it usually defaults to the name of the project.</span></span>  
  
 <span data-ttu-id="bccee-112">El siguiente código muestra cómo asignar una propiedad de contexto de encabezado SOAP donde es el espacio de nombres del esquema de propiedad **SOAPHeader** con un nombre de propiedad de **OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="bccee-112">The following code shows assigning a SOAP header context property where the property schema namespace is **SOAPHeader** with a property name of **OrigDest**:</span></span>  
  
```  
requestMessageInstance(SOAPHeader.OrigDest) = stringVar;  
```  
  
 <span data-ttu-id="bccee-113">Para obtener más información sobre propiedades de contexto y esquemas de propiedades, vea [esquemas de propiedades](../core/property-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="bccee-113">For more information about property schemas and context properties, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
## <a name="using-biztalk-editor-to-set-soap-header-context-properties"></a><span data-ttu-id="bccee-114">Usar el Editor de BizTalk para establecer las propiedades de contexto de encabezados SOAP</span><span class="sxs-lookup"><span data-stu-id="bccee-114">Using BizTalk Editor to set SOAP header context properties</span></span>  
 <span data-ttu-id="bccee-115">Respecto a las orquestaciones, las propiedades de contexto del encabezado SOAP están establecidas como cadenas que contienen datos XML.</span><span class="sxs-lookup"><span data-stu-id="bccee-115">For orchestrations, the SOAP header context properties are set to strings that contain XML data.</span></span> <span data-ttu-id="bccee-116">Establezca estas cadenas mediante el Editor de expresiones de BizTalk en un **asignación de mensajes** o **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="bccee-116">You set these strings using the BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span>  
  
 <span data-ttu-id="bccee-117">El siguiente ejemplo muestra la configuración de la cadena de la propiedad de contexto:</span><span class="sxs-lookup"><span data-stu-id="bccee-117">The following example shows the string setting the context property:</span></span>  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = "<?xml version=\"1.0\"?>  
<OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
<Origination>Home</Origination>  
<Destination>Work</Destination>  
</OrigDest>"  
```  
  
## <a name="using-biztalk-editor-to-create-an-instance-of-a-soap-header-root-element"></a><span data-ttu-id="bccee-118">Usar el Editor de BizTalk para crear una instancia de un elemento raíz de encabezado SOAP</span><span class="sxs-lookup"><span data-stu-id="bccee-118">Using BizTalk Editor to create an instance of a SOAP header root element</span></span>  
 <span data-ttu-id="bccee-119">La configuración del encabezado SOAP a la cadena correcta puede ser una tarea difícil.</span><span class="sxs-lookup"><span data-stu-id="bccee-119">Setting the SOAP header to the correct string can be difficult.</span></span> <span data-ttu-id="bccee-120">Al agregar una referencia Web a un proyecto de BizTalk, todas las partes del mensaje Web se agregan a Reference.xsd como elementos raíz.</span><span class="sxs-lookup"><span data-stu-id="bccee-120">When adding a Web reference to a BizTalk project, all complex Web message parts are added to Reference.xsd as root elements.</span></span> <span data-ttu-id="bccee-121">Reference.xsd también contiene elementos raíz para cada encabezado SOAP definido.</span><span class="sxs-lookup"><span data-stu-id="bccee-121">Reference.xsd also contains root elements for each defined SOAP header.</span></span> <span data-ttu-id="bccee-122">Para asegurar que establece el encabezado SOAP con la cadena correcta, debe usar el Editor de BizTalk para crear una instancia del elemento raíz del encabezado SOAP para Reference.xsd.</span><span class="sxs-lookup"><span data-stu-id="bccee-122">To ensure that you set the SOAP header with the correct string, you should use BizTalk Editor to create an instance of the SOAP header root element for Reference.xsd.</span></span> <span data-ttu-id="bccee-123">Puede usar los datos de instancia generados directamente en los datos de instancia para contener los datos reales.</span><span class="sxs-lookup"><span data-stu-id="bccee-123">You can use the generated instance data directly or the instance data to contain your real data.</span></span>  
  
 <span data-ttu-id="bccee-124">Para obtener más información acerca de cómo utilizar el Editor de BizTalk para generar datos de instancia, consulte [cómo generar mensajes de instancia](../core/how-to-generate-instance-messages.md).</span><span class="sxs-lookup"><span data-stu-id="bccee-124">For more information about using the BizTalk Editor to generate instance data, see [How to Generate Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a><span data-ttu-id="bccee-125">Crear un XmlDocument para establecer propiedades de contexto</span><span class="sxs-lookup"><span data-stu-id="bccee-125">Creating an XmlDocument to set context properties</span></span>  
 <span data-ttu-id="bccee-126">Puede establecer las propiedades de contexto mediante la creación de un **XmlDocument** y escribir el valor de cadena de la **XmlDocument** a la propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="bccee-126">You can set context properties by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span> <span data-ttu-id="bccee-127">Declare una variable de tipo **XMLDocument** y asigne los datos XML.</span><span class="sxs-lookup"><span data-stu-id="bccee-127">You declare a variable of type **XMLDocument** and assign the XML data.</span></span>  
  
 <span data-ttu-id="bccee-128">En el ejemplo siguiente se muestra la configuración de declaración de una variable de tipo **XMLDocument** y asigne los datos XML:</span><span class="sxs-lookup"><span data-stu-id="bccee-128">The following example shows setting a declaring a variable of type **XMLDocument** and assign the XML data:</span></span>  
  
```  
xmlDoc.LoadXml("<?xml version=\"1.0\"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination>Home</Origination><Destination>Work</Destination></OrigDest>");  
```  
  
 <span data-ttu-id="bccee-129">El siguiente ejemplo muestra la configuración de la propiedad de contexto:</span><span class="sxs-lookup"><span data-stu-id="bccee-129">The following example shows setting the context property:</span></span>  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = xmlDoc.OuterXml;  
```  
  
 <span data-ttu-id="bccee-130">Para obtener más información acerca de cómo utilizar el Editor de expresiones de BizTalk, consulte [requisitos y limitaciones para las expresiones](../core/requirements-and-limitations-for-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="bccee-130">For more information about using BizTalk Expression Editor, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span> <span data-ttu-id="bccee-131">Para obtener más información sobre cómo llamar a las clases. NET, vea [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).</span><span class="sxs-lookup"><span data-stu-id="bccee-131">For more information about calling .NET classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="creating-soap-headers-for-a-soap-request"></a><span data-ttu-id="bccee-132">Crear encabezados SOAP para una solicitud SOAP</span><span class="sxs-lookup"><span data-stu-id="bccee-132">Creating SOAP headers for a SOAP request</span></span>  
 <span data-ttu-id="bccee-133">Cuando cree encabezados SOAP para la solicitud SOAP, debe asegurarse de que ha creado los encabezados SOAP correctamente.</span><span class="sxs-lookup"><span data-stu-id="bccee-133">When you create SOAP headers for the SOAP request, you must ensure that you have correctly created the SOAP headers.</span></span> <span data-ttu-id="bccee-134">El adaptador de SOAP no comprueba el contenido de las propiedades de contexto del encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="bccee-134">The SOAP adapter does not verify the contents of the SOAP header context properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bccee-135">Si el encabezado SOAP es incorrecto, BizTalk no puede enviar la solicitud SOAP al servicio Web.</span><span class="sxs-lookup"><span data-stu-id="bccee-135">If the SOAP header is incorrect, BizTalk cannot send the SOAP request to the Web service.</span></span>  
  
 <span data-ttu-id="bccee-136">La respuesta SOAP que devuelve BizTalk al servicio Web también puede contener encabezados SOAP.</span><span class="sxs-lookup"><span data-stu-id="bccee-136">The SOAP response that BizTalk returns to the Web service may also contain SOAP headers.</span></span> <span data-ttu-id="bccee-137">Sólo puede obtener acceso a estos encabezados SOAP si son encabezados SOAP definidos.</span><span class="sxs-lookup"><span data-stu-id="bccee-137">You can only access these SOAP headers if they are defined SOAP headers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bccee-138">Los servicios Web consumidos sólo admiten encabezados SOAP definidos.</span><span class="sxs-lookup"><span data-stu-id="bccee-138">Consumed Web services support only defined SOAP headers.</span></span>  
  
 <span data-ttu-id="bccee-139">Para obtener más información acerca de los encabezados SOAP definidos, consulte [Using SOAP Headers](../core/using-soap-headers.md).</span><span class="sxs-lookup"><span data-stu-id="bccee-139">For more information about defined SOAP headers, see [Using SOAP Headers](../core/using-soap-headers.md).</span></span> <span data-ttu-id="bccee-140">Los encabezados SOAP de respuesta están establecidos como propiedades de contexto que usan la misma sintaxis que los encabezados SOAP de solicitud.</span><span class="sxs-lookup"><span data-stu-id="bccee-140">The response SOAP headers are set to context properties using the same syntax as the request SOAP headers.</span></span>  
  
 <span data-ttu-id="bccee-141">El siguiente código muestra cómo obtener acceso a los encabezados SOAP de respuesta:</span><span class="sxs-lookup"><span data-stu-id="bccee-141">The following code shows how to access the response SOAP headers:</span></span>  
  
```  
stringVar = ResponseMessageInstance(SOAPHeader.OrigDest);  
```  
  
 <span data-ttu-id="bccee-142">Los valores contenidos en las propiedades de contexto son cadenas que contienen datos XML.</span><span class="sxs-lookup"><span data-stu-id="bccee-142">The values contained in the context properties are strings containing XML data.</span></span> <span data-ttu-id="bccee-143">Establezca estas cadenas mediante el Editor de expresiones de BizTalk en un **asignación de mensajes** o **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="bccee-143">You set these strings using BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span> <span data-ttu-id="bccee-144">Cargar la cadena en un **XmlDocument** y utilizar consultas XPath para obtener acceso a campos específicos.</span><span class="sxs-lookup"><span data-stu-id="bccee-144">You load the string in an **XmlDocument** and use XPath queries to access specific fields.</span></span>  
  
 <span data-ttu-id="bccee-145">Para obtener más información acerca de cómo crear documentos XML en el Editor de expresiones de BizTalk, consulte [lenguaje XLANG s](../core/xlang-s-language.md).</span><span class="sxs-lookup"><span data-stu-id="bccee-145">For more information about creating XML documents in BizTalk Expression Editor, see [XLANG-s Language](../core/xlang-s-language.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bccee-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="bccee-146">See Also</span></span>  
 <span data-ttu-id="bccee-147">[Lenguaje XLANG-s.](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="bccee-147">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 [<span data-ttu-id="bccee-148">Encabezados SOAP con servicios Web consumidos</span><span class="sxs-lookup"><span data-stu-id="bccee-148">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)