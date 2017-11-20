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
# <a name="assert"></a><span data-ttu-id="00ce5-102">Assert</span><span class="sxs-lookup"><span data-stu-id="00ce5-102">Assert</span></span>
<span data-ttu-id="00ce5-103">*Aserción* es el proceso de agregar instancias de objetos en memoria de trabajo del motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="00ce5-103">*Assertion* is the process of adding object instances into the Business Rule engine's working memory.</span></span> <span data-ttu-id="00ce5-104">El motor procesa las instancias de acuerdo con las condiciones y acciones que se escriben en el tipo de instancia, mediante las fases de acción o resolución de conflictos o coincidencias.</span><span class="sxs-lookup"><span data-stu-id="00ce5-104">The engine processes each instance according to the conditions and actions that are written against the type of the instance, using the match-conflict resolution-action phases.</span></span>  
  
 <span data-ttu-id="00ce5-105">Los temas siguientes describen los comportamientos que son el resultado del uso de la **Assert** función para tipos de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="00ce5-105">The following topics describe behaviors that result from using the **Assert** function for different fact types.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="00ce5-106">Objetos .NET</span><span class="sxs-lookup"><span data-stu-id="00ce5-106">.NET Objects</span></span>  
 <span data-ttu-id="00ce5-107">Cada objeto se agrega a la memoria de trabajo como una instancia independiente.</span><span class="sxs-lookup"><span data-stu-id="00ce5-107">Each object is asserted into the working memory as a separate instance.</span></span> <span data-ttu-id="00ce5-108">Esto significa que cada predicado que haga referencia al tipo de objeto analiza la instancia en cuestión (por ejemplo, IF Object.Property = 1).</span><span class="sxs-lookup"><span data-stu-id="00ce5-108">This means that the instance is analyzed by each predicate that references the object's type (for example, IF Object.Property = 1).</span></span> <span data-ttu-id="00ce5-109">También se pone a disposición para aquellas acciones de regla que hagan referencia al tipo, en función de los resultados que se obtengan de las condiciones de regla.</span><span class="sxs-lookup"><span data-stu-id="00ce5-109">It is also made available to rule actions that reference the type, dependent on the results of the rule conditions.</span></span>  
  
 <span data-ttu-id="00ce5-110">Considere el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="00ce5-110">Consider the following example.</span></span>  
  
 <span data-ttu-id="00ce5-111">**Regla 1**</span><span class="sxs-lookup"><span data-stu-id="00ce5-111">**Rule 1**</span></span>  
  
```  
IF A.Value = 1  
THEN A.Status = "good"  
```  
  
 <span data-ttu-id="00ce5-112">**Regla 2**</span><span class="sxs-lookup"><span data-stu-id="00ce5-112">**Rule 2**</span></span>  
  
```  
IF B.Value = 1  
THEN A.Status = "good"  
```  
  
 <span data-ttu-id="00ce5-113">En la regla 1, solo las instancias de un que tienen un valor de 1 tendrán sus **estado** propiedad actualizada.</span><span class="sxs-lookup"><span data-stu-id="00ce5-113">In Rule 1, only those instances of A that have a Value of 1 will have their **Status** property updated.</span></span> <span data-ttu-id="00ce5-114">En la regla 2, sin embargo, si la condición se evalúa como **true**, todas las instancias de A ya tienen su estado actualizado.</span><span class="sxs-lookup"><span data-stu-id="00ce5-114">In Rule 2, however, if the condition evaluates to **true**, all instances of A will have their status updated.</span></span> <span data-ttu-id="00ce5-115">De hecho, si hay varias instancias de B, las instancias se actualizan cada vez que la condición se evalúa como **true** para una instancia de B.</span><span class="sxs-lookup"><span data-stu-id="00ce5-115">In fact, if there are multiple instances of B, the A instances will be updated each time the condition evaluates to **true** for a B instance.</span></span>  
  
 <span data-ttu-id="00ce5-116">Para validar un objeto .NET desde dentro de una regla, puede agregar la integrada **Assert** funcionar como una acción de regla.</span><span class="sxs-lookup"><span data-stu-id="00ce5-116">To assert a .NET object from within a rule, you can add the built-in **Assert** function as a rule action.</span></span> <span data-ttu-id="00ce5-117">Tenga en cuenta que el motor de reglas tiene una **CreateObject** función, pero no se muestra como una función independiente en el Compositor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="00ce5-117">Note that the rule engine has a **CreateObject** function, but it is not displayed as a separate function in the Business Rule Composer.</span></span> <span data-ttu-id="00ce5-118">Su invocación se genera al arrastrar un método de construcción del objeto que desea crear desde la vista Clase .NET del Explorador de hechos hasta el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="00ce5-118">Its invocation is built by dragging the constructor method of the object you wish to create from the .NET Class view of the Facts Explorer to the action pane.</span></span> <span data-ttu-id="00ce5-119">El Compositor de reglas de negocio traduce el método de constructor en un **CreateObject** llamar a en la definición de regla.</span><span class="sxs-lookup"><span data-stu-id="00ce5-119">The Business Rule Composer then translates the constructor method into a **CreateObject** call in the rule definition.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="00ce5-120">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="00ce5-120">TypedXmlDocument</span></span>  
 <span data-ttu-id="00ce5-121">Cuando un **TypedXmlDocument** se impone, el motor de reglas de negocios crea secundarios **TypedXmlDocument** instancias basadas en los selectores definidos en la regla.</span><span class="sxs-lookup"><span data-stu-id="00ce5-121">When a **TypedXmlDocument** is asserted, the Business Rule Engine creates child **TypedXmlDocument** instances based on the selectors defined in the rule.</span></span>  
  
 <span data-ttu-id="00ce5-122">Los selectores y los campos son expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="00ce5-122">Selectors and fields are both XPath expressions.</span></span> <span data-ttu-id="00ce5-123">Los selectores pueden considerarse una forma de aislar los nodos de un documento XML y los campos pueden usarse como elementos específicos de identificación en el selector.</span><span class="sxs-lookup"><span data-stu-id="00ce5-123">You can think of selectors as a way to isolate nodes of an XML document, and fields as identifying specific items within the selector.</span></span> <span data-ttu-id="00ce5-124">El motor agrupa todos los campos de un selector en un objeto.</span><span class="sxs-lookup"><span data-stu-id="00ce5-124">All the fields inside one selector are grouped together as an object by the engine.</span></span> <span data-ttu-id="00ce5-125">Cuando se selecciona un nodo en el **esquemas XML** pestaña en el Explorador de hechos, el Compositor de reglas de negocio se rellena automáticamente el **Selector XPath** propiedad para todos los nodos y el **XPath Field**  propiedad de cualquier nodo que no contiene nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="00ce5-125">When you select a node under the **XML Schemas** tab in the Facts Explorer, the Business Rule Composer automatically fills in the **XPath Selector** property for all nodes, and the **XPath Field** property for any node that does not contain child nodes.</span></span> <span data-ttu-id="00ce5-126">Como alternativa, puede escribir sus propias expresiones de XPath para **Selector XPath** y **XPath Field** si es necesario.</span><span class="sxs-lookup"><span data-stu-id="00ce5-126">Alternatively, you can enter your own XPath expressions for **XPath Selector** and **XPath Field** if necessary.</span></span>  
  
 <span data-ttu-id="00ce5-127">Si el selector coincide con varias partes del documento XML, varios objetos de este tipo se imponen en la memoria de trabajo del motor de reglas o se retiran de ella.</span><span class="sxs-lookup"><span data-stu-id="00ce5-127">If the selector matches multiple portions of the XML document, multiple objects of this type are asserted into or retracted from the rule engine working memory.</span></span> <span data-ttu-id="00ce5-128">Suponga que dispone del siguiente documento XML.</span><span class="sxs-lookup"><span data-stu-id="00ce5-128">Assume you have the following XML.</span></span>  
  
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
  
 <span data-ttu-id="00ce5-129">Si usa el selector /root/order (o //order), se agregan dos objetos a la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="00ce5-129">If you use the selector /root/order (or //order), two objects are added to the working memory.</span></span>  
  
 <span data-ttu-id="00ce5-130">1\)</span><span class="sxs-lookup"><span data-stu-id="00ce5-130">1\)</span></span>  
  
```  
<order customer="Joe">  
   <item name="router" quantity="10" cost="550" />  
   <item name="switch" quantity="3" cost="300" />  
</order>  
```  
  
 <span data-ttu-id="00ce5-131">2\)</span><span class="sxs-lookup"><span data-stu-id="00ce5-131">2\)</span></span>  
  
```  
<order customer="Jane">  
   <item name="switch" quantity="1" cost="300" />  
   <item name="cable" quantity="23" cost="9.99" />  
</order>  
```  
  
 <span data-ttu-id="00ce5-132">En cada selector se hace referencia a los campos individuales mediante XPaths.</span><span class="sxs-lookup"><span data-stu-id="00ce5-132">Within each selector, the individual fields are referred to by XPaths.</span></span>  
  
 <span data-ttu-id="00ce5-133">Si usa el selector /root/order/item (o (//order/item o //item), se agregan cuatro objetos a la memoria de trabajo del motor de reglas, dos elementos para Joe y dos elementos para Jane.</span><span class="sxs-lookup"><span data-stu-id="00ce5-133">If you use the selector /root/order/item (or (//order/item or //item), four objects  are added to the rule engine working memory, the two items for Joe and the two items for Jane.</span></span>  
  
```  
<root>  
   <order customer="Joe">  
  
   </order>  
   <order customer="Jane">  
  
   </order>  
</root>  
```  
  
 <span data-ttu-id="00ce5-134">Cada objeto tiene acceso a los tres campos:@name, @quantity, y @cost.</span><span class="sxs-lookup"><span data-stu-id="00ce5-134">Each object has access to three fields—@name, @quantity, and @cost.</span></span> <span data-ttu-id="00ce5-135">Dado que el objeto es una referencia en el documento original, puede hacer referencia a campos de elemento primario (por ejemplo, "../@customer").</span><span class="sxs-lookup"><span data-stu-id="00ce5-135">Because the object is a reference into the original document, you can refer to parent fields (for example, "../@customer").</span></span>  
  
 <span data-ttu-id="00ce5-136">Puede usar varios selectores en el mismo documento.</span><span class="sxs-lookup"><span data-stu-id="00ce5-136">You can use multiple selectors within the same document.</span></span> <span data-ttu-id="00ce5-137">Esto le permite ver distintas partes del documento. Por ejemplo, si una sección es el pedido y otra contiene la dirección de envío).</span><span class="sxs-lookup"><span data-stu-id="00ce5-137">This enables you to view different parts of the document (for example, if one section is the order and another section contains the shipping address).</span></span> <span data-ttu-id="00ce5-138">No obstante, tenga en cuenta que los objetos creados se definen mediante la cadena XPath que los ha creado.</span><span class="sxs-lookup"><span data-stu-id="00ce5-138">However, keep in mind that the objects that are created are defined by the XPath string that created them.</span></span> <span data-ttu-id="00ce5-139">Uso de una expresión XPath diferente, incluso si se resuelve en el mismo nodo, da como resultado un único **TypedXmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="00ce5-139">Using a different XPath expression, even if it resolves to the same node, results in a unique **TypedXmlDocument**.</span></span>  
  
 <span data-ttu-id="00ce5-140">El motor de reglas admite los tipos escalares básicos de .NET de forma nativa, además de los objetos de los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="00ce5-140">The rule engine supports basic .NET scalar types natively, as well as objects for reference types.</span></span> <span data-ttu-id="00ce5-141">Los documentos XML están formados básicamente de texto, pero el valor de campo puede ser de cualquier tipo en función del tipo que se especificó al generar la regla.</span><span class="sxs-lookup"><span data-stu-id="00ce5-141">XML documents are basically text, but based on the type that was specified when the rule was built, the field value may be of any type.</span></span> <span data-ttu-id="00ce5-142">Además, dado que los campos son expresiones XPath, éstos pueden devolver Nodeset, en cuyo caso se usa como valor el primer elemento del conjunto.</span><span class="sxs-lookup"><span data-stu-id="00ce5-142">Also, because fields are XPath expressions, they may return a nodeset, in which case the first item in the set is used as the value.</span></span>  
  
 <span data-ttu-id="00ce5-143">En segundo plano, el motor de reglas puede convertir un valor de campo de texto en cualquiera de los tipos admitidos a través de la **XmlConvert** función.</span><span class="sxs-lookup"><span data-stu-id="00ce5-143">Behind the scenes, the rule engine can convert a text field value to any one of the supported types through the **XmlConvert** function.</span></span> <span data-ttu-id="00ce5-144">Esto puede especificarse al establecer el tipo en el Compositor de reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="00ce5-144">You can specify this by setting the type in the Business Rule Composer.</span></span> <span data-ttu-id="00ce5-145">Si la conversión no es posible, se lanza una excepción.</span><span class="sxs-lookup"><span data-stu-id="00ce5-145">An exception is thrown if a conversion is not possible.</span></span> <span data-ttu-id="00ce5-146">Los tipos de **bool** y **doble** puede recuperarse únicamente como su tipo correspondiente, cadenas u objetos.</span><span class="sxs-lookup"><span data-stu-id="00ce5-146">The types **bool** and **double** can be retrieved only as their respective type, strings, or objects.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="00ce5-147">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="00ce5-147">TypedDataTable</span></span>  
 <span data-ttu-id="00ce5-148">Cuando un **TypedDataTable** se impone, todos los **DataRows** contenidos en el **DataTable** se imponen automáticamente en el motor como **TypedDataRows**.</span><span class="sxs-lookup"><span data-stu-id="00ce5-148">When a **TypedDataTable** is asserted, all **DataRows** contained in the **DataTable** are automatically asserted into the engine as **TypedDataRows**.</span></span> <span data-ttu-id="00ce5-149">Cada vez que una tabla o columna de tabla se utiliza como un argumento de regla, la expresión se evalúa con cada **TypedDataRows**y no con la **TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="00ce5-149">Any time a table or table column is used as a rule argument, the expression is evaluated against the individual **TypedDataRows**, and not against the **TypedDataTable**.</span></span>  
  
 <span data-ttu-id="00ce5-150">Suponga, por ejemplo, que cuenta con la regla siguiente generada en una tabla "Customers":</span><span class="sxs-lookup"><span data-stu-id="00ce5-150">For example, suppose that you have the following rule built against a "Customers" table:</span></span>  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
> [!NOTE]
>  <span data-ttu-id="00ce5-151">Para crear una regla en una tabla de base de datos, debe usar **tabla o fila de datos** como el tipo de enlace de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="00ce5-151">To build a rule against a database table, you must use **Data table / row** as the database binding type.</span></span>  
  
 <span data-ttu-id="00ce5-152">Suponga que impone la siguiente **DataTable** con tres **DataRows** en el motor (como un **TypedDataTable**).</span><span class="sxs-lookup"><span data-stu-id="00ce5-152">Suppose that you assert the following **DataTable** with three **DataRows** into the engine (as a **TypedDataTable**).</span></span>  
  
|<span data-ttu-id="00ce5-153">CustomerID</span><span class="sxs-lookup"><span data-stu-id="00ce5-153">CustomerID</span></span>|<span data-ttu-id="00ce5-154">ContactTitle</span><span class="sxs-lookup"><span data-stu-id="00ce5-154">ContactTitle</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="00ce5-155">001</span><span class="sxs-lookup"><span data-stu-id="00ce5-155">001</span></span>|<span data-ttu-id="00ce5-156">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="00ce5-156">Supply Clerk</span></span>|  
|<span data-ttu-id="00ce5-157">002</span><span class="sxs-lookup"><span data-stu-id="00ce5-157">002</span></span>|<span data-ttu-id="00ce5-158">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="00ce5-158">Supply Clerk</span></span>|  
|<span data-ttu-id="00ce5-159">003</span><span class="sxs-lookup"><span data-stu-id="00ce5-159">003</span></span>|<span data-ttu-id="00ce5-160">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="00ce5-160">Supply Clerk</span></span>|  
  
 <span data-ttu-id="00ce5-161">El motor inserta tres **TypedDataRows**: 001 y 002, 003.</span><span class="sxs-lookup"><span data-stu-id="00ce5-161">The engine inserts three **TypedDataRows**: 001, 002, and 003.</span></span>  
  
 <span data-ttu-id="00ce5-162">Cada **TypedDataRow** se evalúa respecto a la regla.</span><span class="sxs-lookup"><span data-stu-id="00ce5-162">Each **TypedDataRow** is evaluated independently against the rule.</span></span> <span data-ttu-id="00ce5-163">La primera **TypedDataRow** cumple la condición de regla y las dos segundas fallan.</span><span class="sxs-lookup"><span data-stu-id="00ce5-163">The first **TypedDataRow** meets the rule condition and the second two fail.</span></span> <span data-ttu-id="00ce5-164">Los resultados aparecen de la forma siguiente.</span><span class="sxs-lookup"><span data-stu-id="00ce5-164">The results appear as follows.</span></span>  
  
|<span data-ttu-id="00ce5-165">CustomerID</span><span class="sxs-lookup"><span data-stu-id="00ce5-165">CustomerID</span></span>|<span data-ttu-id="00ce5-166">ContactTitle</span><span class="sxs-lookup"><span data-stu-id="00ce5-166">ContactTitle</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="00ce5-167">001</span><span class="sxs-lookup"><span data-stu-id="00ce5-167">001</span></span>|<span data-ttu-id="00ce5-168">Purchasing Manager</span><span class="sxs-lookup"><span data-stu-id="00ce5-168">Purchasing Manager</span></span>|  
|<span data-ttu-id="00ce5-169">002</span><span class="sxs-lookup"><span data-stu-id="00ce5-169">002</span></span>|<span data-ttu-id="00ce5-170">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="00ce5-170">Supply Clerk</span></span>|  
|<span data-ttu-id="00ce5-171">003</span><span class="sxs-lookup"><span data-stu-id="00ce5-171">003</span></span>|<span data-ttu-id="00ce5-172">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="00ce5-172">Supply Clerk</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="00ce5-173">Las TypedDataRows también pueden imponerse directamente en el motor.</span><span class="sxs-lookup"><span data-stu-id="00ce5-173">TypedDataRows can also be directly asserted into the engine.</span></span> <span data-ttu-id="00ce5-174">Se procesan tal y como se detalló con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="00ce5-174">These are processed in the same way as described earlier.</span></span>  
  
 <span data-ttu-id="00ce5-175">El **DataSetName.DataTableName** se considera que es un identificador único.</span><span class="sxs-lookup"><span data-stu-id="00ce5-175">The **DataSetName.DataTableName** is considered to be a unique identifier.</span></span> <span data-ttu-id="00ce5-176">Por lo tanto, si un segundo **TypedDataTable** se impone con el mismo **conjunto de datos** nombre y **DataTable** nombre, sustituye al primer **TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="00ce5-176">Therefore, if a second **TypedDataTable** is asserted with the same **DataSet** name and **DataTable** name, it supersedes the first **TypedDataTable**.</span></span> <span data-ttu-id="00ce5-177">Todos los **TypedDataRow**que están asociadas a la primera **TypedDataTable** se retiran y el segundo **TypedDataTable** se impone.</span><span class="sxs-lookup"><span data-stu-id="00ce5-177">All **TypedDataRow**s associated with the first **TypedDataTable** are retracted, and the second **TypedDataTable** is asserted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="00ce5-178">DataConnection</span><span class="sxs-lookup"><span data-stu-id="00ce5-178">DataConnection</span></span>  
 <span data-ttu-id="00ce5-179">Al igual que con un **TypedDataTable**, arrastrando una tabla o columna como argumento de regla en el Compositor de reglas de negocios da como resultado reglas basadas en el valor devuelto **TypedDataRow**s en contraposición a la  **DataConnection** propio.</span><span class="sxs-lookup"><span data-stu-id="00ce5-179">As with a **TypedDataTable**, dragging a table or column as a rule argument in the Business Rule Composer results in rules built against the returned **TypedDataRow**s as opposed to the **DataConnection** itself.</span></span>  
  
 <span data-ttu-id="00ce5-180">Suponga que se crea la siguiente regla y un **DataConnection** se impone que contiene un **SqlConnection** a Northwind.Customers:</span><span class="sxs-lookup"><span data-stu-id="00ce5-180">Suppose that the following rule is created and a **DataConnection** is asserted that contains a **SqlConnection** to Northwind.Customers:</span></span>  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
 <span data-ttu-id="00ce5-181">Cuando el motor evalúa la regla usada en el **TypedDataTable** sección, genera dinámicamente una consulta que el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="00ce5-181">When the engine evaluates the rule used in the **TypedDataTable** section, it dynamically builds a query that looks like:</span></span>  
  
```  
SELECT *  
FROM Northwind.Customers  
WHERE CustomerID = 1  
```  
  
 <span data-ttu-id="00ce5-182">Dado que una sola fila en la base de datos cumple este criterio, solo uno **TypedDataRow** se crea y se impone en el motor para su posterior procesamiento.</span><span class="sxs-lookup"><span data-stu-id="00ce5-182">Because only one row in the database meets this criterion, only one **TypedDataRow** is created and asserted into the engine for further processing.</span></span>  
  
## <a name="summary-of-asserted-entities-and-instance-types"></a><span data-ttu-id="00ce5-183">Resumen de tipos de instancia y entidades impuestas</span><span class="sxs-lookup"><span data-stu-id="00ce5-183">Summary of Asserted Entities and Instance Types</span></span>  
 <span data-ttu-id="00ce5-184">En la tabla siguiente se resume el comportamiento que adopta la función Imponer en los distintos tipos. La tabla refleja el número de instancias resultantes que se crean en el motor para cada entidad impuesta y el tipo que se aplica a cada instancia para identificarla.</span><span class="sxs-lookup"><span data-stu-id="00ce5-184">The following table summarizes the assert behavior for the various types, showing the number of resulting instances created in the engine for each asserted entity, as well as the type that is applied to each of those instances to identify them.</span></span>  
  
|<span data-ttu-id="00ce5-185">Entidad</span><span class="sxs-lookup"><span data-stu-id="00ce5-185">Entity</span></span>|<span data-ttu-id="00ce5-186">Número de instancias impuestas</span><span class="sxs-lookup"><span data-stu-id="00ce5-186">Number of instances asserted</span></span>|<span data-ttu-id="00ce5-187">Tipo de instancia</span><span class="sxs-lookup"><span data-stu-id="00ce5-187">Instance type</span></span>|  
|------------|----------------------------------|-------------------|  
|<span data-ttu-id="00ce5-188">Objeto .NET</span><span class="sxs-lookup"><span data-stu-id="00ce5-188">.NET object</span></span>|<span data-ttu-id="00ce5-189">1 (el objeto en sí)</span><span class="sxs-lookup"><span data-stu-id="00ce5-189">1 (the object itself)</span></span>|<span data-ttu-id="00ce5-190">Clase .NET completa</span><span class="sxs-lookup"><span data-stu-id="00ce5-190">Fully Qualified .NET Class</span></span>|  
|<span data-ttu-id="00ce5-191">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="00ce5-191">TypedXmlDocument</span></span>|<span data-ttu-id="00ce5-192">1-N TypedXmlDocument (s): en función de los enlaces de Selector creados y el contenido del documento</span><span class="sxs-lookup"><span data-stu-id="00ce5-192">1-N TypedXmlDocument(s): Based on Selector bindings created and document content</span></span>|<span data-ttu-id="00ce5-193">DocumentType.Selector</span><span class="sxs-lookup"><span data-stu-id="00ce5-193">DocumentType.Selector</span></span>|  
|<span data-ttu-id="00ce5-194">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="00ce5-194">TypedDataTable</span></span>|<span data-ttu-id="00ce5-195">1-N TypedDataRow:</span><span class="sxs-lookup"><span data-stu-id="00ce5-195">1-N TypedDataRow(s):</span></span><br /><br /> <span data-ttu-id="00ce5-196">Una para cada DataRow de la DataTable</span><span class="sxs-lookup"><span data-stu-id="00ce5-196">One for each DataRow in the DataTable</span></span>|<span data-ttu-id="00ce5-197">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="00ce5-197">DataSetName.DataTableName</span></span>|  
|<span data-ttu-id="00ce5-198">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="00ce5-198">TypedDataRow</span></span>|<span data-ttu-id="00ce5-199">1 (la TypedDataRow impuesta)</span><span class="sxs-lookup"><span data-stu-id="00ce5-199">1 (the TypedDataRow asserted)</span></span>|<span data-ttu-id="00ce5-200">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="00ce5-200">DataSetName.DataTableName</span></span>|  
|<span data-ttu-id="00ce5-201">DataConnection</span><span class="sxs-lookup"><span data-stu-id="00ce5-201">DataConnection</span></span>|<span data-ttu-id="00ce5-202">1-N (una para cada TypedDataRow devuelta por la consulta a DataConnection)</span><span class="sxs-lookup"><span data-stu-id="00ce5-202">1-N (one for each TypedDataRow returned by querying the DataConnection)</span></span>|<span data-ttu-id="00ce5-203">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="00ce5-203">DataSetName.DataTableName</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00ce5-204">Vea también</span><span class="sxs-lookup"><span data-stu-id="00ce5-204">See Also</span></span>  
 [<span data-ttu-id="00ce5-205">Funciones de Control del motor</span><span class="sxs-lookup"><span data-stu-id="00ce5-205">Engine Control Functions</span></span>](../core/engine-control-functions.md)