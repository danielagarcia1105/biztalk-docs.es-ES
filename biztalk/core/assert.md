---
title: Assert | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Assert function [Business Rules Engine], .NET objects
- Assert function [Business Rules Engine], TypedXMLDocument
- Assert function [Business Rules Engine]
- Assert function [Business Rules Engine], examples
- Assert function [Business Rules Engine], TypedData table
- Assert function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e9989214-3c10-4691-9c38-f6fe64e511ed
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2de66aab5cde0a9515f41713d3390632180fbff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="assert"></a>Assert
*Aserción* es el proceso de agregar instancias de objetos en memoria de trabajo del motor de reglas de negocios. El motor procesa las instancias de acuerdo con las condiciones y acciones que se escriben en el tipo de instancia, mediante las fases de acción o resolución de conflictos o coincidencias.  
  
 Los temas siguientes describen los comportamientos que son el resultado del uso de la **Assert** función para tipos de datos diferentes.  
  
## <a name="net-objects"></a>Objetos .NET  
 Cada objeto se agrega a la memoria de trabajo como una instancia independiente. Esto significa que cada predicado que haga referencia al tipo de objeto analiza la instancia en cuestión (por ejemplo, IF Object.Property = 1). También se pone a disposición para aquellas acciones de regla que hagan referencia al tipo, en función de los resultados que se obtengan de las condiciones de regla.  
  
 Considere el ejemplo siguiente.  
  
 **Regla 1**  
  
```  
IF A.Value = 1  
THEN A.Status = "good"  
```  
  
 **Regla 2**  
  
```  
IF B.Value = 1  
THEN A.Status = "good"  
```  
  
 En la regla 1, solo las instancias de un que tienen un valor de 1 tendrán sus **estado** propiedad actualizada. En la regla 2, sin embargo, si la condición se evalúa como **true**, todas las instancias de A ya tienen su estado actualizado. De hecho, si hay varias instancias de B, las instancias se actualizan cada vez que la condición se evalúa como **true** para una instancia de B.  
  
 Para validar un objeto .NET desde dentro de una regla, puede agregar la integrada **Assert** funcionar como una acción de regla. Tenga en cuenta que el motor de reglas tiene una **CreateObject** función, pero no se muestra como una función independiente en el Compositor de reglas de negocios. Su invocación se genera al arrastrar un método de construcción del objeto que desea crear desde la vista Clase .NET del Explorador de hechos hasta el panel de acciones. El Compositor de reglas de negocio traduce el método de constructor en un **CreateObject** llamar a en la definición de regla.  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 Cuando un **TypedXmlDocument** se impone, el motor de reglas de negocios crea secundarios **TypedXmlDocument** instancias basadas en los selectores definidos en la regla.  
  
 Los selectores y los campos son expresiones XPath. Los selectores pueden considerarse una forma de aislar los nodos de un documento XML y los campos pueden usarse como elementos específicos de identificación en el selector. El motor agrupa todos los campos de un selector en un objeto. Cuando se selecciona un nodo en el **esquemas XML** pestaña en el Explorador de hechos, el Compositor de reglas de negocio se rellena automáticamente el **Selector XPath** propiedad para todos los nodos y el **XPath Field**  propiedad de cualquier nodo que no contiene nodos secundarios. Como alternativa, puede escribir sus propias expresiones de XPath para **Selector XPath** y **XPath Field** si es necesario.  
  
 Si el selector coincide con varias partes del documento XML, varios objetos de este tipo se imponen en la memoria de trabajo del motor de reglas o se retiran de ella. Suponga que dispone del siguiente documento XML.  
  
```  
<root>  
   <order customer="Joe">  
      <item name="router" quantity="10" cost="550" />  
      <item name="switch" quantity="3" cost="300" />  
   </order>  
   <order customer="Jane">  
      <item name="switch" quantity="1" cost="300" />  
      <item name="cable" quantity="23" cost="9.99" />  
   </order>  
</root>  
```  
  
 Si usa el selector /root/order (o //order), se agregan dos objetos a la memoria de trabajo.  
  
 1\)  
  
```  
<order customer="Joe">  
   <item name="router" quantity="10" cost="550" />  
   <item name="switch" quantity="3" cost="300" />  
</order>  
```  
  
 2\)  
  
```  
<order customer="Jane">  
   <item name="switch" quantity="1" cost="300" />  
   <item name="cable" quantity="23" cost="9.99" />  
</order>  
```  
  
 En cada selector se hace referencia a los campos individuales mediante XPaths.  
  
 Si usa el selector /root/order/item (o (//order/item o //item), se agregan cuatro objetos a la memoria de trabajo del motor de reglas, dos elementos para Joe y dos elementos para Jane.  
  
```  
<root>  
   <order customer="Joe">  
  
   </order>  
   <order customer="Jane">  
  
   </order>  
</root>  
```  
  
 Cada objeto tiene acceso a los tres campos:@name, @quantity, y @cost. Dado que el objeto es una referencia en el documento original, puede hacer referencia a campos de elemento primario (por ejemplo, "../@customer").  
  
 Puede usar varios selectores en el mismo documento. Esto le permite ver distintas partes del documento. Por ejemplo, si una sección es el pedido y otra contiene la dirección de envío). No obstante, tenga en cuenta que los objetos creados se definen mediante la cadena XPath que los ha creado. Uso de una expresión XPath diferente, incluso si se resuelve en el mismo nodo, da como resultado un único **TypedXmlDocument**.  
  
 El motor de reglas admite los tipos escalares básicos de .NET de forma nativa, además de los objetos de los tipos de referencia. Los documentos XML están formados básicamente de texto, pero el valor de campo puede ser de cualquier tipo en función del tipo que se especificó al generar la regla. Además, dado que los campos son expresiones XPath, éstos pueden devolver Nodeset, en cuyo caso se usa como valor el primer elemento del conjunto.  
  
 En segundo plano, el motor de reglas puede convertir un valor de campo de texto en cualquiera de los tipos admitidos a través de la **XmlConvert** función. Esto puede especificarse al establecer el tipo en el Compositor de reglas de negocio. Si la conversión no es posible, se lanza una excepción. Los tipos de **bool** y **doble** puede recuperarse únicamente como su tipo correspondiente, cadenas u objetos.  
  
## <a name="typeddatatable"></a>TypedDataTable  
 Cuando un **TypedDataTable** se impone, todos los **DataRows** contenidos en el **DataTable** se imponen automáticamente en el motor como **TypedDataRows**. Cada vez que una tabla o columna de tabla se utiliza como un argumento de regla, la expresión se evalúa con cada **TypedDataRows**y no con la **TypedDataTable**.  
  
 Suponga, por ejemplo, que cuenta con la regla siguiente generada en una tabla "Customers":  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
> [!NOTE]
>  Para crear una regla en una tabla de base de datos, debe usar **tabla o fila de datos** como el tipo de enlace de la base de datos.  
  
 Suponga que impone la siguiente **DataTable** con tres **DataRows** en el motor (como un **TypedDataTable**).  
  
|CustomerID|ContactTitle|  
|----------------|------------------|  
|001|Supply Clerk|  
|002|Supply Clerk|  
|003|Supply Clerk|  
  
 El motor inserta tres **TypedDataRows**: 001 y 002, 003.  
  
 Cada **TypedDataRow** se evalúa respecto a la regla. La primera **TypedDataRow** cumple la condición de regla y las dos segundas fallan. Los resultados aparecen de la forma siguiente.  
  
|CustomerID|ContactTitle|  
|----------------|------------------|  
|001|Purchasing Manager|  
|002|Supply Clerk|  
|003|Supply Clerk|  
  
> [!NOTE]
>  Las TypedDataRows también pueden imponerse directamente en el motor. Se procesan tal y como se detalló con anterioridad.  
  
 El **DataSetName.DataTableName** se considera que es un identificador único. Por lo tanto, si un segundo **TypedDataTable** se impone con el mismo **conjunto de datos** nombre y **DataTable** nombre, sustituye al primer **TypedDataTable**. Todos los **TypedDataRow**que están asociadas a la primera **TypedDataTable** se retiran y el segundo **TypedDataTable** se impone.  
  
## <a name="dataconnection"></a>DataConnection  
 Al igual que con un **TypedDataTable**, arrastrando una tabla o columna como argumento de regla en el Compositor de reglas de negocios da como resultado reglas basadas en el valor devuelto **TypedDataRow**s en contraposición a la  **DataConnection** propio.  
  
 Suponga que se crea la siguiente regla y un **DataConnection** se impone que contiene un **SqlConnection** a Northwind.Customers:  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
 Cuando el motor evalúa la regla usada en el **TypedDataTable** sección, genera dinámicamente una consulta que el siguiente aspecto:  
  
```  
SELECT *  
FROM Northwind.Customers  
WHERE CustomerID = 1  
```  
  
 Dado que una sola fila en la base de datos cumple este criterio, solo uno **TypedDataRow** se crea y se impone en el motor para su posterior procesamiento.  
  
## <a name="summary-of-asserted-entities-and-instance-types"></a>Resumen de tipos de instancia y entidades impuestas  
 En la tabla siguiente se resume el comportamiento que adopta la función Imponer en los distintos tipos. La tabla refleja el número de instancias resultantes que se crean en el motor para cada entidad impuesta y el tipo que se aplica a cada instancia para identificarla.  
  
|Entidad|Número de instancias impuestas|Tipo de instancia|  
|------------|----------------------------------|-------------------|  
|Objeto .NET|1 (el objeto en sí)|Clase .NET completa|  
|TypedXmlDocument|1-N TypedXmlDocument (s): en función de los enlaces de Selector creados y el contenido del documento|DocumentType.Selector|  
|TypedDataTable|1-N TypedDataRow:<br /><br /> Una para cada DataRow de la DataTable|DataSetName.DataTableName|  
|TypedDataRow|1 (la TypedDataRow impuesta)|DataSetName.DataTableName|  
|DataConnection|1-N (una para cada TypedDataRow devuelta por la consulta a DataConnection)|DataSetName.DataTableName|  
  
## <a name="see-also"></a>Vea también  
 [Funciones de Control del motor](../core/engine-control-functions.md)