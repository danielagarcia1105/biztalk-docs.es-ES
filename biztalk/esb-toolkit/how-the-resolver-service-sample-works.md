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
# <a name="how-the-resolver-service-sample-works"></a>Cómo funciona el ejemplo de servicio de resolución
El ejemplo de servicio de resolución crea instancias del servicio de resolución y pasa el mensaje especificado a ella para su procesamiento. La aplicación de cliente de ejemplo de servicio de resolución usa el primer parámetro como la ruta de acceso al archivo ResolverList.xml, que contiene varias solicitudes de resolución y envía estas solicitudes al servicio de resolución. Por ejemplo, la siguiente es la solicitud XPATH que se utilizan en el ejemplo.  
  
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
>  El contenido real de la  **\<contenido\>**  elemento no contiene los caracteres de espacio en blanco usados para ajustar las líneas en la lista anterior.  
  
 La lista anterior muestra que la solicitud contiene la cadena de conexión de configuración de resolución dentro de un  **\<contenido\>**  elemento. El  **\<cuerpo\>**  elemento contiene el cuerpo del mensaje.  
  
 El servicio de resolución utiliza el **ResolverMgr** clase para crear instancias de una instancia concreta de la resolución adecuada, definida por el tipo de resolución en la cadena de conexión. En el caso de la solicitud XPATH, esta es la resolución XPATH.  
  
 A continuación, el marco de trabajo crea una instancia de la **ResolveProvider** clase denominada ESB. Resolver.XPath para procesar la solicitud. La aplicación cliente escribe el mensaje de respuesta desde el servicio de resolución en la carpeta denominada \Source\Samples\ResolverService\Output. La siguiente lista muestra el contenido de la respuesta.  
  
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