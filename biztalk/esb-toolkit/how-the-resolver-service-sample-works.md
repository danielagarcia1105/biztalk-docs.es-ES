---
title: "Cómo funciona el ejemplo de servicio de resolución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33b5f886-ec54-4b2b-b09d-fb4c47ad43a5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af9f90bf80435b00a0d39e83d2b2293595f6f200
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-the-resolver-service-sample-works"></a><span data-ttu-id="db5fe-102">Cómo funciona el ejemplo de servicio de resolución</span><span class="sxs-lookup"><span data-stu-id="db5fe-102">How the Resolver Service Sample Works</span></span>
<span data-ttu-id="db5fe-103">El ejemplo de servicio de resolución crea instancias del servicio de resolución y pasa el mensaje especificado a ella para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="db5fe-103">The Resolver Service sample instantiates the Resolver service and passes the message you specify to it for processing.</span></span> <span data-ttu-id="db5fe-104">La aplicación de cliente de ejemplo de servicio de resolución usa el primer parámetro como la ruta de acceso al archivo ResolverList.xml, que contiene varias solicitudes de resolución y envía estas solicitudes al servicio de resolución.</span><span class="sxs-lookup"><span data-stu-id="db5fe-104">The Resolver Service sample client application uses the first parameter as the path to the ResolverList.xml file, which contains multiple resolver requests, and sends these requests to the Resolver service.</span></span> <span data-ttu-id="db5fe-105">Por ejemplo, la siguiente es la solicitud XPATH que se utilizan en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="db5fe-105">For example, the following is the XPATH request used in the sample.</span></span>  
  
```  
  
//XPATH  
<Resolver>  
  <name>XPATHWithFILE</name>   
  <Content>![CDATA[XPATH:\\TransportLocation=/*[local-name()='OrderDoc'   
    and namespace-uri()='http://globalbank.esb.dynamicresolution.com/  
    northamericanservices/']/*[local-name()='ID' and namespace-  
    uri()='http://globalbank.esb.dynamicresolution.com/  
    northamericanservices/'];TargetNamespace=;  
    MessageExchangePattern=;EndpointConfig=;JaxRpcResponse=;TransportType=;  
    Action=;TransformType=]]  
  </Content>   
  <body>  
    ![CDATA[   
    <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
      <ns0:customerName>Microsoft</ns0:customerName>  
  
<ns0:ID>FILE://C:\Projects\Microsoft.Practices.ESB\Source\Samples  
    \DynamicResolution\Test\Filedrop\OUt\%MessageID%.xml</ns0:ID>   
      <ns0:requestType>10</ns0:requestType>   
    </ns0:OrderDoc>  
    ]]   
  </body>  
</Resolver>  
```  
  
> [!NOTE]
>  <span data-ttu-id="db5fe-106">El contenido real de la  **\<contenido\>**  elemento no contiene los caracteres de espacio en blanco usados para ajustar las líneas en la lista anterior.</span><span class="sxs-lookup"><span data-stu-id="db5fe-106">The actual content of the **\<Content\>** element does not contain the white space characters used to wrap the lines in the preceding listing.</span></span>  
  
 <span data-ttu-id="db5fe-107">La lista anterior muestra que la solicitud contiene la cadena de conexión de configuración de resolución dentro de un  **\<contenido\>**  elemento.</span><span class="sxs-lookup"><span data-stu-id="db5fe-107">The preceding listing shows that the request contains the resolver configuration connection string within a **\<Content\>** element.</span></span> <span data-ttu-id="db5fe-108">El  **\<cuerpo\>**  elemento contiene el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="db5fe-108">The **\<body\>** element contains the message body.</span></span>  
  
 <span data-ttu-id="db5fe-109">El servicio de resolución utiliza el **ResolverMgr** clase para crear instancias de una instancia concreta de la resolución adecuada, definida por el tipo de resolución en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="db5fe-109">The Resolver service uses the **ResolverMgr** class to instantiate a concrete instance of the appropriate resolver, defined by the resolver type in the connection string.</span></span> <span data-ttu-id="db5fe-110">En el caso de la solicitud XPATH, esta es la resolución XPATH.</span><span class="sxs-lookup"><span data-stu-id="db5fe-110">In the case of the XPATH request, this is the XPATH resolver.</span></span>  
  
 <span data-ttu-id="db5fe-111">A continuación, el marco de trabajo crea una instancia de la **ResolveProvider** clase denominada ESB. Resolver.XPath para procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="db5fe-111">Next, the framework creates an instance of the **ResolveProvider** class named ESB.Resolver.XPath to process the request.</span></span> <span data-ttu-id="db5fe-112">La aplicación cliente escribe el mensaje de respuesta desde el servicio de resolución en la carpeta denominada \Source\Samples\ResolverService\Output.</span><span class="sxs-lookup"><span data-stu-id="db5fe-112">The client application writes the response message from the Resolver service into the folder named \Source\Samples\ResolverService\Output.</span></span> <span data-ttu-id="db5fe-113">La siguiente lista muestra el contenido de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="db5fe-113">The following listing shows the contents of the response.</span></span>  
  
```  
  
//XPATH  
Resolver.Action =   
Resolver.ActionField =   
Resolver.DocumentSpecName =   
Resolver.DocumentSpecStrongName =   
Resolver.EndpointConfig =   
Resolver.EpmRRCorrelationToken =   
Resolver.FixJaxRpc = False  
Resolver.InboundTransportLocation =   
Resolver.InboundTransportType =   
Resolver.InterchangeId =   
Resolver.IsRequestResponse =   
Resolver.MessageExchangePattern =   
Resolver.MessageType =   
Resolver.MethodName =   
Resolver.OutboundTransportCLSID =   
Resolver.ReceiveLocationName =   
Resolver.ReceivePortName =   
Resolver.Success = False  
Resolver.TargetNamespace =   
Resolver.TransformType =   
Resolver.TransportLocation = FILE://C:\Projects\Microsoft.  
    Practices.ESB\Source\Samples  
\DynamicResolution\Test\Filedrop\OUt\%MessageID%.xml  
Resolver.TransportNamespace =   
Resolver.TransportType = FILE  
Resolver.WindowUserField =  
```