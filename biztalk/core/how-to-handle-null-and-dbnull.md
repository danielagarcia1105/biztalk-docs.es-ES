---
title: "Cómo controlar valores Null y DBNull | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: business rules, NULL
ms.assetid: d235c265-4947-470b-9f2d-9936ae1b88a1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b07ac74828a858b368cac5d401081a58b8602323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-handle-null-and-dbnull"></a><span data-ttu-id="60440-102">Cómo controlar valores Null y DBNull</span><span class="sxs-lookup"><span data-stu-id="60440-102">How to Handle Null and DBNull</span></span>
<span data-ttu-id="60440-103">En este tema se describen los comportamientos esperados al trabajar con valores NULL asociados a los diferentes tipos, además de las opciones que permiten comprobar valores nulos o la existencia de un campo o miembro concreto.</span><span class="sxs-lookup"><span data-stu-id="60440-103">This topic describes the expected behaviors when dealing with null values associated with different types, and discusses options for checking null or existence of a particular field or member.</span></span>  
  
## <a name="xml"></a><span data-ttu-id="60440-104">XML</span><span class="sxs-lookup"><span data-stu-id="60440-104">XML</span></span>  
 <span data-ttu-id="60440-105">La siguiente información se aplica a XML:</span><span class="sxs-lookup"><span data-stu-id="60440-105">The following applies to XML:</span></span>  
  
-   <span data-ttu-id="60440-106">Un valor XML nunca será devuelto de un documento como NULL.</span><span class="sxs-lookup"><span data-stu-id="60440-106">An XML value will never be returned from a document as null.</span></span> <span data-ttu-id="60440-107">Se tratará de una cadena vacía o de un error del tipo "no existe".</span><span class="sxs-lookup"><span data-stu-id="60440-107">It is either an empty string or a "does not exist" error.</span></span> <span data-ttu-id="60440-108">Cuando se trata de una cadena vacía, se puede producir un error durante la conversión de determinados tipos, como por ejemplo, los campos especificados como tipo entero al crear reglas.</span><span class="sxs-lookup"><span data-stu-id="60440-108">When it is an empty string, an error may occur for conversion of certain types, for example, fields specified as an integer type when building rules.</span></span>  
  
-   <span data-ttu-id="60440-109">El Compositor de reglas de negocio no permite establecer un campo como null, o para establecer el tipo de un campo para **objeto**.</span><span class="sxs-lookup"><span data-stu-id="60440-109">The Business Rule Composer does not allow you to set a field to null or to set the type of a field to **object**.</span></span>  
  
-   <span data-ttu-id="60440-110">Mediante el modelo de objetos puede establecer el tipo en **objeto**.</span><span class="sxs-lookup"><span data-stu-id="60440-110">Through the object model you can set the type to **Object**.</span></span> <span data-ttu-id="60440-111">En este caso, el valor devuelto es el tipo al que se evalúa la expresión XPath: **float**, **booleano**, o **cadena**, en función de la expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="60440-111">In this case, the value returned is the type to which the XPath evaluates— **float**, **boolean**, or **string**, depending on the XPath expression.</span></span>  
  
## <a name="net-classes"></a><span data-ttu-id="60440-112">clases .NET</span><span class="sxs-lookup"><span data-stu-id="60440-112">.NET classes</span></span>  
 <span data-ttu-id="60440-113">La siguiente información se aplica a las clases .NET:</span><span class="sxs-lookup"><span data-stu-id="60440-113">The following applies to .NET classes:</span></span>  
  
-   <span data-ttu-id="60440-114">No se puede comparar con null si el tipo de valor devuelto no es un **objeto** tipo.</span><span class="sxs-lookup"><span data-stu-id="60440-114">You are not allowed to compare to null if your return type is not an **object** type.</span></span>  
  
-   <span data-ttu-id="60440-115">Puede pasar NULL como parámetro en aquellos parámetros que no sean tipos de valores aunque, dependiendo de la implementación del miembro, es posible que se produzca un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="60440-115">You can pass null as a parameter for parameters that are not value types, but you may get a runtime error, depending on the implementation of the member.</span></span>  
  
-   <span data-ttu-id="60440-116">Puede establecer campos de tipos derivados de **objeto** en null.</span><span class="sxs-lookup"><span data-stu-id="60440-116">You can set fields of types derived from **Object** to null.</span></span>  
  
## <a name="data-connection"></a><span data-ttu-id="60440-117">Conexión de datos</span><span class="sxs-lookup"><span data-stu-id="60440-117">Data connection</span></span>  
 <span data-ttu-id="60440-118">La siguiente información se aplica a una conexión de datos:</span><span class="sxs-lookup"><span data-stu-id="60440-118">The following applies to a data connection:</span></span>  
  
-   <span data-ttu-id="60440-119">Puede comparar cualquier columna de la tabla de base de datos en null, si la tabla admite valores NULL en la columna y el tipo de columna no es **texto**, **ntext**, y **imagen**.</span><span class="sxs-lookup"><span data-stu-id="60440-119">You can compare any database table column to null, if the table allows nulls for the column and the column type is not **text**, **ntext**, and **image**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="60440-120">El Compositor de reglas de negocios le permite usar las columnas de tipo, **texto** y **ntext**, en las condiciones.</span><span class="sxs-lookup"><span data-stu-id="60440-120">The Business Rule Composer allows you to use columns of type, **text** and **ntext**, in conditions.</span></span> <span data-ttu-id="60440-121">Sin embargo, al ejecutar la directiva, recibirá un mensaje de error que indica: "No se pueden comparar ni ordenar los tipos de datos text, ntext e image, excepto cuando se utiliza el operador IS NULL o LIKE".</span><span class="sxs-lookup"><span data-stu-id="60440-121">However, when you execute the policy, you will receive an error message, which says, "The text, ntext, and image data types cannot be compared or sorted, except when using IS NULL or LIKE operator".</span></span>  
  
-   <span data-ttu-id="60440-122">Puede establecer cualquier columna de la tabla de la base de datos como NULL si dicha tabla admite valores NULL en la columna.</span><span class="sxs-lookup"><span data-stu-id="60440-122">You can set any database table column to null, if the table allows nulls for the column.</span></span>  
  
-   <span data-ttu-id="60440-123">El Compositor de reglas de negocio establece automáticamente el tipo de miembro en el enlace **objeto**, si comparar ni establecer como null para un tipo de valor; cambia al tipo original si restablece o reemplaza el argumento.</span><span class="sxs-lookup"><span data-stu-id="60440-123">The Business Rule Composer automatically sets the member type in the binding to **object**, if you compare or set to null for a value type; it changes back to the original type if you reset or replace the argument.</span></span>  
  
-   <span data-ttu-id="60440-124">Para un tipo de cadena, se cambia el tipo a **objeto** si establece en null, pero deja como una cadena si se compara con null.</span><span class="sxs-lookup"><span data-stu-id="60440-124">For a string type, it changes the type to **object** if you set it to null, but leaves it as a string if you compare against null.</span></span>  
  
-   <span data-ttu-id="60440-125">No se puede comparar ni establecer como **DBNull.Value** desde el Compositor de reglas de negocios, ya que no cambiará el tipo de columna **objeto**.</span><span class="sxs-lookup"><span data-stu-id="60440-125">You cannot compare or set to **DBNull.Value** from the Business Rule Composer, because it will not change the column type to **object**.</span></span>  
  
-   <span data-ttu-id="60440-126">El motor convertirá un valor DBNull en NULL para realizar una comparación, y convertirá el valor NULL a un valor DBNull para realizar una operación de inserción en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="60440-126">The engine will convert a DBNull value to null for comparison and will convert null to a DBNull value for insertion into the database.</span></span>  
  
-   <span data-ttu-id="60440-127">Las pruebas omitirán los valores NULL (así es como funciona SQL Server).</span><span class="sxs-lookup"><span data-stu-id="60440-127">Tests will ignore null values (this is the way SQL Server works).</span></span> <span data-ttu-id="60440-128">Por ejemplo, si tiene la regla "IF db.column > 5 THEN .", solo se prueban las filas que tengan un valor en db.column y se omiten las filas con valores NULL.</span><span class="sxs-lookup"><span data-stu-id="60440-128">For example, if you have the rule "IF db.column > 5 THEN .", only the rows that have a value in db.column are tested—rows with null are skipped.</span></span>  
  
## <a name="typeddatatable-and-typeddatarow"></a><span data-ttu-id="60440-129">TypedDataTable y TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="60440-129">TypedDataTable and TypedDataRow</span></span>  
 <span data-ttu-id="60440-130">La siguiente información se aplica a TypedDataTable y a TypedDataRow:</span><span class="sxs-lookup"><span data-stu-id="60440-130">The following applies to TypedDataTable and TypedDataRow:</span></span>  
  
-   <span data-ttu-id="60440-131">El Compositor de reglas de negocio cambia el tipo de campo a **objeto** en la misma manera que con **DataConnection**s.</span><span class="sxs-lookup"><span data-stu-id="60440-131">The Business Rule Composer changes the field type to **object** in the same manner as with **DataConnection**s.</span></span>  
  
-   <span data-ttu-id="60440-132">Las pruebas generarán un error con los valores NULL, a menos que la comparación se realice con valores NULL.</span><span class="sxs-lookup"><span data-stu-id="60440-132">Tests will fail for null values, unless you are comparing to null.</span></span> <span data-ttu-id="60440-133">Por ejemplo, habrá un error en la regla "IF db.column > 5 THEN", si las filas impuestas tiene un valor null.</span><span class="sxs-lookup"><span data-stu-id="60440-133">For example, there will be an error in the rule "IF db.column > 5 THEN ", if any row asserted has a null value.</span></span>  
  
     <span data-ttu-id="60440-134">Tenga en cuenta que, dado que las condiciones se evalúan en paralelo, como pruebas "IF db.column! = NULL AND db.column > 5 THEN" seguirán generando errores porque ambas pruebas se evalúan potencialmente en cada fila.</span><span class="sxs-lookup"><span data-stu-id="60440-134">Note that because conditions are evaluated in parallel, tests like "IF db.column != NULL AND db.column > 5 THEN  " will still fail, because both tests are potentially evaluated on every row.</span></span>  
  
## <a name="checking-for-null-or-existence"></a><span data-ttu-id="60440-135">Comprobar la existencia de campos o de valores NULL</span><span class="sxs-lookup"><span data-stu-id="60440-135">Checking for null or existence</span></span>  
 <span data-ttu-id="60440-136">Al crear reglas de negocios, lo natural es comprobar si un campo existe antes de realizar una comparación con su valor.</span><span class="sxs-lookup"><span data-stu-id="60440-136">When writing business rules, it is natural to check for the existence of a field before comparing its value.</span></span> <span data-ttu-id="60440-137">Sin embargo, si el campo es NULL o no existe, la comparación con el valor generará un error.</span><span class="sxs-lookup"><span data-stu-id="60440-137">However, if the field is null or does not exist, comparing the value will cause an error.</span></span> <span data-ttu-id="60440-138">Imagine que tiene la siguiente regla:</span><span class="sxs-lookup"><span data-stu-id="60440-138">Assume you have the following rule:</span></span>  
  
 <span data-ttu-id="60440-139">Si no existe Product/Quantity AND Product/Quantity > 1</span><span class="sxs-lookup"><span data-stu-id="60440-139">IF Product/Quantity Exists AND Product/Quantity > 1</span></span>  
  
 <span data-ttu-id="60440-140">Se producirá un error en la regla si no existe Product/Quantity.</span><span class="sxs-lookup"><span data-stu-id="60440-140">An error will be thrown in the rule if Product/Quantity does not exist.</span></span> <span data-ttu-id="60440-141">Una de las formas de evitar este problema consiste en transferir un nodo primario a un método auxiliar que devuelva el valor del elemento en caso de que exista, o bien cualquier otro valor si no existe.</span><span class="sxs-lookup"><span data-stu-id="60440-141">One of the ways to circumvent this problem is to pass a parent node to a helper method that returns the element value if it exists or something else if it does not.</span></span> <span data-ttu-id="60440-142">Consulte las siguientes reglas.</span><span class="sxs-lookup"><span data-stu-id="60440-142">See the following rules.</span></span>  
  
 <span data-ttu-id="60440-143">**Regla 1**</span><span class="sxs-lookup"><span data-stu-id="60440-143">**Rule 1**</span></span>  
  
 <span data-ttu-id="60440-144">IF EXISTS(Product/Quantity) THEN ASSERT(CREATEOBJECT(typeof(Helper), Product/Quantity)</span><span class="sxs-lookup"><span data-stu-id="60440-144">IF EXISTS(Product/Quantity) THEN ASSERT(CREATEOBJECT(typeof(Helper), Product/Quantity)</span></span>  
  
 <span data-ttu-id="60440-145">**Regla 2**</span><span class="sxs-lookup"><span data-stu-id="60440-145">**Rule 2**</span></span>  
  
 <span data-ttu-id="60440-146">IF Helper.Value == X THEN...</span><span class="sxs-lookup"><span data-stu-id="60440-146">IF Helper.Value == X THEN...</span></span>  
  
 <span data-ttu-id="60440-147">Otra posible solución consiste en crear una regla similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="60440-147">Another possible solution is to create a rule like the following:</span></span>  
  
 <span data-ttu-id="60440-148">IF Product/Quantity Exist Then CheckQuantityAndDoSomething(Product/Quantity)</span><span class="sxs-lookup"><span data-stu-id="60440-148">IF Product/Quantity Exist Then CheckQuantityAndDoSomething(Product/Quantity)</span></span>  
  
 <span data-ttu-id="60440-149">En el ejemplo anterior, la función CheckQuantityAndDoSomething comprobará el valor del parámetro y se ejecutará si se cumple la condición.</span><span class="sxs-lookup"><span data-stu-id="60440-149">In the preceding example, the CheckQuantityAndDoSomething function will check the parameter value and execute if the condition is met.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60440-150">Como alternativa, puede modificar la expresión XPath **campo** propiedad del hecho XML para detectar los errores, pero no es el enfoque recomendado.</span><span class="sxs-lookup"><span data-stu-id="60440-150">Alternatively, you can modify the XPath **Field** property for the XML fact to catch any errors, but it is not the recommended approach.</span></span>