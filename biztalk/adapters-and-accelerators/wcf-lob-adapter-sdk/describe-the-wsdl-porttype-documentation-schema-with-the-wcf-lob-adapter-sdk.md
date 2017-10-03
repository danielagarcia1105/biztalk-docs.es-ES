---
title: "Describe el esquema de documentación de WSDL PortType con el SDK del adaptador LOB de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dd96eaf-b3b3-49b4-aea9-0ae1e8999d62
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 038b8ca075e756a0857e70a420c0fc7913113c92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="describe-the-wsdl-porttype-documentation-schema-with-the-wcf-lob-adapter-sdk"></a>Describe el esquema de documentación de WSDL PortType con el SDK del adaptador LOB de WCF
El archivo WSDL que el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] genera contiene información descriptiva adicional para cada portType. El esquema para esta información adicional se describe en este tema.  
  
## <a name="documentation-xml-schema"></a>Esquema de documentación XML  
 La documentación de la operación se implementa mediante la anotación de portType para agregar un nodo que representa la documentación del adaptador para la operación. Este nodo contiene subnodos que describan la operación y los parámetros. Este esquema se define como sigue.  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
\<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  \<xs:element name="adapterOperationDocumentation">  
    \<xs:complexType>  
      \<xs:sequence>  
        \<xs:element name="summary" type="xs:string" />  
        \<xs:element maxOccurs="unbounded" name="param">  
          \<xs:complexType>  
            \<xs:simpleContent>  
              \<xs:extension base="xs:string">  
                \<xs:attribute name="name" type="xs:string" use="required" />  
              \</xs:extension>  
            \</xs:simpleContent>  
          \</xs:complexType>  
        \</xs:element>  
        \<xs:element name="returns" type="xs:string" />  
      \</xs:sequence>  
    \</xs:complexType>  
  \</xs:element>  
\</xs:schema>  
```  
  
 Cuando el WSDL se genera para una operación determinada, el esquema anterior se utiliza para proporcionar información descriptiva adicional en formato legible. Por ejemplo, se devuelve la siguiente información de portType de la operación EchoString del adaptador de eco.  
  
```  
\<wsdl:portType name="EchoService">  
  \<wsdl:operation name="EchoString">  
    \<wsdl:documentation>  
      \<doc:adapterOperationDocumentation>  
        \<doc:summary>String EchoString( string aName)\</doc:summary>  
        \<doc:param name="aName">This string will be echoed back to the user.\</doc:param>  
        \<doc:returns>String value containing the value of aName \</doc:returns>  
      \</doc:adapterOperationDocumentation>  
    \</wsdl:documentation>  
    \<wsdl:input wsaw:Action="Echo/EchoString" message="ns2:EchoService_EchoString_InputMessage" />  
    \<wsdl:output wsaw:Action="Echo/EchoString/response" message="ns2:EchoService_EchoString_OutputMessage" />  
  \</wsdl:operation>  
\</wsdl:portType>  
```  
  
 Se obtienen los valores de los elementos de la documentación de `Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata` para la operación. El ejemplo anterior se generó como resultado el siguiente ejemplo.  
  
```csharp  
ParameterizedOperationMetadata om = new ParameterizedOperationMetadata(operationId, operationId);  
// set this if you want this operation to belong to this interface name  
// in the generated proxy, the interface name will be EchoService  
// and the client implementation name will be EchoServiceClient.  
om.OperationGroup = "EchoService";  
// set the operation namespace to be same as service namespace  
om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;              
switch (operationId)  
{  
   case "Echo/EchoString":  
       om.DisplayName = "EchoString";  
       om.OriginalName = "targetSystemEchoString";  
       om.Description = "String EchoString( string aName)";  
       OperationParameter parm1 = new OperationParameter("aName", OperationParameterDirection.In, QualifiedType.StringType, false);  
       parm1.Description = "This string will be echoed back to the user.";  
       OperationResult result = new OperationResult(new SimpleQualifiedType(XmlTypeCode.String), false);  
       result.Description = "String value containing the value of aName";  
       om.Parameters.Add(parm1);  
       om.OperationResult = result;  
       return om;   
```  
  
## <a name="see-also"></a>Vea también  
 [Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)