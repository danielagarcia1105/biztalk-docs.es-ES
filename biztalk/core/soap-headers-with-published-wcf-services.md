---
title: Encabezados SOAP con servicios WCF publicados | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing, SOAP headers [WCF services]
- SOAP headers, WCF services
- WCF services, SOAP headers
ms.assetid: 5564a57e-e241-4595-a959-4289c8502410
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78f36e778930a781ac797e18308240ecb4bef667
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="soap-headers-with-published-wcf-services"></a>Encabezados SOAP con servicios WCF publicados
Adaptadores de recepción de WCF pueden copiar todos los valores de encabezado SOAP en los mensajes entrantes en el **InboundHeaders** propiedad, o puede escribir o promover valores específicos en el contexto del mensaje de BizTalk. Los adaptadores pueden funcionar con los encabezados SOAP personalizados y los encabezados SOAP estándar que utiliza la infraestructura de WCF, por ejemplo, WS-Addressing, WS-Security y WS-AtomicTransaction. El **InboundHeaders** propiedad de contexto está en el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**y contiene representaciones de cadena de SOAP valores de encabezado de mensajes entrantes.  
  
> [!NOTE]
>  Si va a promover los valores del encabezado SOAP que ha especificado, debe haber un esquema de propiedades implementado en el proyecto de BizTalk que corresponda a los valores que se van a promover.  
  
> [!NOTE]
>  Las propiedades promocionadas no pueden ser superiores a 256 caracteres.  
  
 Los siguientes datos XML muestran un ejemplo de la representación de cadena de los encabezados SOAP para la **InboundHeaders** propiedad. Esto se recibe desde el cliente y se envía a la ubicación de recepción de BizTalk.  
  
```  
<headers>  
<a:Action s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">Operation_1</a:Action>  
<SalesAgent xmlns="Microsoft.Samples.BizTalk.WCF.CustomSoapHeaderPipeline">Contoso</SalesAgent>  
<a:MessageID xmlns:a="http://www.w3.org/2005/08/addressing">urn:uuid:26e6720f-5a82-4ef2-b597-6ef077bab92e</a:MessageID>  
<a:ReplyTo xmlns:a="http://www.w3.org/2005/08/addressing"><a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address></a:ReplyTo>  
<a:To s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">net.tcp://localhost:9990/NetTcpOrderProcess</a:To>  
</headers>  
```  
  
 Para escribir o promover los valores del encabezado SOAP en el contexto del mensaje de BizTalk, es necesario colocar una colección de parejas de valores que se componen del nombre de propiedad y de espacio de nombres en el mensaje WCF, de modo que los adaptadores de WCF reconocerán que los valores de encabezado se deben escribir o promover. Un adaptador de WCF espera las siguientes propiedades del mensaje en los mensajes de WCF para escribir o promover los valores del encabezado SOAP en el contexto del mensaje de BizTalk:  
  
-   Para promover los valores del encabezado SOAP en el contexto de mensaje de BizTalk, los adaptadores de WCF se buscan la pareja de clave **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote** y el valor **lista\< KeyValuePair\<XmlQualifiedName, objeto\>\>**.  
  
     Con esta pareja, adaptadores de WCF toman el espacio de nombres, el nombre y el valor de la **XmlQualifiedName** objeto y usarlos para la promoción de los valores de encabezado.  
  
-   Para escribir pero no promover los valores del encabezado SOAP en el contexto de mensaje de BizTalk, los adaptadores de WCF se buscan la pareja de clave **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext** y el valor  **Lista\<KeyValuePair\<XmlQualifiedName, objeto\>\>**.  
  
     Con esta pareja, los adaptadores de WCF escriben los valores en el contexto del mensaje.  
  
 El siguiente código muestra cómo escribir o promover los valores del encabezado SOAP en el contexto del mensaje de BizTalk:  
  
```  
const string PropertiesToPromoteKey="http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote";  
const string PropertiesToWriteKey="http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext";  
  
XmlQualifiedName PropName1=new XmlQualifiedName("Destination", "http://tempuri.org/2007/sample-properties");  
XmlQualifiedName PropName2=new XmlQualifiedName("Source", "http://tempuri.org/2007/sample-properties");  
  
//Create a List of KeyValuePairs that indicate properties to be promoted to BizTalk message context.   
//A Property Schema must be deployed and string values have a limit of 256 characters  
List<KeyValuePair<XmlQualifiedName, object>> promoteProps=new List<KeyValuePair<XmlQualifiedName, object>>();  
promoteProps.Add(new KeyValuePair<XmlQualifiedName, object>(PropName1, "Property value"));  
wcfMessage.Properties[PropertiesToPromoteKey]=promoteProps;  
  
//Create a List of KeyValuePairs that indicate properties to be written to BizTalk message context  
List<KeyValuePair<XmlQualifiedName, object>> writeProps=new List<KeyValuePair<XmlQualifiedName, object>>();  
writeProps.Add(new KeyValuePair<XmlQualifiedName, object>(PropName2, "Property value"));  
wcfMessage.Properties[PropertiesToWriteKey]=writeProps;  
```  
  
 El Asistente para publicación de Servicio WCF de BizTalk no incluye definiciones de encabezado SOAP personalizadas en los metadatos generados. Para publicar los metadatos de los servicios WCF con encabezados SOAP personalizados, debe crear de forma manual un archivo de Lenguaje de descripción de servicios Web (WSDL). Puede usar el **externalMetadataLocation** atributo de la [ \<serviceMetadata\> ](http://go.microsoft.com/fwlink/?LinkId=89121) elemento en el archivo Web.config que genera el Asistente para especificar la ubicación de la Archivo WSDL. El archivo WSDL se devuelve al usuario en respuesta a las solicitudes de intercambio de metadatos (MEX) WSDL en lugar de WSDL generado de forma automática.  
  
 Los siguientes datos XML muestran un ejemplo de una parte del archivo WSDL que define los encabezados SOAP personalizados:  
  
```  
<wsdl:operation name="Request">  
  <soap12:operation soapAction="http://Microsoft.Samples.BizTalk.NetTcpAdapter/OrderProcess/IOrderProcess/Request" style="document" />   
   <wsdl:input name="Order">  
     <soap12:header message="i0:Order_Headers" part="SalesAgent" use="literal" />   
     <soap12:body use="literal" />   
   </wsdl:input>  
   <wsdl:output name="OrderConfirmation">  
     <soap12:header message="i0:OrderConfirmation_Headers" part="PaymentAgent" use="literal" />   
     <soap12:body use="literal" />   
   </wsdl:output>  
</wsdl:operation>  
```  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Obtener acceso a encabezados SOAP en mensajes WCF con orquestaciones](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [Obtener acceso a encabezados SOAP en mensajes WCF con componentes de canalización](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a>Vea también  
 [Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md)   
 [Encabezados SOAP con servicios WCF consumidos](../core/soap-headers-with-consumed-wcf-services.md)