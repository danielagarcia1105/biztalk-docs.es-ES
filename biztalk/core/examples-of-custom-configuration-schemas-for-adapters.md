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
# <a name="examples-of-custom-configuration-schemas-for-adapters"></a>Ejemplos de esquemas de configuración personalizada para los adaptadores
En esta sección se proporcionan los siguientes ejemplos sobre cómo personalizar esquemas de configuración para adaptadores:  
  
-   **Ejemplo 1** muestra un archivo de esquema XSD personalizado completo que representa una página de propiedades de adaptador con las extensiones BAF: Designer y BAF: Description.  
  
-   **Ejemplo 2** también usa las extensiones BAF: Designer y BAF: Description para mostrar cómo crear una ventana de valor de propiedad personalizada para el **BatchSize** propiedad que solo acepte valores entre 1 y 99, inclusive.  
  
-   **Ejemplo 3** muestra cómo se limita BAF: Password a 8 caracteres. De forma predeterminada, se permiten 22 caracteres.  
  
-   **Ejemplo 4** muestra cómo implementar restricciones de coincidencia de patrones en los valores de propiedad porque no se admiten los patrones de XSD.  
  
## <a name="example-1"></a>Ejemplo 1  
 Este ejemplo muestra un esquema XSD personalizado completo. Representa una página de propiedades del adaptador con las extensiones baf:designer y baf:description.  
  
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
  
## <a name="example-2"></a>Ejemplo 2  
 Este ejemplo utiliza las extensiones BAF: Designer y BAF: Description para mostrar cómo crear una ventana de valor de propiedad personalizada para el **BatchSize** propiedad que solo acepte valores entre 1 y 99, inclusive.  
  
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
  
## <a name="example-3"></a>Ejemplo 3  
 Este ejemplo muestra cómo se limita baf:Password a 8 caracteres. De forma predeterminada, se permiten 22 caracteres.  
  
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
  
## <a name="example-4"></a>Ejemplo 4  
 Este ejemplo muestra cómo se implementan restricciones de coincidencia de patrones en los valores de propiedad porque los patrones de XSD no son compatibles.  
  
 Campos como **ClientIdentifier** siempre son una cadena numérica de tres caracteres. De este modo, un valor de propiedad 10 no es válido mientras que 010 sí lo es. El siguiente fragmento de esquema de configuración define un **ClientIdentifier** propiedad. El **ClientIdentifierConverter** (clase), implementado en su ensamblado de adaptador, implementa la coincidencia de patrones. En este caso, el convertidor de tipos personalizado restringe los valores a una cadena de tres dígitos exactamente (del 000 al 999). En el esquema de configuración, asegúrese de que el nodo baf:converter tiene el ensamblado y escriba el conjunto de nombre completo de forma correcta. Si el usuario intenta escribir un valor que no es válido, aparecerá un mensaje de excepción cuando se produzca un error de validación en la página de propiedades.  
  
 Puede usar el código siguiente en los esquemas de configuración de la página de propiedades del adaptador.  
  
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
  
 Puede colocar el código siguiente en su ensamblado de adaptador.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Extensiones de esquema de configuración de marco de trabajo de adaptadores](../core/adapter-framework-configuration-schema-extensions.md)