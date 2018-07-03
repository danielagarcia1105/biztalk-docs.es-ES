---
title: Con el tipo de hechos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RuleEngine library
- Business Rule Composer, typed facts
- ITypedFact interface
- DataConnection class
- facts, typed
- TypedDataTable class
- TypedDataRow class
- TypedXmlDocument class
ms.assetid: 8207bfd5-ebd2-45ac-8992-795acdf3ba4c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56fd7d05f6970d8086b9180b0af867c0dcf84119
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000141"
---
# <a name="typed-facts"></a><span data-ttu-id="5d48a-102">Hechos con tipo</span><span class="sxs-lookup"><span data-stu-id="5d48a-102">Typed Facts</span></span>
<span data-ttu-id="5d48a-103">*Con el tipo de hechos* son clases que implementan la **ITypedFact** interfaz: **TypedXmlDocument**, **DataConnection**, **TypedDataTable** , y **TypedDataRow**.</span><span class="sxs-lookup"><span data-stu-id="5d48a-103">*Typed facts* are classes that implement the **ITypedFact** interface: **TypedXmlDocument**, **DataConnection**, **TypedDataTable**, and **TypedDataRow**.</span></span>  

## <a name="typedxmldocument"></a><span data-ttu-id="5d48a-104">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="5d48a-104">TypedXmlDocument</span></span>  
 <span data-ttu-id="5d48a-105">El **TypedXmlDocument** clase representa el tipo de documento XML en el marco de trabajo de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="5d48a-105">The **TypedXmlDocument** class represents the XML document type in the Business Rules Framework.</span></span> <span data-ttu-id="5d48a-106">Cuando se usa un nodo de un documento XML como un argumento en una regla, se crean dos expresiones de XPath: los enlaces de Selector y campo.</span><span class="sxs-lookup"><span data-stu-id="5d48a-106">When you use a node of an XML document as an argument in a rule, two XPath expressions are created: the Selector and Field bindings.</span></span>  

 <span data-ttu-id="5d48a-107">Si el nodo no tiene ningún nodo secundario, un *enlace de Selector* (también conocido como un enlace XmlDocument) se crea para el nodo primario del nodo y un *enlace de campo* (también denominado enlace XmlDocumentMember) se crea en el nodo en Sí.</span><span class="sxs-lookup"><span data-stu-id="5d48a-107">If the node has no child nodes, a *Selector binding* (also known as an XmlDocument binding) is created to the node's parent node and a *Field binding* (also known as an XmlDocumentMember binding) is created to the node itself.</span></span> <span data-ttu-id="5d48a-108">Este enlace de campo depende del enlace de selector.</span><span class="sxs-lookup"><span data-stu-id="5d48a-108">This Field binding is relative to the Selector binding.</span></span> <span data-ttu-id="5d48a-109">Si el nodo tiene nodos secundarios, se crea un enlace de selector en el nodo y no se crea ningún enlace de campo.</span><span class="sxs-lookup"><span data-stu-id="5d48a-109">If the node has child nodes, a Selector binding is created to the node and no Field binding is created.</span></span>  

 <span data-ttu-id="5d48a-110">Supongamos que tiene el siguiente esquema.</span><span class="sxs-lookup"><span data-stu-id="5d48a-110">Suppose that you have the following schema.</span></span>  

 <span data-ttu-id="5d48a-111">![Esquema de ejemplo mostrado en el Explorador de hechos](../core/media/xmldocumentbrowser.gif "xmldocumentbrowser")</span><span class="sxs-lookup"><span data-stu-id="5d48a-111">![Sample schema displayed in Facts Explorer](../core/media/xmldocumentbrowser.gif "xmldocumentbrowser")</span></span>  
<span data-ttu-id="5d48a-112">Case.xsd</span><span class="sxs-lookup"><span data-stu-id="5d48a-112">Case.xsd</span></span>  

 <span data-ttu-id="5d48a-113">Si se selecciona el nodo Income, únicamente se crea un enlace de selector porque el nodo tiene nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="5d48a-113">If the Income node is selected, only a Selector binding is created, because the node has child nodes.</span></span> <span data-ttu-id="5d48a-114">La expresión XPath de forma predeterminada en el **Selector XPath** contiene la propiedad del panel de propiedades:</span><span class="sxs-lookup"><span data-stu-id="5d48a-114">The default XPath expression in the **XPath Selector** property of the Property pane contains:</span></span>  

```  
/*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']/*[local-name()='Income' and namespace-uri()='']  
```  

 <span data-ttu-id="5d48a-115">Sin embargo, si se selecciona el nodo Name, se crean tanto un enlace de selector como un enlace de campo.</span><span class="sxs-lookup"><span data-stu-id="5d48a-115">However, if the Name node is selected, both a Selector binding and a Field binding are created.</span></span> <span data-ttu-id="5d48a-116">La información de enlace es similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="5d48a-116">The binding information looks like.</span></span>  


|      <span data-ttu-id="5d48a-117">Property</span><span class="sxs-lookup"><span data-stu-id="5d48a-117">Property</span></span>      |                                    <span data-ttu-id="5d48a-118">Valor</span><span class="sxs-lookup"><span data-stu-id="5d48a-118">Value</span></span>                                    |
|--------------------|-----------------------------------------------------------------------------|
|  <span data-ttu-id="5d48a-119">**Campo XPath**</span><span class="sxs-lookup"><span data-stu-id="5d48a-119">**XPath Field**</span></span>   |               <span data-ttu-id="5d48a-120">\*[local-name () = 'Name' y espacio ='']</span><span class="sxs-lookup"><span data-stu-id="5d48a-120">\*[local-name()='Name' and namespace-uri()='']</span></span>                |
| <span data-ttu-id="5d48a-121">**Selector XPath**</span><span class="sxs-lookup"><span data-stu-id="5d48a-121">**XPath Selector**</span></span> | <span data-ttu-id="5d48a-122">/\*[local-name () = 'Root' y espacio ='<http://LoansProcessor.Case>']</span><span class="sxs-lookup"><span data-stu-id="5d48a-122">/\*[local-name()='Root' and namespace-uri()='<http://LoansProcessor.Case>']</span></span> |

 <span data-ttu-id="5d48a-123">Las expresiones XPath predeterminadas para los nodos XML se pueden cambiar antes de arrastrar el nodo a un argumento de regla y colocar la información de enlace nueva en la directiva.</span><span class="sxs-lookup"><span data-stu-id="5d48a-123">You can change the default XPath expressions for the XML nodes before you drag the node into a rule argument, and the new binding information is placed in the policy.</span></span> <span data-ttu-id="5d48a-124">No obstante, tenga en cuenta que cualquier cambio realizado a las expresiones XPath debe volver a especificarse en el Compositor de reglas de negocio al volver a cargar el esquema.</span><span class="sxs-lookup"><span data-stu-id="5d48a-124">Note, however, that any edits that are made to the XPath expressions must be re-entered in the Business Rule Composer when the schema is reloaded.</span></span>  

 <span data-ttu-id="5d48a-125">Cuando se crean definiciones de vocabulario para los nodos XML, las expresiones XPath para los enlaces tienen valores predeterminados similares basados en las reglas descritas anteriormente, aunque se pueden modificar en el Asistente para definición de vocabulario.</span><span class="sxs-lookup"><span data-stu-id="5d48a-125">When vocabulary definitions are created for XML nodes, the XPath expressions for the bindings have similar defaults based on the rules described earlier, but can be edited in the Vocabulary Definition Wizard.</span></span> <span data-ttu-id="5d48a-126">Los cambios realizados a las expresiones se ubican en la definición de vocabulario y se ven reflejados en cualquier argumento de regla creado a partir de las definiciones.</span><span class="sxs-lookup"><span data-stu-id="5d48a-126">Changes to the expressions are placed in the vocabulary definition and are reflected in any rule arguments built from the definitions.</span></span>  

## <a name="dataconnection"></a><span data-ttu-id="5d48a-127">DataConnection</span><span class="sxs-lookup"><span data-stu-id="5d48a-127">DataConnection</span></span>  
 <span data-ttu-id="5d48a-128">**DataConnection** se proporciona una clase .NET en el **RuleEngine** biblioteca.</span><span class="sxs-lookup"><span data-stu-id="5d48a-128">**DataConnection** is a .NET class provided in the **RuleEngine** library.</span></span> <span data-ttu-id="5d48a-129">Contiene .NET **SqlConnection** instancia y un **DataSet** nombre.</span><span class="sxs-lookup"><span data-stu-id="5d48a-129">It contains a .NET **SqlConnection** instance and a **DataSet** name.</span></span> <span data-ttu-id="5d48a-130">El **DataSet** nombre le permite crear un identificador único para el **SqlConnection** y se utiliza en la definición del tipo resultante.</span><span class="sxs-lookup"><span data-stu-id="5d48a-130">The **DataSet** name enables you to create a unique identifier for the **SqlConnection** and is used in defining the resulting type.</span></span>  

 <span data-ttu-id="5d48a-131">El **DataConnection** clase proporciona una optimización del rendimiento al motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="5d48a-131">The **DataConnection** class provides a performance optimization to the Business Rule engine.</span></span> <span data-ttu-id="5d48a-132">En vez de imponer en las tablas del motor de base de datos muy grande (**TypedDataTable** clase) que puede contener muchas filas de la base de datos (**TypedDataRow** clase) que no están relacionados con la directiva, puede imponer un ligera **DataConnection**.</span><span class="sxs-lookup"><span data-stu-id="5d48a-132">Rather than asserting into the engine very large database tables (**TypedDataTable** class) that may contain many database rows (**TypedDataRow** class) that are not relevant to the policy, you can assert a lightweight **DataConnection**.</span></span> <span data-ttu-id="5d48a-133">Cuando el motor evalúa una directiva, crea una consulta SELECT según los predicados o acciones de regla y las consultas dinámicamente el **DataConnection** en ejecución.</span><span class="sxs-lookup"><span data-stu-id="5d48a-133">When the engine evaluates a policy, it dynamically builds a SELECT query based on the rule predicates/actions and queries the **DataConnection** at execution.</span></span> <span data-ttu-id="5d48a-134">Por ejemplo, supongamos la siguiente regla:</span><span class="sxs-lookup"><span data-stu-id="5d48a-134">For example, suppose you have the following rule:</span></span>  

```  
IF NorthWind.Products.UnitPrice >= 0   
THEN <do something>  
```  

 <span data-ttu-id="5d48a-135">La siguiente consulta SQL la genera la regla:</span><span class="sxs-lookup"><span data-stu-id="5d48a-135">The following SQL query is generated by from the rule:</span></span>  

```  
Select * From [Product] Where [UnitPrice] >= 0  
```  

 <span data-ttu-id="5d48a-136">Los resultados de la consulta se imponen en el motor en forma de filas de datos.</span><span class="sxs-lookup"><span data-stu-id="5d48a-136">The results of the query are asserted back into the engine as data rows.</span></span>  

> [!NOTE]
>  <span data-ttu-id="5d48a-137">El uso de un **OleDbConnection** en un **DataConnection** no se admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="5d48a-137">The use of an **OleDbConnection** in a **DataConnection** is not currently supported.</span></span>  

 <span data-ttu-id="5d48a-138">Cuando se selecciona una tabla o columna de base de datos para usar en una acción o condición de regla, puede elegir enlazar al objeto mediante **DataConnection** o **TypedDataTable** seleccionando "Conexión de datos" o " La base de datos tabla o fila"desde el **tipo de enlace de la base de datos**cuadro desplegable en la ventana de propiedades para el **bases de datos** pestaña del explorador de hechos.</span><span class="sxs-lookup"><span data-stu-id="5d48a-138">When you select a database table/column to use in a rule condition or action, you can choose to bind to the object using either **DataConnection** or **TypedDataTable** by selecting "Data connection" or "Database table/row" from the **Database binding type**drop-down box in the Property Window for the **Databases** tab of Fact Explorer.</span></span>  

> [!NOTE]
>  <span data-ttu-id="5d48a-139">El enlace DataConnection se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5d48a-139">The DataConnection binding is used by default.</span></span>  

## <a name="typeddatatable"></a><span data-ttu-id="5d48a-140">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="5d48a-140">TypedDataTable</span></span>  
 <span data-ttu-id="5d48a-141">Puede imponer un ADO.NET **DataTable** objeto en el motor, pero se tratará como cualquier otro objeto. NET.</span><span class="sxs-lookup"><span data-stu-id="5d48a-141">You can assert an ADO.NET **DataTable** object into the engine, but it will be treated like any other .NET object.</span></span> <span data-ttu-id="5d48a-142">En la mayoría de los casos en su lugar desea imponer la clase del motor de reglas **TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="5d48a-142">In most cases you will instead want to assert the rule engine class **TypedDataTable**.</span></span>  

 <span data-ttu-id="5d48a-143">**TypedDataTable** es una clase de contenedor que contiene un ADO.NET **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="5d48a-143">**TypedDataTable** is a wrapper class that contains an ADO.NET **DataTable**.</span></span> <span data-ttu-id="5d48a-144">El constructor simplemente toma un **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="5d48a-144">The constructor simply takes a **DataTable**.</span></span> <span data-ttu-id="5d48a-145">Cada vez que una tabla o columna de tabla se utiliza como un argumento de regla, la expresión se evalúa con respecto a la persona **TypedDataRow** contenedores y no con el **TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="5d48a-145">Any time a table or table column is used as a rule argument, the expression is evaluated against the individual **TypedDataRow** wrappers, and not against the **TypedDataTable**.</span></span>  

## <a name="typeddatarow"></a><span data-ttu-id="5d48a-146">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="5d48a-146">TypedDataRow</span></span>  
 <span data-ttu-id="5d48a-147">Se trata de un contenedor de hechos con tipo para ADO **DataRow** objeto.</span><span class="sxs-lookup"><span data-stu-id="5d48a-147">This is a typed fact wrapper for an ADO **DataRow** object.</span></span> <span data-ttu-id="5d48a-148">Arrastrar una tabla o columna a un argumento de regla en el Compositor de reglas basadas en el valor devuelto da como resultado **TypedDataRow** contenedores.</span><span class="sxs-lookup"><span data-stu-id="5d48a-148">Dragging a table or column to a rule argument in the Business Rule Composer results in rules built against the returned **TypedDataRow** wrappers.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5d48a-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d48a-149">See Also</span></span>  
 [<span data-ttu-id="5d48a-150">Hechos</span><span class="sxs-lookup"><span data-stu-id="5d48a-150">Facts</span></span>](../core/facts.md)