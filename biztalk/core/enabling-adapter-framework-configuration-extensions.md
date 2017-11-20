---
title: "Habilitar extensiones de configuración de marco de trabajo de adaptadores | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 851f4a20-502d-45f8-9647-13bec33fa460
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346bbc3d4d136ad7116a68b3c57a47566f258a68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-adapter-framework-configuration-extensions"></a><span data-ttu-id="5bb70-102">Habilitar extensiones de configuración de marco de trabajo de adaptadores</span><span class="sxs-lookup"><span data-stu-id="5bb70-102">Enabling Adapter Framework Configuration Extensions</span></span>
<span data-ttu-id="5bb70-103">El marco de trabajo de adaptadores de BizTalk proporciona varias extensiones para mejorar la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="5bb70-103">The BizTalk Adapter Framework provides several extensions to improve the user experience.</span></span> <span data-ttu-id="5bb70-104">Para usar estas extensiones, importe el esquema del marco de trabajo, BiztalkAdapterFramework.xsd.</span><span class="sxs-lookup"><span data-stu-id="5bb70-104">To use these extensions, import the framework's schema, BiztalkAdapterFramework.xsd.</span></span> <span data-ttu-id="5bb70-105">Importar el esquema permite tener acceso a decoraciones y tipos especializados y usarlos en el esquema de configuración del adaptador, tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="5bb70-105">Importing the schema enables you to access decorations and specialized types and to use them in the adapter's configuration schema, as described below.</span></span> <span data-ttu-id="5bb70-106">En el siguiente código se muestra el modo de importar el esquema:</span><span class="sxs-lookup"><span data-stu-id="5bb70-106">The following code shows how to import the schema:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?><xs:schema   targetNamespace="http://tempuri.org/XMLSchema.xsd"   
         elementFormDefault="qualified" xmlns="http://tempuri.org/XMLSchema.xsd"   
         xmlns:baf="BiztalkAdapterFramework.xsd"   
         xmlns:xs="http://www.w3.org/2001/XMLSchema"   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:import namespace="BiztalkAdapterFramework.xsd" />  
. . .  
</xs:schema>  
```  
  
## <a name="importing-the-biztalk-adapter-framework-extensions-schema-xsd"></a><span data-ttu-id="5bb70-107">Importar el esquema XSD de extensiones del marco de trabajo de adaptadores de BizTalk</span><span class="sxs-lookup"><span data-stu-id="5bb70-107">Importing the BizTalk Adapter Framework Extensions Schema XSD</span></span>  
 <span data-ttu-id="5bb70-108">Importando el esquema XSD de extensiones del marco de trabajo, puede usar decoraciones como \<BAF: filename > como un tipo de elemento, que muestra el nombre de archivo emergente cuando se edita el elemento.</span><span class="sxs-lookup"><span data-stu-id="5bb70-108">By importing the Adapter Framework extensions schema XSD, you can use decorations such as \<baf:FileName> as an element's type, which shows the file name pop-up when editing the element.</span></span>  
  
 <span data-ttu-id="5bb70-109">Otras decoraciones controlan la visualización de la propiedad en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="5bb70-109">Additional decorations control the display of the property in the interface.</span></span> <span data-ttu-id="5bb70-110">El \<BAF: Description > decoración, por ejemplo, agrega el texto de ayuda para el elemento.</span><span class="sxs-lookup"><span data-stu-id="5bb70-110">The \<baf:description> decoration, for example, adds help text to the element.</span></span> <span data-ttu-id="5bb70-111">El \<BAF: Description > decoración muestra el texto en la parte inferior de la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="5bb70-111">The \<baf:description> decoration displays the text at the bottom of the property page.</span></span> <span data-ttu-id="5bb70-112">El \<baf: browsable > decoración oculta un elemento de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="5bb70-112">The \<baf:browsable> decoration hides an element from the interface.</span></span> <span data-ttu-id="5bb70-113">El siguiente código muestra cómo puede usar estos elementos dentro de un esquema de configuración:</span><span class="sxs-lookup"><span data-stu-id="5bb70-113">The following code shows how you can use these elements within a configuration schema:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?><xs:schema   targetNamespace="http://tempuri.org/XMLSchema.xsd"   
         elementFormDefault="qualified" xmlns="http://tempuri.org/XMLSchema.xsd"   
         xmlns:baf="BiztalkAdapterFramework.xsd"   
         xmlns:xs="http://www.w3.org/2001/XMLSchema"   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:import namespace="BiztalkAdapterFramework.xsd" />  
   <xs:element name="Send">  
      <xs:complexType>  
         <xs:sequence>  
            <xs:element name="directory" type="xs:string" />  
               <xs:annotation>  
                  <xs:appinfo>  
                     <baf:designer>  
                        <baf:description>Enter the directory that will receive sent files..  
                        </baf:description>  
                     </baf:designer>  
                  </xs:appinfo>  
               </xs:annotation>  
            </xs:element>  
            <xs:element name="fileName" type="" />  
            <xs:element name="sendBatchSize" type="xs:int" />  
            <xs:element name="fileCopyMode" type="CopyMode" />  
            <xs:element name="uri" type="xs:string" >  
               <xs:annotation>  
                  <xs:appinfo>  
                     <baf:designer>  
                        <baf:browsable show="false" />  
                     </baf:designer>  
                  </xs:appinfo>  
               </xs:annotation>  
            </xs:element>  
         </xs:sequence>  
      </xs:complexType>  
   </xs:element>  
   <xs:simpleType name="CopyMode">  
      <xs:restriction base="xs:string">  
         <xs:enumeration value="Append">  
            <xs:annotation>  
               <xs:documentation>= 0</xs:documentation>  
            </xs:annotation>  
         <xs:enumeration value="Create">  
            <xs:annotation>  
               <xs:documentation>= 1</xs:documentation>  
            </xs:annotation>  
         <xs:enumeration value="CreateNew">  
            <xs:annotation>  
               <xs:documentation>= 2</xs:documentation>  
            </xs:annotation>  
         </xs:enumeration>  
      </xs:restriction>  
   </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bb70-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bb70-114">See Also</span></span>  
 [<span data-ttu-id="5bb70-115">Extensiones de esquema de configuración de marco de trabajo de adaptadores</span><span class="sxs-lookup"><span data-stu-id="5bb70-115">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)