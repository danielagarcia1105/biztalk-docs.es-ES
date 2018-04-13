---
title: Especificar el cuerpo del mensaje para los adaptadores de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF adapters, SOAP messages
- messages, WCF adapters
- WCF adapters, message bodies
- SOAP messages, WCF adapters
ms.assetid: b20364b7-0365-4636-b4d6-bde9c69b8dcb
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 109ad486baa542aff3cd1c4a44804ff2fd79aac5
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="specifying-the-message-body-for-the-wcf-adapters"></a><span data-ttu-id="bd3d0-102">Especificar el cuerpo del mensaje para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="bd3d0-102">Specifying the Message Body for the WCF Adapters</span></span>
<span data-ttu-id="bd3d0-103">Puede usar el **mensajes** ficha en los adaptadores de WCF para especificar cómo se extrae el cuerpo del mensaje de BizTalk de un mensaje SOAP entrante y el cuerpo del mensaje de BizTalk se coloca en un mensaje SOAP saliente.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-103">You can use the **Messages** tab in the WCF adapters to specify how the BizTalk message body is extracted from an incoming SOAP message, and how the BizTalk message body is placed in an outgoing SOAP message.</span></span>  
  
## <a name="specifying-how-the-biztalk-message-body-is-extracted-from-an-incoming-soap-message"></a><span data-ttu-id="bd3d0-104">Especificar cómo se extrae el cuerpo del mensaje de BizTalk de un mensaje SOAP entrante</span><span class="sxs-lookup"><span data-stu-id="bd3d0-104">Specifying How the BizTalk Message Body Is Extracted from an Incoming SOAP Message</span></span>  
 <span data-ttu-id="bd3d0-105">Puede controlar cómo crear el cuerpo del mensaje de BizTalk entrante a partir de mensajes SOAP que llegan a través de los adaptadores de WCF.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-105">You can control how to create the inbound BizTalk message body from the SOAP messages incoming through the WCF adapters.</span></span> <span data-ttu-id="bd3d0-106">Las ilustraciones siguientes muestran el **mensajes** adaptadores de envío y la recepción de las pestañas de WCF-NetNamedPipe como ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-106">The following figures show the **Messages** tabs of the WCF-NetNamedPipe receive adapter and send adapter as examples.</span></span>  
  
 <span data-ttu-id="bd3d0-107">![Adaptadores de recepción de la pestaña mensajes en WCF](../core/media/abbaccfc-092c-42c6-9207-fa1af28912ac.gif "abbaccfc-092c-42c6-9207-fa1af28912ac")</span><span class="sxs-lookup"><span data-stu-id="bd3d0-107">![The Messages tab in the WCF receive adapters](../core/media/abbaccfc-092c-42c6-9207-fa1af28912ac.gif "abbaccfc-092c-42c6-9207-fa1af28912ac")</span></span>  
  
 <span data-ttu-id="bd3d0-108">![Adaptadores de envío de la pestaña mensajes en WCF](../core/media/58e1d490-5bd9-4571-87b1-4dea6dbfe2de.gif "58e1d490-5bd9-4571-87b1-4dea6dbfe2de")</span><span class="sxs-lookup"><span data-stu-id="bd3d0-108">![The Messages tab in the WCF send adapters](../core/media/58e1d490-5bd9-4571-87b1-4dea6dbfe2de.gif "58e1d490-5bd9-4571-87b1-4dea6dbfe2de")</span></span>  
  
 <span data-ttu-id="bd3d0-109">Para especificar cómo se crea el cuerpo del mensaje de BizTalk, seleccione una de las siguientes opciones en el **cuerpo del mensaje entrante de BizTalk** sección en las ilustraciones anteriores:</span><span class="sxs-lookup"><span data-stu-id="bd3d0-109">To specify how to create the BizTalk message body, select one of the following options in the **Inbound BizTalk message body** section in the preceding figures:</span></span>  
  
-   <span data-ttu-id="bd3d0-110">**Sobre--entero \<soap: Envelope\>**.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-110">**Envelope -- entire \<soap:Envelope\>**.</span></span> <span data-ttu-id="bd3d0-111">Utiliza SOAP **sobres** elemento de un mensaje entrante para crear la parte del cuerpo de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-111">Uses the SOAP **Envelope** element of an incoming message to create the BizTalk message body part.</span></span> <span data-ttu-id="bd3d0-112">El mensaje entrante completo se convierte en el cuerpo del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-112">The entire incoming message becomes the BizTalk message body.</span></span> <span data-ttu-id="bd3d0-113">Use esta opción para crear el cuerpo del mensaje de BizTalk incorporando todos los encabezados.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-113">Use this option to create the BizTalk message body incorporating all the headers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd3d0-114">Los encabezados SOAP se colocan en el contexto del mensaje, pero no se promocionan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-114">The SOAP headers are placed in the message context, but they are not promoted automatically.</span></span> <span data-ttu-id="bd3d0-115">La promoción se puede realizar en un componente de canalización personalizada.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-115">Promotion can be done in a custom pipeline component.</span></span>  
  
-   <span data-ttu-id="bd3d0-116">**Cuerpo--contenido \<soap: Body\> elemento**.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-116">**Body -- contents of \<soap:Body\> element**.</span></span> <span data-ttu-id="bd3d0-117">Utiliza el contenido del mensaje SOAP **cuerpo** elemento de un mensaje entrante para crear la parte del cuerpo de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-117">Uses the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part.</span></span> <span data-ttu-id="bd3d0-118">Si el elemento **Body** tiene varios elementos secundarios, sólo el primero de ellos será la parte del cuerpo del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-118">If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.</span></span>  
  
-   <span data-ttu-id="bd3d0-119">**Ruta--contenido ubicado por la ruta de cuerpo**.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-119">**Path -- content located by body path**.</span></span> <span data-ttu-id="bd3d0-120">Usa la expresión de ruta de cuerpo en el **expresión de ruta de acceso del cuerpo** cuadro de texto para crear la parte del cuerpo de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-120">Uses the body path expression in the **Body path expression** text box to create the BizTalk message body part.</span></span> <span data-ttu-id="bd3d0-121">Esta expresión se evalúa con respecto al elemento secundario inmediato del elemento **Cuerpo** de SOAP de un mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-121">The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message.</span></span> <span data-ttu-id="bd3d0-122">Cuando los mensajes entrantes incluyen datos binarios, se puede usar esta opción para que el cuerpo del mensaje de BizTalk incluya únicamente los datos binarios sin etiquetas.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-122">When incoming messages have binary data, you can use this option for the BizTalk message body to include only the binary data without any tags.</span></span>  
  
 <span data-ttu-id="bd3d0-123">Cuando el **ruta--contenido ubicado por la ruta de cuerpo** opción está seleccionada, el **codificación de nodo** propiedad se puede configurar para especificar el tipo de codificación esperado para el nodo especificado por la expresión de ruta de cuerpo el **expresión de ruta de acceso del cuerpo** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-123">When the **Path -- content located by body path** option is selected, the **Node encoding** property can be configured to specify the expected encoding type for the node specified by the body path expression in the **Body path expression** text box.</span></span> <span data-ttu-id="bd3d0-124">Si la expresión de ruta de cuerpo coincide con más de un elemento, sólo se usa el primer elemento coincidente.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-124">If the body path expression matches more than one element, only the first matched element is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd3d0-125">Para el **expresión de ruta de acceso del cuerpo** sólo el XPath que se admiten expresiones adecuadas para el procesamiento progresivo de XML de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-125">For the **body path expression** property, only the XPath expressions suitable for forward-only processing of XML are supported.</span></span> <span data-ttu-id="bd3d0-126">Para obtener más información sobre las expresiones XPath disponibles para esta propiedad, vea "El mejor de ambos mundos: combinación de XPath con el XmlReader" en [ http://go.microsoft.com/fwlink/?LinkID=75701 ](http://go.microsoft.com/fwlink/?LinkID=75701).</span><span class="sxs-lookup"><span data-stu-id="bd3d0-126">For more information about the XPath expressions available for this property, see "The Best of Both Worlds: Combining XPath with the XmlReader" at [http://go.microsoft.com/fwlink/?LinkID=75701](http://go.microsoft.com/fwlink/?LinkID=75701).</span></span>  
  
 <span data-ttu-id="bd3d0-127">Si el **ruta--contenido ubicado por la ruta de cuerpo** opción está seleccionada y el **codificación de nodo** propiedad está establecida en **cadena**, los adaptadores de WCF esperan que el nodo coincidente tiene UTF-8 datos de caracteres codificados.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-127">If the **Path -- content located by body path** option is selected and the **Node encoding** property is set to **String**, the WCF adapters expect that the matched node has UTF-8 encoded character data.</span></span> <span data-ttu-id="bd3d0-128">Si los mensajes entrantes incluyen caracteres de escape datos de caracteres para los caracteres especiales XML como \< y \>, los adaptadores de WCF restauran los datos de carácter de escape al crear la parte del cuerpo de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-128">If the incoming messages include escaped character data for the XML special characters such as \< and \>, the WCF adapters restore the escaped character data when creating the BizTalk message body part.</span></span> <span data-ttu-id="bd3d0-129">Por ejemplo, si el nodo coincidente escape como datos de caracteres **&lt;FirstName&gt;CONTOSO&lt;/FirstName&gt;** los adaptadores WCF crean **\< FirstName\>CONTOSO\</FirstName\>** cuerpo del mensaje en la entrada de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-129">For example, if the matched node has escaped character data such as **&lt;FirstName&gt;CONTOSO&lt;/FirstName&gt;** the WCF adapters create **\<FirstName\>CONTOSO\</FirstName\>** in the inbound BizTalk message body.</span></span>  
  
 <span data-ttu-id="bd3d0-130">Si el **ruta--contenido ubicado por la ruta de cuerpo** opción está seleccionada y el **codificación de nodo** propiedad está establecida en **hexadecimal** o **Base64**, el nodo coincidente puede tener válido **BinHex** o **Base64** secuencia.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-130">If the **Path -- content located by body path** option is selected and the **Node encoding** property is set to **Hex** or **Base64**, the matched node can have a valid **BinHex** or **Base64** sequence.</span></span> <span data-ttu-id="bd3d0-131">Si el nodo coincidente tiene una secuencia no válida, el cliente WCF recibe **FaultException**, un mensaje de error se registra en el registro de eventos en el equipo de BizTalk Server y se suspende ningún mensaje.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-131">If the matched node has an invalid sequence, the WCF client receives **FaultException**, an error message is logged in the event log on your BizTalk Server computer, and no message is suspended.</span></span>  
  
 <span data-ttu-id="bd3d0-132">Si el **ruta--contenido ubicado por la ruta de cuerpo** opción está seleccionada y el **codificación de nodo** propiedad está establecida en **XML**, los adaptadores WCF crean el cuerpo del mensaje de BizTalk con el XML externo del nodo seleccionado por la expresión de ruta de acceso de cuerpo en el **expresión de ruta de acceso del cuerpo** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-132">If the **Path -- content located by body path** option is selected and the **Node encoding** property is set to **XML**, the WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in the **Body path expression** text box.</span></span>  
  
 <span data-ttu-id="bd3d0-133">Si el nodo coincidente no tiene datos codificados como se especifica en el **codificación de nodo** propiedad, se crea un cuerpo de mensaje de BizTalk entrante vacío.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-133">If the matched node does not have data encoded as specified in the **Node encoding** property, an empty inbound BizTalk message body is created.</span></span>  
  
 <span data-ttu-id="bd3d0-134">Por ejemplo, suponga que los adaptadores de envío WCF reciben el mensaje de SOAP siguiente procedente de clientes de WCF:</span><span class="sxs-lookup"><span data-stu-id="bd3d0-134">For example, suppose the WCF send adapters receive the following SOAP message from WCF clients:</span></span>  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/OrderRefresh</a:Action>   
    <a:MessageID>urn:uuid:59e74507-66d0-4d50-be70-c3ec248b6f78</a:MessageID>   
    <a:ReplyTo>  
       <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>   
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessServiceBizTalk</a:To>   
  </s:Header>  
  <s:Body>  
    <Order xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
     <OrderDetail>  
       <CustomerID>CONTOSO</CustomerID>   
       <OrderID>00000000</OrderID>   
     </OrderDetail>  
    </Order>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="bd3d0-135">Si configura el **cuerpo del mensaje entrante de BizTalk** sección tal y como se muestra en la siguiente tabla, el mensaje SOAP entrante anterior se convierte en la parte del cuerpo de mensaje de BizTalk entrante.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-135">If you configure the **Inbound BizTalk message body** section as shown in the following table, the previous incoming SOAP message becomes the inbound BizTalk message body part.</span></span>  
  
|<span data-ttu-id="bd3d0-136">Cuerpo de mensaje entrante de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bd3d0-136">Inbound BizTalk message body</span></span>|<span data-ttu-id="bd3d0-137">Expresión de ruta de cuerpo</span><span class="sxs-lookup"><span data-stu-id="bd3d0-137">Body path expression</span></span>|<span data-ttu-id="bd3d0-138">Codificación de nodo</span><span class="sxs-lookup"><span data-stu-id="bd3d0-138">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="bd3d0-139">**Sobre--entero \<soap: Envelope\>**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-139">**Envelope -- entire \<soap:Envelope\>**</span></span>|<span data-ttu-id="bd3d0-140">N/D</span><span class="sxs-lookup"><span data-stu-id="bd3d0-140">N/A</span></span>|<span data-ttu-id="bd3d0-141">N/D</span><span class="sxs-lookup"><span data-stu-id="bd3d0-141">N/A</span></span>|  
  
 <span data-ttu-id="bd3d0-142">Si configura el **cuerpo del mensaje de BizTalk** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean la parte de cuerpo de mensaje de BizTalk entrante para que contenga únicamente la **orden** elemento en la versión anterior mensaje SOAP entrante.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-142">If you configure the **BizTalk message body** section as shown in the following table, the WCF adapters create the inbound BizTalk message body part to contain only the **Order** element in the previous incoming SOAP message.</span></span>  
  
|<span data-ttu-id="bd3d0-143">Cuerpo de mensaje entrante de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bd3d0-143">Inbound BizTalk message body</span></span>|<span data-ttu-id="bd3d0-144">Expresión de ruta de cuerpo</span><span class="sxs-lookup"><span data-stu-id="bd3d0-144">Body path expression</span></span>|<span data-ttu-id="bd3d0-145">Codificación de nodo</span><span class="sxs-lookup"><span data-stu-id="bd3d0-145">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="bd3d0-146">**Cuerpo--contenido \<soap: Body\> elemento**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-146">**Body -- contents of \<soap:Body\> element**</span></span>|<span data-ttu-id="bd3d0-147">N/D</span><span class="sxs-lookup"><span data-stu-id="bd3d0-147">N/A</span></span>|<span data-ttu-id="bd3d0-148">N/D</span><span class="sxs-lookup"><span data-stu-id="bd3d0-148">N/A</span></span>|  
  
 <span data-ttu-id="bd3d0-149">Si configura el **cuerpo del mensaje de BizTalk** sección tal y como se muestra en la tabla siguiente, los adaptadores de WCF esperan que el nodo de entrada que coincide con la expresión de ruta de cuerpo tendrá datos de caracteres con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-149">If you configure the **BizTalk message body** section as shown in the following table, the WCF adapters expect that the incoming node that the body path expression matches will have UTF-8 encoded character data.</span></span>  
  
|<span data-ttu-id="bd3d0-150">Cuerpo de mensaje entrante de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bd3d0-150">Inbound BizTalk message body</span></span>|<span data-ttu-id="bd3d0-151">Expresión de ruta de cuerpo</span><span class="sxs-lookup"><span data-stu-id="bd3d0-151">Body path expression</span></span>|<span data-ttu-id="bd3d0-152">Codificación de nodo</span><span class="sxs-lookup"><span data-stu-id="bd3d0-152">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="bd3d0-153">**Ruta--contenido ubicado por la ruta de cuerpo**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-153">**Path -- content located by body path**</span></span>|<span data-ttu-id="bd3d0-154">/\*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span><span class="sxs-lookup"><span data-stu-id="bd3d0-154">/\*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span></span>|<span data-ttu-id="bd3d0-155">**String**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-155">**String**</span></span>|  
  
 <span data-ttu-id="bd3d0-156">Para el mensaje SOAP entrante anterior, los adaptadores de WCF usan los datos de caracteres, **CONTOSO**, de la **CustomerID** elemento que se va a crear la parte del cuerpo de mensaje de BizTalk entrante.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-156">For the previous incoming SOAP message, the WCF adapters use the character data, **CONTOSO**, of the **CustomerID** element to create the inbound BizTalk message body part.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd3d0-157">No se puede utilizar la sintaxis abreviada de XPath, **/Order/OrderDetail/CustomerID**, para el mensaje SOAP entrante anterior.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-157">You cannot use the abbreviated syntax of XPath, **/Order/OrderDetail/CustomerID**, for the previous incoming SOAP message.</span></span> <span data-ttu-id="bd3d0-158">Esto es porque la sintaxis abreviada de XPath devuelve el nodo no declarado en un espacio de nombres y el **CustomerID** elemento del mensaje SOAP anterior se declara en el **http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess** espacio de nombres con espacios de nombres predeterminados.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-158">This is because the abbreviated syntax of XPath returns the node not declared in a namespace, and the **CustomerID** element in the previous SOAP message is declared in the **http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess** namespace by default namespaces.</span></span>  
  
 <span data-ttu-id="bd3d0-159">Si configura el **cuerpo del mensaje de BizTalk** sección tal y como se muestra en la siguiente tabla, el **CustomID** elemento en el mensaje SOAP entrante anterior debe tener válido **BinHex**o **Base64** secuencia.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-159">If you configure the **BizTalk message body** section as shown in the following table, the **CustomID** element in the previous incoming SOAP message should have a valid **BinHex** or **Base64** sequence.</span></span>  
  
|<span data-ttu-id="bd3d0-160">Cuerpo de mensaje entrante de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bd3d0-160">Inbound BizTalk message body</span></span>|<span data-ttu-id="bd3d0-161">Expresión de ruta de cuerpo</span><span class="sxs-lookup"><span data-stu-id="bd3d0-161">Body path expression</span></span>|<span data-ttu-id="bd3d0-162">Codificación de nodo</span><span class="sxs-lookup"><span data-stu-id="bd3d0-162">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="bd3d0-163">**Ruta--contenido ubicado por la ruta de cuerpo**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-163">**Path -- content located by body path**</span></span>|<span data-ttu-id="bd3d0-164">/\*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span><span class="sxs-lookup"><span data-stu-id="bd3d0-164">/\*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span></span>|<span data-ttu-id="bd3d0-165">**Hex** o **Base64**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-165">**Hex** or **Base64**</span></span>|  
  
 <span data-ttu-id="bd3d0-166">Si configura el **cuerpo del mensaje de BizTalk** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean el cuerpo del mensaje de BizTalk entrante para el mensaje SOAP entrante anterior tal como se muestra en el código después de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-166">If you configure the **BizTalk message body** section as shown in the following table, the WCF adapters create the inbound BizTalk message body for the previous incoming SOAP message as shown in the code after the table.</span></span>  
  
|<span data-ttu-id="bd3d0-167">Cuerpo de mensaje entrante de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bd3d0-167">Inbound BizTalk message body</span></span>|<span data-ttu-id="bd3d0-168">Expresión de ruta de cuerpo</span><span class="sxs-lookup"><span data-stu-id="bd3d0-168">Body path expression</span></span>|<span data-ttu-id="bd3d0-169">Codificación de nodo</span><span class="sxs-lookup"><span data-stu-id="bd3d0-169">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="bd3d0-170">**Ruta--contenido ubicado por la ruta de cuerpo**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-170">**Path -- content located by body path**</span></span>|<span data-ttu-id="bd3d0-171">/\*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span><span class="sxs-lookup"><span data-stu-id="bd3d0-171">/\*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span></span>|<span data-ttu-id="bd3d0-172">**XML**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-172">**XML**</span></span>|  
  
```  
<CustomerID xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">CONTOSO</CustomerID>   
```  
  
## <a name="specifying-the-source-of-the-outbound-wcf-message-body"></a><span data-ttu-id="bd3d0-173">Especificar el origen del cuerpo del mensaje WCF saliente</span><span class="sxs-lookup"><span data-stu-id="bd3d0-173">Specifying the Source of the Outbound WCF Message Body</span></span>  
 <span data-ttu-id="bd3d0-174">Puede controlar cómo crear el cuerpo del mensaje de BizTalk saliente a partir de mensajes WCF que llegan a través de los adaptadores de WCF.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-174">You can control how to create the outbound WCF message body from a BizTalk message body to send through the WCF adapters.</span></span> <span data-ttu-id="bd3d0-175">Para especificar cómo se coloca el cuerpo del mensaje de BizTalk en el cuerpo del mensaje WCF saliente, puede usar una de las siguientes opciones en el **cuerpo del mensaje saliente de WCF** sección en la **mensajes** pestaña tal y como se muestra en el figuras en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="bd3d0-175">To specify how the BizTalk message body is placed in the outbound WCF message body, you can use one of the following options in the **Outbound WCF message body** section on the **Messages** tab as shown in the figures in the previous section:</span></span>  
  
-   <span data-ttu-id="bd3d0-176">**Cuerpo--Cuerpo de mensaje de respuesta de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-176">**Body -- BizTalk response message body**.</span></span> <span data-ttu-id="bd3d0-177">La parte del cuerpo de mensaje de BizTalk se utiliza para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-177">Uses the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message.</span></span> <span data-ttu-id="bd3d0-178">El cuerpo del mensaje de BizTalk saliente se convierte en el cuerpo del mensaje SOAP saliente.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-178">The outgoing BizTalk message body becomes the body of the outbound SOAP message.</span></span>  
  
-   <span data-ttu-id="bd3d0-179">**Plantilla--contenido especificado por plantilla**.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-179">**Template -- content specified by template**.</span></span> <span data-ttu-id="bd3d0-180">Utiliza la plantilla proporcionada en el **XML** cuadro de texto para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-180">Uses the template supplied in the **XML** text box to create the content of the SOAP **Body** element for an outgoing message.</span></span> <span data-ttu-id="bd3d0-181">Los adaptadores de WCF con **cuerpo--cuerpo de mensaje de respuesta de BizTalk** (el valor predeterminado) opción no permite el envío de mensajes no XML, como imágenes de mapa de bits y datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-181">The WCF adapters with **Body -- BizTalk response message body** (the default value) option do not allow sending non-XML message such as character data and bitmap images.</span></span> <span data-ttu-id="bd3d0-182">Puede usar el **plantilla--contenido especificado por plantilla** opción para los adaptadores de WCF enviar mensajes no XML codificados en **base64**, **hexadecimal**, o **cadena** .</span><span class="sxs-lookup"><span data-stu-id="bd3d0-182">You can use the **Template -- content specified by template** option for the WCF adapters to send non-XML messages encoded in **base64**, **hex**, or **string**.</span></span>  
  
 <span data-ttu-id="bd3d0-183">Cuando el **plantilla--contenido especificado por plantilla** opción está seleccionada, debe proporcionar un elemento XML de plantilla arbitrario en el **cuerpo del mensaje saliente de WCF - XML** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-183">When the **Template -- content specified by template** option is selected, you must provide an arbitrary template XML element in the **Outbound WCF message body - XML** text box.</span></span> <span data-ttu-id="bd3d0-184">El elemento XML de plantilla debe contener lo siguiente **bts-msg-body** elemento solamente una vez a menos que el elemento XML de plantilla se deja en blanco:</span><span class="sxs-lookup"><span data-stu-id="bd3d0-184">The template XML element must contain the following **bts-msg-body** element once and only once unless the template XML element is left empty:</span></span>  
  
```  
<bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2010" encoding="[base64|hex|string|xml]"/>  
```  
  
 <span data-ttu-id="bd3d0-185">Los adaptadores de WCF codifican el cuerpo del mensaje de BizTalk según el **codificación** de atributo en la plantilla XML y, a continuación, reemplace el **bts-msg-body** elemento con el cuerpo de mensaje de BizTalk codificado al crear mensajes WCF salientes.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-185">The WCF adapters encode the BizTalk message body according to the **encoding** attribute in the XML template, and then replace the **bts-msg-body** element with the encoded BizTalk message body when creating outbound WCF messages.</span></span> <span data-ttu-id="bd3d0-186">Si el **cuerpo del mensaje saliente de WCF - XML** cuadro de texto se deja vacío, los adaptadores de WCF codifican el cuerpo del mensaje de BizTalk en **Base64**y, a continuación, coloque el **Base64** de secuencia en el cuerpo del mensaje SOAP saliente.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-186">If the **Outbound WCF message body - XML** text box is left empty, the WCF adapters encode the BizTalk message body in **Base64**, and then place the **Base64** sequence in the outbound SOAP message body.</span></span>  
  
 <span data-ttu-id="bd3d0-187">Si el **codificación** atributo en la plantilla XML se establece en **cadena**, los adaptadores de WCF codifican la parte del cuerpo de mensaje de BizTalk como datos de caracteres con codificación UTF-8, en el que los caracteres especiales de XML como \< y \> son caracteres de escape.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-187">If the **encoding** attribute in the XML template is set to **string**, the WCF adapters encode the BizTalk message body part as UTF-8 encoded character data, in which the XML special characters such as \< and \> are escaped.</span></span>  
  
 <span data-ttu-id="bd3d0-188">Si el **codificación** atributo en la plantilla XML se establece en **base64** o **hexadecimal**, los adaptadores de WCF codifican la parte del cuerpo de mensaje de BizTalk como un **BinHex** o **Base64** secuencia.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-188">If the **encoding** attribute in the XML template is set to **base64** or **hex**, the WCF adapters encode the BizTalk message body part as a **BinHex** or **Base64** sequence.</span></span>  
  
 <span data-ttu-id="bd3d0-189">Si el **codificación** atributo en la plantilla XML se establece en **xml**, los adaptadores de WCF sustituyen el **bts-msg-body** elemento con el cuerpo del mensaje de BizTalk saliente para crear el mensaje saliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-189">If the **encoding** attribute in the XML template is set to **xml**, the WCF adapters replace the **bts-msg-body** element with the outbound BizTalk message body to create the outgoing WCF message.</span></span>  
  
 <span data-ttu-id="bd3d0-190">Por ejemplo, suponga que los adaptadores de WCF tienen que enviar la parte del cuerpo del mensaje de BizTalk siguiente a clientes de WCF:</span><span class="sxs-lookup"><span data-stu-id="bd3d0-190">For example, suppose the WCF adapters need to send the following BizTalk message body part to WCF clients:</span></span>  
  
```  
<ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
```  
  
 <span data-ttu-id="bd3d0-191">Si configura el **cuerpo del mensaje saliente de WCF** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean los mensajes WCF salientes como se muestra en el código después de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-191">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  
  
|<span data-ttu-id="bd3d0-192">Cuerpo de mensaje saliente de WCF</span><span class="sxs-lookup"><span data-stu-id="bd3d0-192">Outbound WCF message body</span></span>|<span data-ttu-id="bd3d0-193">XML</span><span class="sxs-lookup"><span data-stu-id="bd3d0-193">XML</span></span>|  
|-------------------------------|---------|  
|<span data-ttu-id="bd3d0-194">**Cuerpo--Cuerpo de mensaje de respuesta de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-194">**Body -- BizTalk response message body**</span></span>|<span data-ttu-id="bd3d0-195">N/D</span><span class="sxs-lookup"><span data-stu-id="bd3d0-195">N/A</span></span>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:6a706a54-c4f5-4767-909d-a992c7c26dba</a:MessageID>  
    <a:ReplyTo>  
<a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessService</a:To>  
  </s:Header>  
  <s:Body>  
    <ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="bd3d0-196">Si configura el **cuerpo del mensaje saliente de WCF** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean los mensajes WCF salientes como se muestra en el código después de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-196">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  
  
|<span data-ttu-id="bd3d0-197">Cuerpo de mensaje saliente de WCF</span><span class="sxs-lookup"><span data-stu-id="bd3d0-197">Outbound WCF message body</span></span>|<span data-ttu-id="bd3d0-198">XML</span><span class="sxs-lookup"><span data-stu-id="bd3d0-198">XML</span></span>|  
|-------------------------------|---------|  
|<span data-ttu-id="bd3d0-199">**Cuerpo--Cuerpo de mensaje de respuesta de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-199">**Body -- BizTalk response message body**</span></span>|<span data-ttu-id="bd3d0-200">\<Book\></span><span class="sxs-lookup"><span data-stu-id="bd3d0-200">\<Book\></span></span><br /><br /> <span data-ttu-id="bd3d0-201">\<**BTS-msg-body** xmlns = "http://www.microsoft.com/schemas/bts2010" codificación = "**cadena**" /\></span><span class="sxs-lookup"><span data-stu-id="bd3d0-201">\<**bts-msg-body** xmlns="http://www.microsoft.com/schemas/bts2010" encoding="**string**"/\></span></span><br /><br /> <span data-ttu-id="bd3d0-202">\</Book\></span><span class="sxs-lookup"><span data-stu-id="bd3d0-202">\</Book\></span></span>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:05dde292-eedd-467e-b0d2-f1b8f0757410</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessService</a:To>  
  </s:Header>  
  <s:Body>  
    <Book><ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  <ns0:OrderDetail>    <ns0:CustomerID>CONTOSO</ns0:CustomerID>    <ns0:OrderID> 01A2c</ns0:OrderID>  </ns0:OrderDetail></ns0:Order>  
    </Book>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="bd3d0-203">Si configura el **cuerpo del mensaje saliente de WCF** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean los mensajes WCF salientes como se muestra en el código después de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-203">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  
  
|<span data-ttu-id="bd3d0-204">Cuerpo de mensaje saliente de WCF</span><span class="sxs-lookup"><span data-stu-id="bd3d0-204">Outbound WCF message body</span></span>|<span data-ttu-id="bd3d0-205">XML</span><span class="sxs-lookup"><span data-stu-id="bd3d0-205">XML</span></span>|  
|-------------------------------|---------|  
|<span data-ttu-id="bd3d0-206">**Cuerpo--Cuerpo de mensaje de respuesta de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-206">**Body -- BizTalk response message body**</span></span>|<span data-ttu-id="bd3d0-207">\<Book\></span><span class="sxs-lookup"><span data-stu-id="bd3d0-207">\<Book\></span></span><br /><br /> <span data-ttu-id="bd3d0-208">\<**BTS-msg-body** xmlns = "http://www.microsoft.com/schemas/bts2010" codificación = "**base64**" /\></span><span class="sxs-lookup"><span data-stu-id="bd3d0-208">\<**bts-msg-body** xmlns="http://www.microsoft.com/schemas/bts2010" encoding="**base64**"/\></span></span><br /><br /> <span data-ttu-id="bd3d0-209">\</Book\></span><span class="sxs-lookup"><span data-stu-id="bd3d0-209">\</Book\></span></span>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://ww  
w.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe  
/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:cb3cac6d-a542-4a90-bad8-cdbfa8251112</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessSer  
vice</a:To>  
  </s:Header>  
  <s:Body>  
    <Book>77u/PG5zMDpPcmRlciB4bWxuczpuczA9Imh0dHA6Ly9NaWNyb3NvZnQuU2FtcGxlcy5CaX  
pUYWxrLk5ldE5hbWVkUGlwZS9PcmRlclByb2Nlc3MiPg0KICA8bnMwOk9yZGVyRGV0YWlsPg0KICAgID  
xuczA6Q3VzdG9tZXJJRD5DT05UT1NPPC9uczA6Q3VzdG9tZXJJRD4NCiAgICA8bnMwOk9yZGVySUQ+MD  
FBMmM8L25zMDpPcmRlcklEPg0KICA8L25zMDpPcmRlckRldGFpbD4NCjwvbnMwOk9yZGVyPg==</Book  
>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="bd3d0-210">Si configura el **cuerpo del mensaje saliente de WCF** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean los mensajes WCF salientes como se muestra en el código después de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bd3d0-210">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  
  
|<span data-ttu-id="bd3d0-211">Cuerpo de mensaje saliente de WCF</span><span class="sxs-lookup"><span data-stu-id="bd3d0-211">Outbound WCF message body</span></span>|<span data-ttu-id="bd3d0-212">XML</span><span class="sxs-lookup"><span data-stu-id="bd3d0-212">XML</span></span>|  
|-------------------------------|---------|  
|<span data-ttu-id="bd3d0-213">**Cuerpo--Cuerpo de mensaje de respuesta de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="bd3d0-213">**Body -- BizTalk response message body**</span></span>|<span data-ttu-id="bd3d0-214">\<Book\></span><span class="sxs-lookup"><span data-stu-id="bd3d0-214">\<Book\></span></span><br /><br /> <span data-ttu-id="bd3d0-215">\<**BTS-msg-body** xmlns = "http://www.microsoft.com/schemas/bts2010" codificación = "**xml**" /\></span><span class="sxs-lookup"><span data-stu-id="bd3d0-215">\<**bts-msg-body** xmlns="http://www.microsoft.com/schemas/bts2010" encoding="**xml**"/\></span></span><br /><br /> <span data-ttu-id="bd3d0-216">\</Book\></span><span class="sxs-lookup"><span data-stu-id="bd3d0-216">\</Book\></span></span>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:A  
ction>  
    <a:MessageID>{513C123C-0600-4A1C-BEE2-EF83E0EFEB15}</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessServiceBizTalk</a:To>  
  </s:Header>  
  <s:Body>  
    <Book>  
      <ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CustomerID_0</ns0:CustomerID>  
    <ns0:OrderID>OrderID_0</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
    </Book>  
  </s:Body>  
</s:Envelope>  
```