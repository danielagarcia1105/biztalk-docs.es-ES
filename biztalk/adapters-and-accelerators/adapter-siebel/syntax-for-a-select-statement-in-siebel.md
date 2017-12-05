---
title: "Sintaxis de una instrucción SELECT en Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, searching and sorting data using
- Data Provider for Siebel, SELECT statement
- SELECT statement, syntax for
ms.assetid: 8528b115-d6f3-420d-8617-0e56dc8922bf
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3eeb0a6d4a1fceebe7e16b3f71566f848e4a20f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="syntax-for-a-select-statement-in-siebel"></a><span data-ttu-id="e213d-102">Sintaxis de una instrucción SELECT de Siebel</span><span class="sxs-lookup"><span data-stu-id="e213d-102">Syntax for a SELECT Statement in Siebel</span></span>
<span data-ttu-id="e213d-103">Mediante la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], los clientes ADO.NET pueden realizar una consulta SELECT en componentes empresariales de Siebel mediante la especificación de una cláusula WHERE que representa una especificación de búsqueda de Siebel válida.</span><span class="sxs-lookup"><span data-stu-id="e213d-103">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], ADO.NET clients can perform a SELECT query on Siebel business components by specifying a WHERE clause that represents a valid Siebel search specification.</span></span> <span data-ttu-id="e213d-104">La sintaxis de la instrucción SELECT es:</span><span class="sxs-lookup"><span data-stu-id="e213d-104">The syntax for the SELECT statement is:</span></span>  
  
```  
SELECT  
<column name 1> AS <column alias 1>,  
<column name 2> AS <column alias 2>,  
…  
FROM  
<Business object name>.<Business component name> AS <table alias>  
WHERE  
<filter condition>  
OPTION  
'ViewMode <value>'  
```  
  
 <span data-ttu-id="e213d-105">En la sintaxis anterior, la opción ViewMode corresponde al sistema Siebel modos de vista, que es un mecanismo de filtrado para restringir el conjunto de registros que coinciden con la consulta.</span><span class="sxs-lookup"><span data-stu-id="e213d-105">In the above syntax, the ViewMode option corresponds to the Siebel system View Modes, which is a filtering mechanism to restrict the set of records that match the query.</span></span> <span data-ttu-id="e213d-106">Para el conjunto de valores permitido, consulte la documentación de Siebel.</span><span class="sxs-lookup"><span data-stu-id="e213d-106">For the allowed set of values, see the Siebel documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e213d-107">Si los nombres de campo en la cláusula WHERE contienen caracteres especiales ni espacios en blanco, asegúrese de que siempre incluye los nombres de campo entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="e213d-107">If the field names in the WHERE clause contain special characters or empty spaces, make sure you always enclose the field names within square brackets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e213d-108">En las consultas SELECT que contiene los nombres de alias con caracteres especiales, asegúrese de que incluir los nombres de alias entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="e213d-108">In SELECT queries containing alias names with special characters, make sure you include the alias names within square brackets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e213d-109">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] alias admite nombres para las tablas en la cláusula SELECT, pero no en la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="e213d-109">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports alias names for tables in the SELECT clause but not in the WHERE clause.</span></span>  
  
## <a name="searching-and-sorting-data-using-the-data-provider-for-siebel"></a><span data-ttu-id="e213d-110">Buscar y ordenar los datos mediante el proveedor de datos para Siebel</span><span class="sxs-lookup"><span data-stu-id="e213d-110">Searching and Sorting Data Using the Data Provider for Siebel</span></span>  
 <span data-ttu-id="e213d-111">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] es compatible con una condición de filtro en las instrucciones de SQL basadas en las especificaciones de búsqueda admitidas por el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="e213d-111">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports a filter condition in SQL statements based on the search specifications supported by the Siebel system.</span></span>  
  
 <span data-ttu-id="e213d-112">Las reglas para la especificación de búsqueda son:</span><span class="sxs-lookup"><span data-stu-id="e213d-112">The rules for the search specification are:</span></span>  
  
-   <span data-ttu-id="e213d-113">Operadores de comparación estándar deben utilizarse para comparar un campo con una constante o un campo a otro campo.</span><span class="sxs-lookup"><span data-stu-id="e213d-113">Standard comparison operators must be used to compare a field to a constant, or one field to another field.</span></span> <span data-ttu-id="e213d-114">Puede tratarse de =,! =, >, <>, =, y < =.</span><span class="sxs-lookup"><span data-stu-id="e213d-114">These include =, !=, >, <, >=, and <=.</span></span>  
  
    ```  
    Example: [Revenue] > 5000  
    ```  
  
-   <span data-ttu-id="e213d-115">Constantes de cadena deben ir entre comillas dobles y los valores de cadena deben distinguir mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e213d-115">String constants must be enclosed in double quotation marks, and the string values must be case-sensitive.</span></span>  
  
    ```  
    Example: [Type] != "COST LIST"  
    ```  
  
-   <span data-ttu-id="e213d-116">Los operadores lógicos AND, OR y no debe utilizarse para negar o combinar expresiones.</span><span class="sxs-lookup"><span data-stu-id="e213d-116">The logical operators AND, OR, and NOT must be used to negate or combine expressions.</span></span> <span data-ttu-id="e213d-117">Se omite la distinción entre mayúsculas y en estos operadores; Por ejemplo, "y" es igual a "AND".</span><span class="sxs-lookup"><span data-stu-id="e213d-117">Case sensitivity is ignored in these operators; for example, “and” is the same as “AND”.</span></span>  
  
    ```  
    Example: [Competitor] IS NOT NULL and [Competitor] != "N"  
    ```  
  
-   <span data-ttu-id="e213d-118">Un nombre de campo en una especificación de búsqueda debe incluirse entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="e213d-118">A field name in a search specification must be enclosed in square brackets.</span></span>  
  
    ```  
    Example: [Conflict Id] = 0  
    ```  
  
-   <span data-ttu-id="e213d-119">El operador LIKE se puede utilizar para crear expresiones de comparación en el que un campo se compara con una constante de cadena de texto o un campo a otro campo y una búsqueda de coincidencias en los primeros caracteres varias es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e213d-119">The LIKE operator may be used to create text string comparison expressions in which a field is compared to a constant, or a field to another field and a match on only the first several characters is required.</span></span> <span data-ttu-id="e213d-120">Los caracteres comodín "*"y"?"</span><span class="sxs-lookup"><span data-stu-id="e213d-120">The wildcard characters “*” and “?”</span></span> <span data-ttu-id="e213d-121">debe utilizarse para indicar cualquier número de caracteres y un carácter único, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e213d-121">must be used to indicate any number of characters, and a single character, respectively.</span></span>  
  
-   <span data-ttu-id="e213d-122">Los clientes ADO.NET pueden especificar objetos de negocios de Siebel originales, los componentes empresariales y nombres de campo del componente de negocio.</span><span class="sxs-lookup"><span data-stu-id="e213d-122">ADO.NET clients can specify original Siebel business objects, business components, and business component field names.</span></span> <span data-ttu-id="e213d-123">Estos nombres deben incluirse entre corchetes si contienen espacios en blanco ni caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="e213d-123">These names must be enclosed in square brackets if they contain any special characters or white space.</span></span> <span data-ttu-id="e213d-124">Ejemplos de consultas que se admiten son:</span><span class="sxs-lookup"><span data-stu-id="e213d-124">Examples of queries that are supported are:</span></span>  
  
    ```  
    SELECT [Name], [Postal Code] FROM Account.Account where [Postal Code] != '11065'  
    SELECT [Name], [Postal Code], Id From Account.Account where [Postal Code] != '60626' Order BY Id ASC, Name DESC  
    SELECT * FROM [Admin Price List].[Price Book Items]  
    ```  
  
 <span data-ttu-id="e213d-125">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] admite ordenar especificaciones en instrucciones SQL basándose en la especificación de ordenación compatible con Siebel.</span><span class="sxs-lookup"><span data-stu-id="e213d-125">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports sort specifications in SQL statements based on the sort specification supported by Siebel.</span></span> <span data-ttu-id="e213d-126">Las reglas para la especificación de clasificación son:</span><span class="sxs-lookup"><span data-stu-id="e213d-126">The rules for the sort specification are:</span></span>  
  
-   <span data-ttu-id="e213d-127">Use comas para separar los nombres de campo en una especificación de ordenación; Por ejemplo, nombre, la ubicación</span><span class="sxs-lookup"><span data-stu-id="e213d-127">Use commas to separate field names in a sort specification; for instance, Name, Location</span></span>  
  
-   <span data-ttu-id="e213d-128">Para indicar que un campo en la lista se ordena en orden descendente, incluir (DESC) después del nombre de campo, como en "Fecha de inicio (DESC)."</span><span class="sxs-lookup"><span data-stu-id="e213d-128">To indicate that a field in the list sorts in descending order, include (DESC) after the field name, as in “Start Date (DESC).”</span></span> <span data-ttu-id="e213d-129">Si no se especifica ningún criterio de ordenación, se utiliza el orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="e213d-129">If no sort order is specified, ascending order is used.</span></span> <span data-ttu-id="e213d-130">Para especificar explícitamente el orden ascendente, utilice la palabra clave (ASC).</span><span class="sxs-lookup"><span data-stu-id="e213d-130">To explicitly specify ascending order, use the keyword (ASC).</span></span>  
  
-   <span data-ttu-id="e213d-131">La expresión de la especificación de ordenación debe ser 255 caracteres o menos.</span><span class="sxs-lookup"><span data-stu-id="e213d-131">The sort specification expression must be 255 characters or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e213d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e213d-132">See Also</span></span>  
 [<span data-ttu-id="e213d-133">Usar el proveedor de datos de .NET Framework para aplicaciones de negocio electrónico de Siebel</span><span class="sxs-lookup"><span data-stu-id="e213d-133">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)