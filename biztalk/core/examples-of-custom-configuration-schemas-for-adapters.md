---
title: Ejemplos de esquemas de configuración personalizada para adaptadores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31b188de-9363-4f4c-b40a-149ff59ddf8d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b11cb16c7b7ae9285b6ffb77c7177964d211482f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245916"
---
# <a name="examples-of-custom-configuration-schemas-for-adapters"></a><span data-ttu-id="5c67f-102">Ejemplos de esquemas de configuración personalizada para los adaptadores</span><span class="sxs-lookup"><span data-stu-id="5c67f-102">Examples of Custom Configuration Schemas for Adapters</span></span>
<span data-ttu-id="5c67f-103">En esta sección se proporcionan los siguientes ejemplos sobre cómo personalizar esquemas de configuración para adaptadores:</span><span class="sxs-lookup"><span data-stu-id="5c67f-103">This section provides the following examples for how to customize configuration schemas for adapters:</span></span>  
  
-   <span data-ttu-id="5c67f-104">**Ejemplo 1** muestra un archivo de esquema XSD personalizado completo que representa una página de propiedades de adaptador con las extensiones BAF: Designer y BAF: Description.</span><span class="sxs-lookup"><span data-stu-id="5c67f-104">**Example 1** shows a complete custom XSD schema file representing an adapter property page using the baf:designer and baf:description extensions.</span></span>  
  
-   <span data-ttu-id="5c67f-105">**Ejemplo 2** también usa las extensiones BAF: Designer y BAF: Description para mostrar cómo crear una ventana de valor de propiedad personalizada para el **BatchSize** propiedad que solo acepte valores entre 1 y 99, inclusive.</span><span class="sxs-lookup"><span data-stu-id="5c67f-105">**Example 2** also uses the baf:designer and baf:description extensions to show how to create a custom property value window for the **BatchSize** property that only accepts values between 1 and 99, inclusive.</span></span>  
  
-   <span data-ttu-id="5c67f-106">**Ejemplo 3** muestra cómo se limita BAF: Password a 8 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5c67f-106">**Example 3** shows how to limit the baf:Password to 8 characters.</span></span> <span data-ttu-id="5c67f-107">De forma predeterminada, se permiten 22 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5c67f-107">By default, it allows 22 characters.</span></span>  
  
-   <span data-ttu-id="5c67f-108">**Ejemplo 4** muestra cómo implementar restricciones de coincidencia de patrones en los valores de propiedad porque no se admiten los patrones de XSD.</span><span class="sxs-lookup"><span data-stu-id="5c67f-108">**Example 4** shows how to implement pattern-matching constraints on property values because XSD patterns are not supported.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="5c67f-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="5c67f-109">Example 1</span></span>  
 <span data-ttu-id="5c67f-110">Este ejemplo muestra un esquema XSD personalizado completo.</span><span class="sxs-lookup"><span data-stu-id="5c67f-110">This example shows a complete custom XSD schema.</span></span> <span data-ttu-id="5c67f-111">Representa una página de propiedades del adaptador con las extensiones baf:designer y baf:description.</span><span class="sxs-lookup"><span data-stu-id="5c67f-111">It represents an adapter property page using the baf:designer and baf:description extensions.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xs:schema   targetNamespace="http://tempuri.org/XMLSchema.xsd"   
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
  
## <a name="example-2"></a><span data-ttu-id="5c67f-112">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="5c67f-112">Example 2</span></span>  
 <span data-ttu-id="5c67f-113">Este ejemplo utiliza las extensiones BAF: Designer y BAF: Description para mostrar cómo crear una ventana de valor de propiedad personalizada para el **BatchSize** propiedad que solo acepte valores entre 1 y 99, inclusive.</span><span class="sxs-lookup"><span data-stu-id="5c67f-113">This example uses the baf:designer and baf:description extensions to show how to create a custom property value window for the **BatchSize** property that only accepts values between 1 and 99, inclusive.</span></span>  
  
```  
   <xs:element name="BatchSize">  
          <xs:simpleType>  
            <xs:annotation>  
              <xs:appinfo>  
                <baf:designer>  
                  <baf:displayname>Batch Size</baf:displayname>  
                  <baf:description>Enter the batch size (1-99)</baf:description>  
                </baf:designer>  
              </xs:appinfo>  
            </xs:annotation>  
            <xs:restriction base="xs:int">  
              <xs:minInclusive value="1" />  
              <xs:maxInclusive value="99" />  
            </xs:restriction>  
          </xs:simpleType>  
        </xs:element>  
```  
  
## <a name="example-3"></a><span data-ttu-id="5c67f-114">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="5c67f-114">Example 3</span></span>  
 <span data-ttu-id="5c67f-115">Este ejemplo muestra cómo se limita baf:Password a 8 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5c67f-115">This example shows how to limit the baf:Password to 8 characters.</span></span> <span data-ttu-id="5c67f-116">De forma predeterminada, se permiten 22 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5c67f-116">By default, it allows 22 characters.</span></span>  
  
```  
<xs:element name="AdapterPassword">  
          <xs:simpleType>  
            <xs:annotation>  
              <xs:appinfo>  
                <baf:designer>  
                  <baf:displayname>Adapter Password</baf:displayname>  
                  <baf:description>Enter the password (up to 8 characters)</baf:description>  
                  <baf:editor assembly="%BTSROOT%\\Developer Tools\\Microsoft.BizTalk.Adapter.Framework.dll">Microsoft.BizTalk.Adapter.Framework.ComponentModel.PasswordUITypeEditor</baf:editor>  
                  <baf:converter assembly="%BTSROOT%\\Developer Tools\\Microsoft.BizTalk.Adapter.Framework.dll">Microsoft.BizTalk.Adapter.Framework.ComponentModel.PasswordTypeConverter</baf:converter>  
                </baf:designer>  
              </xs:appinfo>  
            </xs:annotation>  
            <xs:restriction base="xs:string">  
              <xs:maxLength value="8" />  
            </xs:restriction>  
          </xs:simpleType>  
        </xs:element>  
```  
  
## <a name="example-4"></a><span data-ttu-id="5c67f-117">Ejemplo 4</span><span class="sxs-lookup"><span data-stu-id="5c67f-117">Example 4</span></span>  
 <span data-ttu-id="5c67f-118">Este ejemplo muestra cómo se implementan restricciones de coincidencia de patrones en los valores de propiedad porque los patrones de XSD no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="5c67f-118">This example shows how to implement pattern-matching constraints on property values because XSD patterns are not supported.</span></span>  
  
 <span data-ttu-id="5c67f-119">Campos como **ClientIdentifier** siempre son una cadena numérica de tres caracteres.</span><span class="sxs-lookup"><span data-stu-id="5c67f-119">Fields such as **ClientIdentifier** are always a three-character numeric string.</span></span> <span data-ttu-id="5c67f-120">De este modo, un valor de propiedad 10 no es válido mientras que 010 sí lo es.</span><span class="sxs-lookup"><span data-stu-id="5c67f-120">A property value of 10 is not valid, whereas 010 is valid.</span></span> <span data-ttu-id="5c67f-121">El siguiente fragmento de esquema de configuración define un **ClientIdentifier** propiedad.</span><span class="sxs-lookup"><span data-stu-id="5c67f-121">The following configuration schema fragment defines a **ClientIdentifier** property.</span></span> <span data-ttu-id="5c67f-122">El **ClientIdentifierConverter** (clase), implementado en su ensamblado de adaptador, implementa la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="5c67f-122">The **ClientIdentifierConverter** class, implemented in your adapter assembly, implements pattern matching.</span></span> <span data-ttu-id="5c67f-123">En este caso, el convertidor de tipos personalizado restringe los valores a una cadena de tres dígitos exactamente (del 000 al 999).</span><span class="sxs-lookup"><span data-stu-id="5c67f-123">In this case, the custom type converter restricts values to a string of exactly three digits (000 to 999).</span></span> <span data-ttu-id="5c67f-124">En el esquema de configuración, asegúrese de que el nodo baf:converter tiene el ensamblado y escriba el conjunto de nombre completo de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="5c67f-124">In the configuration schema, make sure the baf:converter node has the assembly and type full name set correctly.</span></span> <span data-ttu-id="5c67f-125">Si el usuario intenta escribir un valor que no es válido, aparecerá un mensaje de excepción cuando se produzca un error de validación en la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="5c67f-125">If the user attempts to enter a value that is not valid, an exception message pops up when a validation error occurs in the property page.</span></span>  
  
 <span data-ttu-id="5c67f-126">Puede usar el código siguiente en los esquemas de configuración de la página de propiedades del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5c67f-126">You can use the following code in the adapter property page configuration schemas.</span></span>  
  
```  
        <xs:element name="ClientIdentifier" type="xs:string">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer>  
                <baf:displayname>Adapter Client</baf:displayname>  
                <baf:description>Enter the Adapter Client (3 digit string)</baf:description>  
                <baf:converter assembly="%BTSROOT%\\Developer Tools\\Microsoft.BizTalk.TestAdapter.dll">Microsoft.BizTalk.TestAdapter.ClientIdentifierConverter</baf:converter>  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
```  
  
 <span data-ttu-id="5c67f-127">Puede colocar el código siguiente en su ensamblado de adaptador.</span><span class="sxs-lookup"><span data-stu-id="5c67f-127">You can place the following code in your adapter assembly.</span></span>  
  
```  
using System;  
using System.ComponentModel;  
using System.Globalization;  
using System.Text.RegularExpressions;  
  
namespace Microsoft.BizTalk.TestAdapter  
{  
       /// <summary>  
       /// Summary description for ClientIdentifierConverter.  
       /// </summary>  
       public class ClientIdentifierConverter : System.ComponentModel.StringConverter   
       {  
              private void Validate(string value)  
              {  
                     Regex regex = new Regex(@"^\d{3}$"); // ^=begin, \d=digit, {3}=exactly 3 occurrences, $=end  
                     Match match = regex.Match((string)value);  
                     if (!match.Success)  
                     {  
                           throw new ApplicationException("Value does not match pattern \"" + regex.ToString() + "\".");  
                     }  
              }  
  
              public override object ConvertFrom(ITypeDescriptorContext context, CultureInfo culture, object value)  
              {  
                     if (value is string)  
                     {  
                           this.Validate((string)value);  
                     }  
                     return base.ConvertFrom(context, culture, value);  
              }  
  
              public override object ConvertTo(ITypeDescriptorContext context, CultureInfo culture, object value, Type destinationType)  
              {  
                     if (typeof(string) == destinationType && value is string)  
                     {  
                           this.Validate((string)value);  
                     }  
                     return base.ConvertTo(context, culture, value, destinationType);  
              }  
       }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c67f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c67f-128">See Also</span></span>  
 [<span data-ttu-id="5c67f-129">Extensiones de esquema de configuración de marco de trabajo de adaptadores</span><span class="sxs-lookup"><span data-stu-id="5c67f-129">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)