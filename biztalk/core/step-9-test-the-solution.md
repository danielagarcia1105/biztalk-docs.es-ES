---
title: 'Paso 9: Probar la solución | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df446ccc-add3-4dd3-b674-253dda385541
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89a3722d6d8e1d4b730341dfaf16d60af1686f21
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973074"
---
# <a name="step-9-test-the-solution"></a><span data-ttu-id="e87d5-102">Paso 9: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="e87d5-102">Step 9: Test the Solution</span></span>
<span data-ttu-id="e87d5-103">En este tema, probará la aplicación híbrida enviando un mensaje de pedido de ventas X12 840 al extremo HTTP donde se implementa el acuerdo EDI.</span><span class="sxs-lookup"><span data-stu-id="e87d5-103">In this topic you test the hybrid application by sending a X12 840 sales order message to the HTTP endpoint where the EDI agreement is deployed.</span></span> <span data-ttu-id="e87d5-104">El aspecto del mensaje de pedido de ventas de muestra será parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e87d5-104">The sample sales order message looks like the following:</span></span>  
  
```  
ISA*00*          *00*          *ZZ*CONTOSO        *ZZ*NORTHWIND      *991221*1226*U*00401*000000025*0*T*:~  
GS*PO*THEM*US*19991221*1226*1*X*004010~  
ST*840*0002~  
BQT*00*BQT02*20120619*001*20120719~  
PER*1A*John*EM*John@contoso.com~  
N1*001~  
N2*co~  
N3*Contoso*One Contoso Way~  
N4*Redmond*WA*98052*US~  
PO1*PO101*121*01*10*AA*A1*1~  
CTT*475~  
SE*10*0002~  
GE*1*1~  
IEA*1*000000025~  
```  
  
 <span data-ttu-id="e87d5-105">En este mensaje, el segmento resaltado (la línea que empieza con **PO1**) contiene la cantidad del pedido.</span><span class="sxs-lookup"><span data-stu-id="e87d5-105">In this message, the highlighted segment (the line starting with **PO1**) contains the order quantity.</span></span> <span data-ttu-id="e87d5-106">La cantidad del pedido en este mensaje es *121*.</span><span class="sxs-lookup"><span data-stu-id="e87d5-106">The order quantity in this message is *121*.</span></span> <span data-ttu-id="e87d5-107">Por lo tanto, si envía este mensaje, se debe insertar en el **SalesOrder** tabla.</span><span class="sxs-lookup"><span data-stu-id="e87d5-107">So, if you send this message, it must be inserted into the **SalesOrder** table.</span></span> <span data-ttu-id="e87d5-108">Puede actualizar la cantidad a menos de 100 y volver a enviar el mensaje y, después, este debe enviarse a la ubicación de archivo especificada en el puerto de envío de archivos.</span><span class="sxs-lookup"><span data-stu-id="e87d5-108">You can update the quantity to less than 100 and resend the message, it must then be sent to the file location you specified in the FILE send port.</span></span>  
  
 <span data-ttu-id="e87d5-109">Para enviar este mensaje al acuerdo EDI, puede usar el **MessageSender** herramienta se incluye en los ejemplos para [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e87d5-109">To send this message to the EDI agreement, you can use the **MessageSender** tool shipped with the samples for [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].</span></span> <span data-ttu-id="e87d5-110">Puede descargar los ejemplos desde [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057).</span><span class="sxs-lookup"><span data-stu-id="e87d5-110">You can download the samples from [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057).</span></span>  
  
### <a name="to-send-a-message"></a><span data-ttu-id="e87d5-111">Para enviar un mensaje</span><span class="sxs-lookup"><span data-stu-id="e87d5-111">To send a message</span></span>  
  
1.  <span data-ttu-id="e87d5-112">Busque la **MessageSender** del proyecto en el paquete de ejemplo y genérelo.</span><span class="sxs-lookup"><span data-stu-id="e87d5-112">Locate the **MessageSender** project in the sample package and build it.</span></span>  
  
2.  <span data-ttu-id="e87d5-113">Utilice el cuadro **MessageSender** ejecutable de línea de comandos (en la carpeta \bin\Debug del proyecto) para enviar mensajes al acuerdo EDI implementado.</span><span class="sxs-lookup"><span data-stu-id="e87d5-113">Use the resulting **MessageSender** command-line executable (under \bin\Debug folder within the project) to send messages to the deployed EDI agreement.</span></span> <span data-ttu-id="e87d5-114">Esta herramienta acepta el parámetro de la línea de comandos en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="e87d5-114">This tool accepts command-line parameter in the following format:</span></span>  
  
    ```  
    MessageSender.exe <ServiceBusNamespace> <IssuerName> <IssuerKey> <EDI agreement endpoint> <MessageFilepath> <ContentType>  
    ```  
  
     <span data-ttu-id="e87d5-115">Donde</span><span class="sxs-lookup"><span data-stu-id="e87d5-115">Where,</span></span>  
  
    |<span data-ttu-id="e87d5-116">Nombre del parámetro</span><span class="sxs-lookup"><span data-stu-id="e87d5-116">Parameter name</span></span>|<span data-ttu-id="e87d5-117">Description</span><span class="sxs-lookup"><span data-stu-id="e87d5-117">Description</span></span>|  
    |--------------------|-----------------|  
    |<span data-ttu-id="e87d5-118">ServiceBusNamespace</span><span class="sxs-lookup"><span data-stu-id="e87d5-118">ServiceBusNamespace</span></span>|<span data-ttu-id="e87d5-119">Espacio de nombres de Service Bus</span><span class="sxs-lookup"><span data-stu-id="e87d5-119">The Service Bus namespace</span></span>|  
    |<span data-ttu-id="e87d5-120">IssuerName</span><span class="sxs-lookup"><span data-stu-id="e87d5-120">IssuerName</span></span>|<span data-ttu-id="e87d5-121">Nombre del emisor del espacio de nombres especificado</span><span class="sxs-lookup"><span data-stu-id="e87d5-121">Issuer Name for the specified namespace</span></span>|  
    |<span data-ttu-id="e87d5-122">IssuerKey</span><span class="sxs-lookup"><span data-stu-id="e87d5-122">IssuerKey</span></span>|<span data-ttu-id="e87d5-123">Clave del emisor del espacio de nombres especificado</span><span class="sxs-lookup"><span data-stu-id="e87d5-123">Issuer Key for the specified namespace</span></span>|  
    |<span data-ttu-id="e87d5-124">Extremo del acuerdo EDI</span><span class="sxs-lookup"><span data-stu-id="e87d5-124">EDI agreement endpoint</span></span>|<span data-ttu-id="e87d5-125">El extremo en el que se implementa el acuerdo EDI.</span><span class="sxs-lookup"><span data-stu-id="e87d5-125">The endpoint where the EDI agreement is deployed.</span></span> <span data-ttu-id="e87d5-126">Puede obtener esta dirección URL del extremo de la pestaña Configuración de recepción (y dentro de ese, la página de transporte) del acuerdo EDI implementado en [(para Azure) del paso 2: crear un acuerdo de EDI](../core/step-2-for-azure-create-an-edi-agreement.md).</span><span class="sxs-lookup"><span data-stu-id="e87d5-126">You can get this endpoint URL from the Receive Settings tab (and within that, the Transport page) of the EDI agreement you deployed in [Step 2 (For Azure): Create an EDI Agreement](../core/step-2-for-azure-create-an-edi-agreement.md).</span></span>|  
    |<span data-ttu-id="e87d5-127">MessageFilePath</span><span class="sxs-lookup"><span data-stu-id="e87d5-127">MessageFilePath</span></span>|<span data-ttu-id="e87d5-128">Ruta de acceso al archivo que contiene el mensaje de solicitud de muestra.</span><span class="sxs-lookup"><span data-stu-id="e87d5-128">Path to the file that contains the sample request message.</span></span>|  
    |<span data-ttu-id="e87d5-129">ContentType</span><span class="sxs-lookup"><span data-stu-id="e87d5-129">ContentType</span></span>|<span data-ttu-id="e87d5-130">Para este tutorial, establezca este parámetro en **texto/sin formato**.</span><span class="sxs-lookup"><span data-stu-id="e87d5-130">For this tutorial, set this parameter to **text/plain**.</span></span>|  
  
     <span data-ttu-id="e87d5-131">Abra un símbolo del sistema y desplácese a la solución en la que compiló el **MessageSender** proyecto.</span><span class="sxs-lookup"><span data-stu-id="e87d5-131">Open a command prompt and navigate to the solution where you built the **MessageSender** project.</span></span> <span data-ttu-id="e87d5-132">Ejecute el siguiente comando para enviar el mensaje de solicitud con una cantidad de pedido superior a 100:</span><span class="sxs-lookup"><span data-stu-id="e87d5-132">Run the following command to send the request message with order quantity more than 100:</span></span>  
  
    ```  
    MessageSender.exe <service bus namespace> owner <issuer key>https://<namespace>.servicebus.appfabriclabs.com/7576ff3d-a0f3-4a46-a4f6-f5be4a50616a/DemoAgreement<path to the sample message> "text/plain"  
    ```  
  
3.  <span data-ttu-id="e87d5-133">Abra SQL Server Management Studio, conéctese a la base de datos que contiene el **SalesOrder** de tabla y compruebe que se inserta un nuevo registro en la tabla.</span><span class="sxs-lookup"><span data-stu-id="e87d5-133">Open SQL Server Management Studio, connect to the database that contains the **SalesOrder** table, and verify that a new record is inserted into the table.</span></span> <span data-ttu-id="e87d5-134">Tenga en cuenta el valor de la **Qty** columna; debe ser *121*.</span><span class="sxs-lookup"><span data-stu-id="e87d5-134">Notice the value in the **Qty** column; it must be *121*.</span></span>  
  
4.  <span data-ttu-id="e87d5-135">Use **MessageSender** enviar otro mensaje, pero esta vez establezca el valor de la cantidad pedida en el mensaje a *99*.</span><span class="sxs-lookup"><span data-stu-id="e87d5-135">Use **MessageSender** to send another message, but this time set the value of the quantity ordered in the message to *99*.</span></span> <span data-ttu-id="e87d5-136">Observará que ahora hay ningún registro insertado en el **SalesOrder** tabla.</span><span class="sxs-lookup"><span data-stu-id="e87d5-136">You will notice that now, no record is inserted in the **SalesOrder** table.</span></span> <span data-ttu-id="e87d5-137">En su lugar, el mensaje se copia en la ubicación de archivo especificada para recibir los mensajes con cantidades de pedido inferior a 100.</span><span class="sxs-lookup"><span data-stu-id="e87d5-137">Instead, the message is copied to the file location you specified for receiving messages with order quantity less than 100.</span></span> <span data-ttu-id="e87d5-138">El mensaje recibido es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e87d5-138">The received message resembles the following:</span></span>  
  
    ```  
    <ns1:SalesOrder xmlns:ns0="http://schemas.microsoft.com/BizTalk/EDI/X12/2006" xmlns:ns1="http://ECommerceSalesOrder.Inbound">  
      <CompanyCode>co</CompanyCode>  
      <PartID>1</PartID>  
      <Quantity>99</Quantity>  
      <AskPrice>10</AskPrice>  
      <RequestShipmentDate>2012-07-19</RequestShipmentDate>  
      <Address>  
        <Line1>Contoso</Line1>  
        <Line2>One Contoso Way</Line2>  
        <City>Redmond</City>  
        <State>WA</State>  
        <Country>US</Country>  
        <Zipcode>98052</Zipcode>  
      </Address>  
      <Contact>  
        <Firstname>John</Firstname>  
        <Lastname>John@contoso.com</Lastname>  
      </Contact>  
      <Comments>Order from Partnerco</Comments>  
      <DateNow>2012-06-19</DateNow>  
    </ns1:SalesOrder>  
  
    ```  
  
     <span data-ttu-id="e87d5-139">Tenga en cuenta el valor de la **cantidad** elemento.</span><span class="sxs-lookup"><span data-stu-id="e87d5-139">Notice the value in the **Quantity** element.</span></span> <span data-ttu-id="e87d5-140">Es *99*.</span><span class="sxs-lookup"><span data-stu-id="e87d5-140">It is *99*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e87d5-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="e87d5-141">See Also</span></span>  
 [<span data-ttu-id="e87d5-142">Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="e87d5-142">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)