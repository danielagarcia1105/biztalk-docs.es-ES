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
# <a name="using-xpaths-in-message-assignments"></a><span data-ttu-id="36597-102">Usar XPaths en las asignaciones de mensajes</span><span class="sxs-lookup"><span data-stu-id="36597-102">Using XPaths in Message Assignments</span></span>
<span data-ttu-id="36597-103">Puede usar el **xpath** función para asignar un valor de XPath para una parte del mensaje, o para asignar un valor a una expresión XPath que hace referencia a una parte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="36597-103">You can use the **xpath** function to assign an XPath value to a message part, or to assign a value to an XPath that refers to a message part.</span></span> <span data-ttu-id="36597-104">Para obtener más información acerca de la asignación a mensajes y partes de mensaje, consulte [construir mensajes](../core/constructing-messages.md).</span><span class="sxs-lookup"><span data-stu-id="36597-104">For more information on assigning to messages and message parts, see [Constructing Messages](../core/constructing-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36597-105">Para obtener más información acerca de la función xpath, consulte la documentación de terceros sobre el lenguaje XML Path (XPath).</span><span class="sxs-lookup"><span data-stu-id="36597-105">For more information on the xpath function, see third-party documentation on the XML Path Language (XPath).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36597-106">El uso de la **xpath** función no se limita a la asignación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="36597-106">The use of the **xpath** function is not limited to message assignment.</span></span> <span data-ttu-id="36597-107">También se puede usar en cualquier expresión; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="36597-107">You can also use it in any expression, for example:</span></span>  
  
```  
If ((System.Double) xpath(_RequestMessage.part, "number(//book[last()]/price)") == 75.00 && (System.Boolean) xpath(msgBoolean, "string(//boolean)") == false)...  
```  
  
> [!NOTE]
>  <span data-ttu-id="36597-108">Si desea asignar un valor a una cadena, utilice la función string() de XPath.</span><span class="sxs-lookup"><span data-stu-id="36597-108">If you want to assign a value to a string, use the XPath string() function.</span></span> <span data-ttu-id="36597-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="36597-109">For example:</span></span>  
  
```  
myString = xpath(msg, "string(/*/book[1]/title)");  
```  
  
> [!NOTE]
>  <span data-ttu-id="36597-110">El motor no es compatible con esquemas, por lo que solo puede leer o escribir valores en los nodos existentes en el mensaje contenedor (debe existir la ruta de acceso completa); de lo contrario, el motor generará una excepción.</span><span class="sxs-lookup"><span data-stu-id="36597-110">The engine is not schema-aware, so you can only read values from or write values to a node that exists in the containing message (the complete path must exist), or the engine will raise an exception.</span></span> <span data-ttu-id="36597-111">Esto ocurre aunque proporcione un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="36597-111">This is true even if you supply a default value.</span></span>  
  
## <a name="assigning-to-an-xpath-in-a-message-part"></a><span data-ttu-id="36597-112">Asignar a una XPath en una parte de mensaje</span><span class="sxs-lookup"><span data-stu-id="36597-112">Assigning to an XPath in a message part</span></span>  
 <span data-ttu-id="36597-113">Considere el esquema siguiente:</span><span class="sxs-lookup"><span data-stu-id="36597-113">Consider the following schema:</span></span>  
  
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
  
 <span data-ttu-id="36597-114">Puede usar la función, tal como se muestra a continuación, para establecer valores en una instancia de documento de ese tipo de esquema:</span><span class="sxs-lookup"><span data-stu-id="36597-114">You can use the  function as follows to set values on a document instance of that schema type:</span></span>  
  
```  
//assumes that a message named _ResponseMessage is already constructed  
_ResponseMessage.part = _RequestMessage.part;  
xpath(_ResponseMessage.part, "/*/book[1]/@country") = "USA";  
xpath(_ResponseMessage.part, "/*/book[1]/title") = "Legends";  
xpath(_ResponseMessage.part, "/*/book[1]/author/FirstName") = "A";  
xpath(_ResponseMessage.part, "/*/book[1]/author/LastName") = "B";  
xpath(_ResponseMessage.part, "/*/book[1]/price") = 50;  
```  
  
## <a name="assigning-to-a-message-part-from-an-xpath"></a><span data-ttu-id="36597-115">Asignar a una parte de mensaje desde una XPath</span><span class="sxs-lookup"><span data-stu-id="36597-115">Assigning to a message part from an XPath</span></span>  
  
```  
//assumes that a message named objMessage is already constructed  
objMessage.BooleanPart = xpath("false()");  
objMessage.IntPart = xpath("100");  
objMessage.StringPart = xpath("'Hello'");  
objMessage.StringPart2 = xpath("'World'");  
```  
  
## <a name="using-xpath-to-assign-from-nodes-and-node-sets"></a><span data-ttu-id="36597-116">Usar XPath para asignar desde nodos y conjuntos de nodos</span><span class="sxs-lookup"><span data-stu-id="36597-116">Using XPath to assign from nodes and node sets</span></span>  
 <span data-ttu-id="36597-117">También puede usar XPath para asignar nodos y conjuntos de nodos XML a un elemento, una clase, un mensaje basado en un esquema o un mensaje basado en una clase XML.</span><span class="sxs-lookup"><span data-stu-id="36597-117">You can also use XPath to assign XML nodes and node sets to an XML element, a class, or a schema-based or class-based message.</span></span>  
  
 <span data-ttu-id="36597-118">Suponga que tiene una clase serializable XML denominada Book. Observe los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="36597-118">Suppose you have an XML-serializable class called Book, and consider the following examples:</span></span>  
  
```  
[Serializable]  
Class Book {...}  
```  
  
 <span data-ttu-id="36597-119">Ejemplo 1: selección del cuarto elemento "book" del catálogo y asignación a una variable "XmlElement":</span><span class="sxs-lookup"><span data-stu-id="36597-119">Example One — select the fourth book element from the catalog, and assign it to an XML element variable:</span></span>  
  
```  
myXmlElement = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="36597-120">Ejemplo 2: selección del cuarto elemento "book" del catálogo y conversión mediante deserialización XML en una instancia de clase "Book":</span><span class="sxs-lookup"><span data-stu-id="36597-120">Example Two — select the fourth book element from the catalog, and convert it using XML deserialization into a Book class instance:</span></span>  
  
```  
myBook = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="36597-121">Ejemplo 3: selección del cuarto elemento "book" del catálogo y conversión en un mensaje de tipo Book:</span><span class="sxs-lookup"><span data-stu-id="36597-121">Example Three — select the fourth book element from the catalog, and convert it a message of type Book:</span></span>  
  
```  
myBookMsg = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="36597-122">Ejemplo 4: selección de todos los elementos "book" del catálogo, donde "MyMethod" usa un "XmlNodeSet" como parámetro:</span><span class="sxs-lookup"><span data-stu-id="36597-122">Example Four — select all book elements in the catalog, where MyMethod takes an XmlNodeSet as a parameter:</span></span>  
  
```  
MyMethod(xpath(myMsg, "/catalog/book"));  
```  
  
 <span data-ttu-id="36597-123">Ejemplo 5: se agrega un elemento "book" al contenedor "BookOfTheMonth":</span><span class="sxs-lookup"><span data-stu-id="36597-123">Example Five — add a book element to the "BookOfTheMonth" container:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BookOfTheMonth") = myBook;  
```  
  
 <span data-ttu-id="36597-124">Ejemplo 6: adición de todos los libros cuyo precio sea 20 o menos a un conjunto de libros recomendados:</span><span class="sxs-lookup"><span data-stu-id="36597-124">Example Six — add all books that are priced at twenty or less to a set of recommended books:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BestPriceBooks") = xpath(MyMsg, "/catalog/book[@price <= 20]");  
```  
  
 <span data-ttu-id="36597-125">Ejemplo 7: llamada a código de usuario que devuelve un elemento XML:</span><span class="sxs-lookup"><span data-stu-id="36597-125">Example Seven — call user code that returns an XML element:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/AdvertisedByPartner") = GetPartnerAdvertisedBook();  
```  
  
 <span data-ttu-id="36597-126">Antes de aplicar los ejemplos 5 y 7:</span><span class="sxs-lookup"><span data-stu-id="36597-126">Before applying examples five and seven:</span></span>  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth/>  
       <BestPriceBooks/>  
       <AdvertisedByPartner/>  
</RecommendedBooks>  
```  
  
 <span data-ttu-id="36597-127">Después de aplicar los ejemplos 5 y 7:</span><span class="sxs-lookup"><span data-stu-id="36597-127">After applying examples five and seven:</span></span>  
  
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