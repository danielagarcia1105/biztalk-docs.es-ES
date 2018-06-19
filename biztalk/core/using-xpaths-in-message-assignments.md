---
title: Usar XPaths en las asignaciones de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XPaths, XPath function
- XPaths, messages
- code samples, XPaths
- messages, XPaths
- XPath function
- XPaths, code samples
- XPaths, nodes
ms.assetid: f2e12409-bb77-4315-b03b-5c7736ae51d5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9ec1e5b56f382601c79324df8651c91c483cb4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288116"
---
# <a name="using-xpaths-in-message-assignments"></a>Usar XPaths en las asignaciones de mensajes
Puede usar el **xpath** función para asignar un valor de XPath para una parte del mensaje, o para asignar un valor a una expresión XPath que hace referencia a una parte del mensaje. Para obtener más información acerca de la asignación a mensajes y partes de mensaje, consulte [construir mensajes](../core/constructing-messages.md).  
  
> [!NOTE]
>  Para obtener más información acerca de la función xpath, consulte la documentación de terceros sobre el lenguaje XML Path (XPath).  
  
> [!NOTE]
>  El uso de la **xpath** función no se limita a la asignación de mensajes. También se puede usar en cualquier expresión; por ejemplo:  
  
```  
If ((System.Double) xpath(_RequestMessage.part, "number(//book[last()]/price)") == 75.00 && (System.Boolean) xpath(msgBoolean, "string(//boolean)") == false)...  
```  
  
> [!NOTE]
>  Si desea asignar un valor a una cadena, utilice la función string() de XPath. Por ejemplo:  
  
```  
myString = xpath(msg, "string(/*/book[1]/title)");  
```  
  
> [!NOTE]
>  El motor no es compatible con esquemas, por lo que solo puede leer o escribir valores en los nodos existentes en el mensaje contenedor (debe existir la ruta de acceso completa); de lo contrario, el motor generará una excepción. Esto ocurre aunque proporcione un valor predeterminado.  
  
## <a name="assigning-to-an-xpath-in-a-message-part"></a>Asignar a una XPath en una parte de mensaje  
 Considere el esquema siguiente:  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="catalog">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element minOccurs="1" maxOccurs="unbounded" name="book">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="title" type="xs:string" />  
              <xs:element name="author">  
                <xs:complexType>  
                  <xs:sequence>  
                    <xs:element name="FirstName" type="xs:string" />  
                    <xs:element name="LastName" type="xs:string" />  
                  </xs:sequence>  
                </xs:complexType>  
              </xs:element>  
              <xs:element name="price" type="xs:string" />  
            </xs:sequence>  
            <xs:attribute name="country" type="xs:string" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 Puede usar la función, tal como se muestra a continuación, para establecer valores en una instancia de documento de ese tipo de esquema:  
  
```  
//assumes that a message named _ResponseMessage is already constructed  
_ResponseMessage.part = _RequestMessage.part;  
xpath(_ResponseMessage.part, "/*/book[1]/@country") = "USA";  
xpath(_ResponseMessage.part, "/*/book[1]/title") = "Legends";  
xpath(_ResponseMessage.part, "/*/book[1]/author/FirstName") = "A";  
xpath(_ResponseMessage.part, "/*/book[1]/author/LastName") = "B";  
xpath(_ResponseMessage.part, "/*/book[1]/price") = 50;  
```  
  
## <a name="assigning-to-a-message-part-from-an-xpath"></a>Asignar a una parte de mensaje desde una XPath  
  
```  
//assumes that a message named objMessage is already constructed  
objMessage.BooleanPart = xpath("false()");  
objMessage.IntPart = xpath("100");  
objMessage.StringPart = xpath("'Hello'");  
objMessage.StringPart2 = xpath("'World'");  
```  
  
## <a name="using-xpath-to-assign-from-nodes-and-node-sets"></a>Usar XPath para asignar desde nodos y conjuntos de nodos  
 También puede usar XPath para asignar nodos y conjuntos de nodos XML a un elemento, una clase, un mensaje basado en un esquema o un mensaje basado en una clase XML.  
  
 Suponga que tiene una clase serializable XML denominada Book. Observe los siguientes ejemplos:  
  
```  
[Serializable]  
Class Book {...}  
```  
  
 Ejemplo 1: selección del cuarto elemento "book" del catálogo y asignación a una variable "XmlElement":  
  
```  
myXmlElement = xpath(myMsg, "/catalog/book[3]");  
```  
  
 Ejemplo 2: selección del cuarto elemento "book" del catálogo y conversión mediante deserialización XML en una instancia de clase "Book":  
  
```  
myBook = xpath(myMsg, "/catalog/book[3]");  
```  
  
 Ejemplo 3: selección del cuarto elemento "book" del catálogo y conversión en un mensaje de tipo Book:  
  
```  
myBookMsg = xpath(myMsg, "/catalog/book[3]");  
```  
  
 Ejemplo 4: selección de todos los elementos "book" del catálogo, donde "MyMethod" usa un "XmlNodeSet" como parámetro:  
  
```  
MyMethod(xpath(myMsg, "/catalog/book"));  
```  
  
 Ejemplo 5: se agrega un elemento "book" al contenedor "BookOfTheMonth":  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BookOfTheMonth") = myBook;  
```  
  
 Ejemplo 6: adición de todos los libros cuyo precio sea 20 o menos a un conjunto de libros recomendados:  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BestPriceBooks") = xpath(MyMsg, "/catalog/book[@price <= 20]");  
```  
  
 Ejemplo 7: llamada a código de usuario que devuelve un elemento XML:  
  
```  
xpath(MyMsg2, "/RecommendedBooks/AdvertisedByPartner") = GetPartnerAdvertisedBook();  
```  
  
 Antes de aplicar los ejemplos 5 y 7:  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth/>  
       <BestPriceBooks/>  
       <AdvertisedByPartner/>  
</RecommendedBooks>  
```  
  
 Después de aplicar los ejemplos 5 y 7:  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth>  
              <Book country="USA">  
                     <title>McSharry</title>  
                     <author>  
                            <FirstName>Nancy</FirstName>  
                            <LastName>Jensen</LastName>  
                     </author>  
              </Book>  
       </BookOfTheMonth>  
       <BestPriceBooks/>  
       <AdvertisedByPartner>  
              <Book country="USA">  
                     <title>The Rooster</title>  
                     <author>  
                            <FirstName>Mindy</FirstName>  
                            <LastName>Martin</LastName>  
                     </author>  
              </Book>  
       </AdvertisedByPartner>  
</RecommendedBooks>  
```