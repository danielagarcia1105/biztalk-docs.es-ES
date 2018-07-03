---
title: Invocar métodos de servicio empresarial con objetos de integración mediante el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- integration objects
- how to, invoke business service methods with integration objects
- business service methods, invoking with integration objects
ms.assetid: ac0fa80a-3451-436e-8a1a-b6b5e93081e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40add1c72dabfd8648d1fa33e968cb26e98c11c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996917"
---
# <a name="invoke-business-service-methods-with-integration-objects-using-the-siebel-adapter"></a><span data-ttu-id="31b6a-102">Invocar métodos de servicio empresarial con objetos de integración mediante el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="31b6a-102">Invoke Business Service Methods with Integration Objects using the Siebel adapter</span></span>
<span data-ttu-id="31b6a-103">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] permite a los clientes del adaptador invocar métodos de servicio empresarial que trabajan con objetos de integración.</span><span class="sxs-lookup"><span data-stu-id="31b6a-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enables adapter clients to invoke business service methods that work with integration objects.</span></span> <span data-ttu-id="31b6a-104">Estos servicios empresariales suelen tienen IN, OUT, o escriba los parámetros IN OUT de datos "jerarquía" para enviar o recibir datos de objetos de integración.</span><span class="sxs-lookup"><span data-stu-id="31b6a-104">These business services typically have IN, OUT, or IN OUT parameters of "hierarchy" data type to send or receive integration object data.</span></span>  
  
 <span data-ttu-id="31b6a-105">La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone estos tipos jerárquicos como cadenas.</span><span class="sxs-lookup"><span data-stu-id="31b6a-105">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes these hierarchical types as strings.</span></span> <span data-ttu-id="31b6a-106">Estos valores de cadena son básicamente una cadena XML que se encapsula en una sección XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="31b6a-106">These string values are essentially an XML string encapsulated in an XML CDATA section.</span></span> <span data-ttu-id="31b6a-107">La cadena XML es compatible con el esquema XML del objeto de integración que el cliente de adaptador está intentando enviar o recibir.</span><span class="sxs-lookup"><span data-stu-id="31b6a-107">The XML string is compatible with the XML schema of the integration object the adapter client is trying to send or receive.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="31b6a-108">Ejemplo basado en este tema.</span><span class="sxs-lookup"><span data-stu-id="31b6a-108">Sample Based On This Topic</span></span>  
 <span data-ttu-id="31b6a-109">Un ejemplo, SiebelAdapterIntegrationObjects, basado en este tema también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31b6a-109">A sample, SiebelAdapterIntegrationObjects, based on this topic is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="31b6a-110">Para obtener más información, consulte [ejemplos para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="31b6a-110">For more information, see [Samples for the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).</span></span>
  
## <a name="creating-an-orchestration-to-invoke-business-service-methods-with-integration-objects"></a><span data-ttu-id="31b6a-111">Creación de una orquestación para invocar métodos de servicio empresarial con objetos de integración</span><span class="sxs-lookup"><span data-stu-id="31b6a-111">Creating an Orchestration to Invoke Business Service Methods with Integration Objects</span></span>  
 <span data-ttu-id="31b6a-112">Creación de una orquestación para invocar un método de servicio de negocio que toma los parámetros de objetos de integración es similar a la orquestación para invocar cualquier otro servicio de negocio, como se describe en [invocar Business Service métodos mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="31b6a-112">Creating an orchestration to invoke a business service method that takes integration object parameters is similar to the orchestration to invoke any other business service, as described in [Invoke Business Service Methods Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span></span>  
  
 <span data-ttu-id="31b6a-113">La diferencia reside en el mensaje de solicitud que quita de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="31b6a-113">The difference lies in the request message that you drop for the orchestration.</span></span> <span data-ttu-id="31b6a-114">Esta diferencia es debido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="31b6a-114">This difference is because of the following:</span></span>  
  
- <span data-ttu-id="31b6a-115">El esquema del mensaje de solicitud es diferente porque invocar un servicio empresarial diferente.</span><span class="sxs-lookup"><span data-stu-id="31b6a-115">The schema for the request message is different because you invoke a different business service.</span></span>  
  
- <span data-ttu-id="31b6a-116">El mensaje de solicitud contiene la cadena XML para el objeto de integración.</span><span class="sxs-lookup"><span data-stu-id="31b6a-116">The request message contains the XML string for the integration object.</span></span> <span data-ttu-id="31b6a-117">Este XML se encapsula en una sección CDATA.</span><span class="sxs-lookup"><span data-stu-id="31b6a-117">This XML is encapsulated in a CDATA section.</span></span> <span data-ttu-id="31b6a-118">Debe generar primero el esquema para el objeto de integración y, a continuación, crear un XML que se ajusta al esquema.</span><span class="sxs-lookup"><span data-stu-id="31b6a-118">You must first generate the schema for the integration object and then create an XML that conforms to the schema.</span></span> <span data-ttu-id="31b6a-119">Este XML debe pasarse en la sección CDATA del mensaje de solicitud enviado al adaptador.</span><span class="sxs-lookup"><span data-stu-id="31b6a-119">This XML must be passed within the CDATA section of the request message sent to the adapter.</span></span>  
  
  <span data-ttu-id="31b6a-120">Después de haber generado el XML que se ajusta al esquema de objetos de integración y lo incluye en el mensaje de solicitud, debe quitar el mensaje de solicitud en una ubicación de archivos, igual que haría para cualquier otra orquestación.</span><span class="sxs-lookup"><span data-stu-id="31b6a-120">After you have generated the XML that conforms to the integration object schema and included it in the request message, you must drop the request message at a FILE location, just like you do for any other orchestration.</span></span> <span data-ttu-id="31b6a-121">Busque el mensaje de respuesta en la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="31b6a-121">Look for the response message in the other FILE location.</span></span>  
  
## <a name="request-and-response-messages-for-invoking-business-service-with-integration-objects"></a><span data-ttu-id="31b6a-122">Mensajes de solicitud y respuesta para invocar el servicio de negocio con objetos de integración</span><span class="sxs-lookup"><span data-stu-id="31b6a-122">Request and Response Messages for Invoking Business Service with Integration Objects</span></span>  
 <span data-ttu-id="31b6a-123">Como se mencionó antes, la única diferencia para invocar un servicio empresarial que toma los parámetros de objetos de integración es el mensaje de solicitud enviado al adaptador.</span><span class="sxs-lookup"><span data-stu-id="31b6a-123">As mentioned before, the only difference for invoking a business service that takes integration object parameters is the request message sent to the adapter.</span></span> <span data-ttu-id="31b6a-124">Esta sección proporciona instrucciones sobre los pasos que debe realizar para crear el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="31b6a-124">This section provides instructions on the steps you must perform to create the request message.</span></span>  
  
 <span data-ttu-id="31b6a-125">Para comprender mejor, tomar un servicio de negocio de Siebel 'Adaptador de Siebel EAI' como un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="31b6a-125">For better understanding, take a Siebel business service 'EAI Siebel Adapter' as an example.</span></span> <span data-ttu-id="31b6a-126">El servicio de negocio 'Adaptador de Siebel de EAI' funciona en un objeto de la integración de Siebel, "Cuenta de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="31b6a-126">The 'EAI Siebel Adapter' business service operates on a Siebel integration object, 'Sample Account'.</span></span> <span data-ttu-id="31b6a-127">Debe realizar las tareas siguientes para crear el mensaje de solicitud para invocar un método expuesto por el servicio de negocio 'Adaptador de Siebel de EAI':</span><span class="sxs-lookup"><span data-stu-id="31b6a-127">You must perform the following tasks to create the request message to invoke a method exposed by the 'EAI Siebel Adapter' business service:</span></span>  
  
- <span data-ttu-id="31b6a-128">**Generar el esquema para el servicio de adaptador de Siebel EAI business**.</span><span class="sxs-lookup"><span data-stu-id="31b6a-128">**Generate the schema for the EAI Siebel Adapter business service**.</span></span> <span data-ttu-id="31b6a-129">Debe usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="31b6a-129">You must use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate the schema.</span></span> <span data-ttu-id="31b6a-130">Cuando genere el esquema, generar el XML que se ajusta al esquema.</span><span class="sxs-lookup"><span data-stu-id="31b6a-130">Once you generate the schema, generate the XML that conforms to the schema.</span></span>  
  
- <span data-ttu-id="31b6a-131">**Generar el esquema para el objeto de integración**.</span><span class="sxs-lookup"><span data-stu-id="31b6a-131">**Generate the schema for the integration object**.</span></span> <span data-ttu-id="31b6a-132">Use las herramientas de Siebel para generar el esquema de un objeto de integración.</span><span class="sxs-lookup"><span data-stu-id="31b6a-132">Use Siebel Tools to generate schema for an integration object.</span></span> <span data-ttu-id="31b6a-133">Desde la interfaz de las herramientas de Siebel, seleccione el objeto de integración, por ejemplo, la cuenta de ejemplo y haga clic en **generar esquema**.</span><span class="sxs-lookup"><span data-stu-id="31b6a-133">From the Siebel Tools interface, select the integration object, for example, Sample Account, and click **Generate Schema**.</span></span> <span data-ttu-id="31b6a-134">Al generar el esquema, asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="31b6a-134">While generating the schema, make sure:</span></span>  
  
  - <span data-ttu-id="31b6a-135">El **seleccione un servicio empresarial en la lista** desplegable tiene el valor "EAI XML XSD Generator".</span><span class="sxs-lookup"><span data-stu-id="31b6a-135">The **Select a Business Service from the list** drop-down has the value "EAI XML XSD Generator".</span></span>  
  
  - <span data-ttu-id="31b6a-136">El **seleccione un tipo de sobre de la lista** desplegable tiene el valor "Siebel sobre del mensaje".</span><span class="sxs-lookup"><span data-stu-id="31b6a-136">The **Select an envelope type from the list** drop-down has the value "Siebel Message Envelope".</span></span>  
  
    <span data-ttu-id="31b6a-137">Para obtener más información, consulte la documentación de Siebel.</span><span class="sxs-lookup"><span data-stu-id="31b6a-137">For more information, see the Siebel documentation.</span></span>  
  
- <span data-ttu-id="31b6a-138">**Crear un mensaje XML que se ajusta al esquema del objeto integración**.</span><span class="sxs-lookup"><span data-stu-id="31b6a-138">**Create an XML message that conforms to schema of the integration object**.</span></span> <span data-ttu-id="31b6a-139">Un mensaje XML de ejemplo generado para el objeto de integración 'Cuenta de ejemplo' tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="31b6a-139">A sample XML message generated for the 'Sample Account' integration object looks like:</span></span>  
  
  ```  
  <?xml version="1.0" encoding="UTF-16"?>  
  <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
    <ListOfSampleAccount>  
      <Account>  
        <CurrencyCode>USD</CurrencyCode>  
        <Location>Redmond</Location>  
        <Name>IntegrationObjectTest</Name>  
      </Account>  
    </ListOfSampleAccount>  
  </SiebelMessage>  
  ```  
  
- <span data-ttu-id="31b6a-140">**Pase este mensaje XML como el valor para el elemento CDATA en el mensaje de solicitud para el método de servicio empresarial**.</span><span class="sxs-lookup"><span data-stu-id="31b6a-140">**Pass this XML message as the value for the CDATA element in the request message for the business service method**.</span></span> <span data-ttu-id="31b6a-141">Un mensaje de solicitud de ejemplo que contiene el mensaje XML anterior dentro de un elemento CDATA es similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="31b6a-141">A sample request message that contains the preceding XML message within a CDATA element looks like the following.</span></span> <span data-ttu-id="31b6a-142">Esta solicitud de ejemplo consiste en invocar el método de inserción para el servicio de negocio 'Adaptador de Siebel de EAI'.</span><span class="sxs-lookup"><span data-stu-id="31b6a-142">This sample request is to invoke the Insert method for the 'EAI Siebel Adapter' business service.</span></span>  
  
  ```  
  <Insert xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter/Operation">  
    <InsertRequestRecord />   
    <InsertInOutRecord>  
      <SiebelMessage xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">  
        <![CDATA[ <?xml version="1.0" encoding="UTF-16"?>  
          <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
            <ListOfSampleAccount>  
              <Account>  
                <CurrencyCode>USD</CurrencyCode>  
                <Location>Redmond</Location>  
                <Name>IntegrationObjectTest</Name>  
              </Account>  
            </ListOfSampleAccount>  
          </SiebelMessage>  
        ]]>   
       </SiebelMessage>  
    </InsertInOutRecord>  
  </Insert>  
  ```  
  
   <span data-ttu-id="31b6a-143">La respuesta de Siebel para el mensaje de solicitud anterior es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="31b6a-143">The response from Siebel for the above request message resembles the following:</span></span>  
  
  ```  
  <?xml version="1.0" encoding="utf-8" ?>   
  <InsertResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter/Operation">  
    <InsertResult>  
      <ErrorCode xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">0x0</ErrorCode>   
      <ErrorContextIntComp xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
      <ErrorContextSearchSpec xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
      <ErrorSymbol xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
      <OMErrorCode xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
      <OMErrorSymbol xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
      <PrimaryRowId xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">1-6SPSJ</PrimaryRowId>   
    </InsertResult>  
    <InsertInOutRecord>  
      <SiebelMessage xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">  
        <![CDATA[ <?xml version="1.0" encoding="UTF-16"?>  
          <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
            <ListOfSampleAccount>  
              <Account>  
                <CurrencyCode>USD</CurrencyCode>  
                <Location>Redmond</Location>  
                <Name>IntegrationObjectTest</Name>  
              </Account>  
            </ListOfSampleAccount>  
          </SiebelMessage>  
        ]]>   
       </SiebelMessage>  
    </InsertInOutRecord>  
  </InsertResponse>  
  ```  
  
  <span data-ttu-id="31b6a-144">Uso de las características de BizTalk, los clientes del adaptador también pueden realizar una validación adicional la integración de entrada y salida del parámetro de objeto con respecto al esquema de objetos de integración (obtenido a partir de las herramientas de Siebel).</span><span class="sxs-lookup"><span data-stu-id="31b6a-144">Using BizTalk features, adapter clients can also perform additional validation of the integration object IN and OUT parameter against the integration object schema (obtained from Siebel Tools.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b6a-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="31b6a-145">See Also</span></span>  
<span data-ttu-id="31b6a-146">[Desarrollar aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)  </span><span class="sxs-lookup"><span data-stu-id="31b6a-146">[Develop BizTalk Applications using the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)  </span></span>  
[<span data-ttu-id="31b6a-147">Desarrollar aplicaciones de Siebel</span><span class="sxs-lookup"><span data-stu-id="31b6a-147">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)