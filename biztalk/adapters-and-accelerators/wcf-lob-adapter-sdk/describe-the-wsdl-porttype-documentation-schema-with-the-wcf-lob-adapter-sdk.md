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
# <a name="describe-the-wsdl-porttype-documentation-schema-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="26ccc-102">Describe el esquema de documentación de WSDL PortType con el SDK del adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="26ccc-102">Describe the WSDL PortType Documentation Schema with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="26ccc-103">El archivo WSDL que el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] genera contiene información descriptiva adicional para cada portType.</span><span class="sxs-lookup"><span data-stu-id="26ccc-103">The WSDL that the  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] generates contains additional descriptive information for each portType.</span></span> <span data-ttu-id="26ccc-104">El esquema para esta información adicional se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="26ccc-104">The schema for this additional information is described in this topic.</span></span>  
  
## <a name="documentation-xml-schema"></a><span data-ttu-id="26ccc-105">Esquema de documentación XML</span><span class="sxs-lookup"><span data-stu-id="26ccc-105">Documentation XML Schema</span></span>  
 <span data-ttu-id="26ccc-106">La documentación de la operación se implementa mediante la anotación de portType para agregar un nodo que representa la documentación del adaptador para la operación.</span><span class="sxs-lookup"><span data-stu-id="26ccc-106">The operation documentation is implemented using annotation of the portType to add a node that represents the adapter documentation for the operation.</span></span> <span data-ttu-id="26ccc-107">Este nodo contiene subnodos que describan la operación y los parámetros.</span><span class="sxs-lookup"><span data-stu-id="26ccc-107">This node contains subnodes that further describe the operation and parameters.</span></span> <span data-ttu-id="26ccc-108">Este esquema se define como sigue.</span><span class="sxs-lookup"><span data-stu-id="26ccc-108">This schema is defined as follows.</span></span>  
  
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
  
 <span data-ttu-id="26ccc-109">Cuando el WSDL se genera para una operación determinada, el esquema anterior se utiliza para proporcionar información descriptiva adicional en formato legible.</span><span class="sxs-lookup"><span data-stu-id="26ccc-109">When WSDL is generated for a given operation, the preceding schema is used to provide additional descriptive information in human readable format.</span></span> <span data-ttu-id="26ccc-110">Por ejemplo, se devuelve la siguiente información de portType de la operación EchoString del adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="26ccc-110">For example, the following portType information is returned for the EchoString operation of the Echo Adapter.</span></span>  
  
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
  
 <span data-ttu-id="26ccc-111">Se obtienen los valores de los elementos de la documentación de `Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata` para la operación.</span><span class="sxs-lookup"><span data-stu-id="26ccc-111">The values for the documentation elements are obtained from `Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata` for the operation.</span></span> <span data-ttu-id="26ccc-112">El ejemplo anterior se generó como resultado el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="26ccc-112">The preceding example was generated as a result of the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="26ccc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="26ccc-113">See Also</span></span>  
 [<span data-ttu-id="26ccc-114">Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="26ccc-114">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)