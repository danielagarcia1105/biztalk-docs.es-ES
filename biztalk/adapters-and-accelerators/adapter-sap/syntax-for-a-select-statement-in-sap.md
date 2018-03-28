---
title: Sintaxis de una instrucción SELECT en SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SELECT statement, syntax for
ms.assetid: 47120d74-bf41-4622-a6bc-7b8ddc959305
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f57cac0673a6520de4b0d881527bbc7b670ca1b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="syntax-for-a-select-statement-in-sap"></a><span data-ttu-id="345d0-102">Sintaxis de una instrucción SELECT en SAP</span><span class="sxs-lookup"><span data-stu-id="345d0-102">Syntax for a SELECT Statement in SAP</span></span>
<span data-ttu-id="345d0-103">Las siguientes secciones describen las especificaciones de gramática para implementar consultas SELECT sobre la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="345d0-103">The following sections describe grammar specifications for implementing SELECT queries against the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="345d0-104">Tenga en cuenta que, en muchos casos, la sintaxis es un poco diferente de la sintaxis básica de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="345d0-104">Notice that in several cases, the syntax is somewhat different from the base Transact-SQL syntax.</span></span>  
  
```  
SELECT {TOP <const> }[0,1] <select_list>  {INTO FILE [‘file_name’ | “file_name”]   
{DELIMITED}[0,1]}[0,1]  FROM table_name  {AS alias_name }[0,1]    
{INNER JOIN table_name {AS alias_name}[0,1] ON  <Join_Condition>}[0,1]  
{ WHERE <predicate> } [0,1] {;}[0,1]   
[OPTION 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'  
```  
  
 <span data-ttu-id="345d0-105">Donde:</span><span class="sxs-lookup"><span data-stu-id="345d0-105">Where:</span></span>  
  
-   <span data-ttu-id="345d0-106">**<select_list>** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`</span><span class="sxs-lookup"><span data-stu-id="345d0-106">**<select_list>** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`</span></span>  
  
-   <span data-ttu-id="345d0-107">**<Join_Condition>** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`</span><span class="sxs-lookup"><span data-stu-id="345d0-107">**<Join_Condition>** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`</span></span>  
  
-   <span data-ttu-id="345d0-108">**\<predicate\>** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`</span><span class="sxs-lookup"><span data-stu-id="345d0-108">**\<predicate\>** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`</span></span>  
  
 <span data-ttu-id="345d0-109">Las condiciones admitidas y las expresiones son:</span><span class="sxs-lookup"><span data-stu-id="345d0-109">The supported conditions and expressions are:</span></span>  
  
-   <span data-ttu-id="345d0-110">**\<condición\>** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`</span><span class="sxs-lookup"><span data-stu-id="345d0-110">**\<condition\>** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`</span></span>  
  
-   <span data-ttu-id="345d0-111">**\<expr\>** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`</span><span class="sxs-lookup"><span data-stu-id="345d0-111">**\<expr\>** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`</span></span>  
  
 <span data-ttu-id="345d0-112">Donde  **\<const\>** = `integer | real | string | ? | NULL | xml_element`.</span><span class="sxs-lookup"><span data-stu-id="345d0-112">Where **\<const\>** = `integer | real | string | ? | NULL | xml_element`.</span></span>  
  
 <span data-ttu-id="345d0-113">**Valores de la palabra clave de opción**</span><span class="sxs-lookup"><span data-stu-id="345d0-113">**Values for the OPTION Keyword**</span></span>  
  
 <span data-ttu-id="345d0-114">Puede especificar las opciones como `OPTION '<option>'`, donde `<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`</span><span class="sxs-lookup"><span data-stu-id="345d0-114">You can specify the options as `OPTION '<option>'`, where `<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`</span></span>  
  
-   <span data-ttu-id="345d0-115">El **no_conversion** opción:</span><span class="sxs-lookup"><span data-stu-id="345d0-115">The **no_conversion** option:</span></span>  
  
    -   <span data-ttu-id="345d0-116">Si el **no_conversion** opción se utiliza, a continuación, se exponen los campos en la tabla con los tipos .NET equivalentes.</span><span class="sxs-lookup"><span data-stu-id="345d0-116">If the **no_conversion** option is used then the fields in the table are exposed using the equivalent .NET types.</span></span> <span data-ttu-id="345d0-117">Para obtener información sobre el equivalente de .NET de los tipos de datos SAP, consulte [tipos de datos básicos de SAP](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="345d0-117">For information about the .NET equivalent of the SAP data types, see [Basic SAP Data Types](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).</span></span>  
  
    -   <span data-ttu-id="345d0-118">Si el **no_conversion** opción no se utiliza, y si un campo no tiene una conversión de salida definido, a continuación, esos campos en la tabla se exponen mediante los tipos de .NET equivalentes.</span><span class="sxs-lookup"><span data-stu-id="345d0-118">If the **no_conversion** option is not used, and if a field does not have a conversion exit defined then those fields in the table are exposed using the equivalent .NET types.</span></span> <span data-ttu-id="345d0-119">Para obtener información sobre el equivalente de .NET de los tipos de datos SAP, consulte [tipos de datos básicos de SAP](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="345d0-119">For information about the .NET equivalent of the SAP data types, see [Basic SAP Data Types](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).</span></span>  
  
    -   <span data-ttu-id="345d0-120">Cuando el **no_conversion** opción no se utiliza, y si un campo tiene una conversión de salida definido, a continuación, esos campos en la tabla se exponen como cadenas de. NET.</span><span class="sxs-lookup"><span data-stu-id="345d0-120">When the **no_conversion** option is not used, and if a field has a conversion exit defined then those fields in the table are exposed as .NET String.</span></span>  
  
-   <span data-ttu-id="345d0-121">Cuando se establece en **batchsize \<tamaño\>**, la ejecución de la instrucción SELECT hace varias llamadas a ponerse al sistema SAP y en cada llamada, solo \<tamaño\> es el número de registros recuperar.</span><span class="sxs-lookup"><span data-stu-id="345d0-121">When set to **batchsize \<size\>**, the execution of the SELECT statement causes multiple calls to be made to the SAP system, and in each call, only \<size\> number of records are retrieved.</span></span> <span data-ttu-id="345d0-122">Por ejemplo, si especifica ' batchsize 100', la consulta SELECT recupera 100 registros solo en todas las llamadas al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="345d0-122">For example, if you specify 'batchsize 100', the SELECT query retrieves 100 records only in each call to the SAP system.</span></span> <span data-ttu-id="345d0-123">Si **batchsize \<tamaño\>**  no se especifica, se supone que el valor predeterminado de 10.000 para el tamaño del lote.</span><span class="sxs-lookup"><span data-stu-id="345d0-123">If **batchsize \<size\>** is not specified, the default value of 10,000 is assumed for the batch size.</span></span> <span data-ttu-id="345d0-124">Tenga en cuenta que debe especificar un valor óptimo para el tamaño del lote en función de la memoria física del equipo y el número de filas en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="345d0-124">Note that you should specify an optimum value for the batch size based on the physical memory of the computer and the number of rows in the SAP system.</span></span> <span data-ttu-id="345d0-125">Si al especificar un valor para tamaño de lote óptimo puede producir excepciones por memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="345d0-125">Failure in specifying an optimum value for batch size may result in out of memory exceptions.</span></span>  
  
-   <span data-ttu-id="345d0-126">Cuando se establece en **disabledatavalidation**, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no valida los valores presentes en las columnas de DAT, TIM y NUMC pero en su lugar los expone como cadena.</span><span class="sxs-lookup"><span data-stu-id="345d0-126">When set to **disabledatavalidation**, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not validate the values present in the DATS, TIMS, and NUMC columns but instead exposes them as string.</span></span>  
  
     <span data-ttu-id="345d0-127">Esto es útil en escenarios donde los clientes ADO.NET no pueden recuperar datos de una tabla SAP que tiene datos no válidos en columnas DAT, TIM y NUMC.</span><span class="sxs-lookup"><span data-stu-id="345d0-127">This is useful in scenarios where ADO.NET clients fail to retrieve data from an SAP table having invalid data in DATS, TIMS, and NUMC columns.</span></span> <span data-ttu-id="345d0-128">Dado que SAP permite que los datos no válidos en columnas DAT, TIM y NUMC, los clientes ADO.NET al intentar leer los datos no pueda analizar los datos no válidos e iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="345d0-128">Because SAP allows invalid data to be present in DATS, TIMS, and NUMC columns, ADO.NET clients attempting to read the data will not be able to parse the invalid data and will throw an exception.</span></span> <span data-ttu-id="345d0-129">Si el **disabledatavalidation** opción está establecida en la consulta SELECT, la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no analiza los datos no válidos, pero ellos extrae como cadenas.</span><span class="sxs-lookup"><span data-stu-id="345d0-129">If the **disabledatavalidation** option is set on the SELECT query, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not parse the invalid data but extracts them as strings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="345d0-130">Siempre debe proporcionar los valores de la palabra clave de opción entre comillas simples, por ejemplo, '*disabledatavalidation*'.</span><span class="sxs-lookup"><span data-stu-id="345d0-130">You must always provide the values for the OPTION keyword within single quotes, for example, '*disabledatavalidation*'.</span></span>  
  
 <span data-ttu-id="345d0-131">Por ejemplo, vea [ejemplos de la instrucción SELECT](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md).</span><span class="sxs-lookup"><span data-stu-id="345d0-131">For example statements, see [Examples for SELECT Statement](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md).</span></span>  
  
## <a name="predicates-syntax"></a><span data-ttu-id="345d0-132">Sintaxis de predicados</span><span class="sxs-lookup"><span data-stu-id="345d0-132">Predicates Syntax</span></span>  
 <span data-ttu-id="345d0-133">El ejemplo siguiente especifica la gramática para el uso de predicados en una instrucción SELECT:</span><span class="sxs-lookup"><span data-stu-id="345d0-133">The following specifies the grammar for using predicates in a SELECT statement:</span></span>  
  
 <span data-ttu-id="345d0-134">`Predicate`:</span><span class="sxs-lookup"><span data-stu-id="345d0-134">`Predicate`:</span></span>  
  
```  
Predicates [AND | OR] Predicates [between|not between] Predicates | [NOT] Predicates | '(' Predicates ')' | Condition  
```  
  
 <span data-ttu-id="345d0-135">`Condition`:</span><span class="sxs-lookup"><span data-stu-id="345d0-135">`Condition`:</span></span>  
  
```  
Expr | LExpr [NOT] BETWEEN RExpr AND RExpr | LExpr [NOT] LIKE Const  
```  
  
 <span data-ttu-id="345d0-136">`Expr`:</span><span class="sxs-lookup"><span data-stu-id="345d0-136">`Expr`:</span></span>  
  
```  
LExpr [=|!=|>|>=|!>|<|<=|!<] RExpr>  
```  
  
 <span data-ttu-id="345d0-137">`LExpr`:</span><span class="sxs-lookup"><span data-stu-id="345d0-137">`LExpr`:</span></span>  
  
```  
ColumnName  
```  
  
 <span data-ttu-id="345d0-138">`RExpr`:</span><span class="sxs-lookup"><span data-stu-id="345d0-138">`RExpr`:</span></span>  
  
```  
Const | PlaceHolder  
```  
  
 <span data-ttu-id="345d0-139">`ColumnName`:</span><span class="sxs-lookup"><span data-stu-id="345d0-139">`ColumnName`:</span></span>  
  
```  
Column | TableName.Column | '['Column']'  
```  
  
 <span data-ttu-id="345d0-140">`Tablename`:</span><span class="sxs-lookup"><span data-stu-id="345d0-140">`Tablename`:</span></span>  
  
```  
Table | '['Table']'  
```  
  
## <a name="considerations-when-calling-a-select-statement"></a><span data-ttu-id="345d0-141">Consideraciones al llamar a una instrucción SELECT</span><span class="sxs-lookup"><span data-stu-id="345d0-141">Considerations When Calling a SELECT Statement</span></span>  
 <span data-ttu-id="345d0-142">Esta sección enumeran los puntos que debe tener en cuenta al utilizar la instrucción SELECT con [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="345d0-142">This section lists the points that you must keep in mind when using the SELECT statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
-   <span data-ttu-id="345d0-143">Al especificar valores de fecha y hora en parámetros o consultas, proporcione los valores como una cadena.</span><span class="sxs-lookup"><span data-stu-id="345d0-143">When specifying date-time values in parameters or queries, provide the values as a string.</span></span> <span data-ttu-id="345d0-144">Proporcionar cadenas de fecha y hora en el formato de fecha y hora SAP.</span><span class="sxs-lookup"><span data-stu-id="345d0-144">Provide date-time strings in the SAP date-time format.</span></span>  
  
    -   <span data-ttu-id="345d0-145">`SAP date format`: AAAAMMDD</span><span class="sxs-lookup"><span data-stu-id="345d0-145">`SAP date format`: YYYYMMDD</span></span>  
  
         <span data-ttu-id="345d0-146">Por ejemplo, la fecha de 2004 10 de noviembre en una consulta SAP es expresados '20041110'.</span><span class="sxs-lookup"><span data-stu-id="345d0-146">For example, the date 2004 November 10 in a SAP query is expressed '20041110'.</span></span>  
  
         <span data-ttu-id="345d0-147">La fecha de 2004 10 de noviembre en un p1 SAPParameter es la cadena de p1. Valor = '20041110'.</span><span class="sxs-lookup"><span data-stu-id="345d0-147">The date 2004 November 10 in a SAPParameter p1 is the string p1.Value='20041110'.</span></span>  
  
    -   <span data-ttu-id="345d0-148">`SAP time format`: HHMMSS</span><span class="sxs-lookup"><span data-stu-id="345d0-148">`SAP time format`: HHMMSS</span></span>  
  
         <span data-ttu-id="345d0-149">Por ejemplo, la hora 10:34:32 en una consulta SAP es expresados '103432'.</span><span class="sxs-lookup"><span data-stu-id="345d0-149">For example, the time 10:34:32 in a SAP query is expressed '103432'.</span></span>  
  
         <span data-ttu-id="345d0-150">La hora 10:34:32 en SAPParameter p2 es la cadena p2. Valor = '103432'.</span><span class="sxs-lookup"><span data-stu-id="345d0-150">The time 10:34:32 in a SAPParameter p2 is the string p2.Value='103432'.</span></span>  
  
     <span data-ttu-id="345d0-151">Para una instrucción SELECT, la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] devuelve `DATE` valores de campo como .NET `System.DateTime` objetos y devuelve `TIME` campo valores como `System.TimeSpan` objetos.</span><span class="sxs-lookup"><span data-stu-id="345d0-151">For a SELECT statement, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns `DATE` field values as .NET `System.DateTime` objects, and returns `TIME` field values as `System.TimeSpan` objects.</span></span> <span data-ttu-id="345d0-152">Si el valor de SAP `DATE` objeto es menor que el valor mínimo permitido de SQL Server (`1/1/1753`), el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] devuelve este valor mínimo, `1/1/1753`.</span><span class="sxs-lookup"><span data-stu-id="345d0-152">If the value of the SAP `DATE` object is less than the minimum allowable SQL Server value (`1/1/1753`), the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns this minimum value, `1/1/1753`.</span></span>  
  
-   <span data-ttu-id="345d0-153">En la cláusula TOP de una consulta SELECT, al utilizar los caracteres especiales "#", "^", "&" y "%" antes o después de un número entero, se omiten los caracteres especiales, aunque no se genera ningún mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="345d0-153">In the TOP clause of a SELECT query, when using the special characters "#", "^", "&", and "%" before or after an integer, the special characters are ignored, although no error message is raised.</span></span> <span data-ttu-id="345d0-154">Por ejemplo, a continuación se omite en la cláusula TOP de una consulta SELECT:</span><span class="sxs-lookup"><span data-stu-id="345d0-154">For example, the following are ignored in the TOP clause of a SELECT query:</span></span>  
  
     <span data-ttu-id="345d0-155">\#5, 5 ^, %5%, o & 5</span><span class="sxs-lookup"><span data-stu-id="345d0-155">\#5, 5^, %5%, or &5</span></span>  
  
     <span data-ttu-id="345d0-156">Sin embargo, con estos caracteres entre enteros, como en 5, 5$ producirá un error.</span><span class="sxs-lookup"><span data-stu-id="345d0-156">However, using these characters between integers, as in 5$5, does throw an error.</span></span>  
  
-   <span data-ttu-id="345d0-157">Nombres de columna devueltos en un esquema para una tabla se devuelven como todos los caracteres en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="345d0-157">Column names returned in a schema for a table are returned as all uppercase characters.</span></span> <span data-ttu-id="345d0-158">Por ejemplo, Establece el resultado de una consulta en el campo `Last Name` devuelve el encabezado de columna `LAST NAME`.</span><span class="sxs-lookup"><span data-stu-id="345d0-158">For example, a query result set on the field `Last Name` returns the column heading `LAST NAME`.</span></span> <span data-ttu-id="345d0-159">Para evitar la unicidad se recomienda conflictos, con todas las letras mayúsculas en instrucciones SELECT.</span><span class="sxs-lookup"><span data-stu-id="345d0-159">To avoid uniqueness conflicts, using all uppercase in SELECT statements is recommended.</span></span>  
  
-   <span data-ttu-id="345d0-160">En la cláusula LIKE de una consulta SELECT, solo el signo de porcentaje, "%" (para cualquier cadena de cero o más caracteres) y caracteres de subrayado, **"_"** (para cualquier carácter individual) son caracteres especiales permitidos.</span><span class="sxs-lookup"><span data-stu-id="345d0-160">In the LIKE clause of a SELECT query, only the percent sign, "%" (for any string of zero or more characters), and underscore, **"_"** (for any single character), are allowable special characters.</span></span> <span data-ttu-id="345d0-161">Todos los demás caracteres especiales se consideran valores de cadena y se omiten.</span><span class="sxs-lookup"><span data-stu-id="345d0-161">All other special characters are considered string values and are ignored.</span></span>  
  
-   <span data-ttu-id="345d0-162">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] la RFC Z_EXTRACT_DATA_OO se usa para realizar consultas SELECT en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="345d0-162">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses the Z_EXTRACT_DATA_OO RFC to perform SELECT queries on the SAP system.</span></span> <span data-ttu-id="345d0-163">La RFC admite la lectura de datos de tablas que cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="345d0-163">The RFC supports reading data from tables that satisfy the following conditions:</span></span>  
  
    -   <span data-ttu-id="345d0-164">TabClass para la tabla es TRANSP, clúster o un grupo.</span><span class="sxs-lookup"><span data-stu-id="345d0-164">TabClass for the table is TRANSP, CUSTER, or POOL.</span></span>  
  
    -   <span data-ttu-id="345d0-165">TabClass es la vista y ViewClass es D o P.</span><span class="sxs-lookup"><span data-stu-id="345d0-165">TabClass is VIEW and ViewClass is either D or P.</span></span>  
  
     <span data-ttu-id="345d0-166">Asegúrese de que la instrucción SELECT lee los datos de tablas que se cumplen estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="345d0-166">Make sure the SELECT statement reads data from tables that satisfy these conditions.</span></span>  
  
-   <span data-ttu-id="345d0-167">Valores de tipos de datos que pueden tener más de 255 caracteres, por ejemplo de cadena, RAWSTRING, LRAW, VARC y LCHAR no se puede usar en una consulta SELECT.</span><span class="sxs-lookup"><span data-stu-id="345d0-167">Values of data types that can take more than 255 characters, for example STRING, RAWSTRING, LRAW, VARC, and LCHAR cannot be used in a SELECT query.</span></span> <span data-ttu-id="345d0-168">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] usa una RFC personalizada que se incluye con la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], Z_EXTRACT_DATA_OO, para realizar consultas SELECT en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="345d0-168">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC shipped with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], Z_EXTRACT_DATA_OO, to perform SELECT queries on the SAP system.</span></span> <span data-ttu-id="345d0-169">Este RFC personalizada no es compatible con cualquier tipo de datos que puede tener más de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="345d0-169">This custom RFC does not support any data type that can take more than 255 characters.</span></span>  
  
-   <span data-ttu-id="345d0-170">El número máximo de columnas o campos que se admiten en una instrucción SELECT es 1000.</span><span class="sxs-lookup"><span data-stu-id="345d0-170">The maximum number of columns or fields that are supported in a SELECT statement is 1000.</span></span>  
  
-   <span data-ttu-id="345d0-171">El número máximo de predicados que se admiten en una cláusula WHERE es 100.</span><span class="sxs-lookup"><span data-stu-id="345d0-171">The maximum number of predicates supported in a WHERE clause is 100.</span></span>  
  
-   <span data-ttu-id="345d0-172">No se admite la selección de varias veces el mismo campo en la misma instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="345d0-172">Selecting the same field multiple times in the same SELECT statement is not supported.</span></span> <span data-ttu-id="345d0-173">La RFC (Z_EXTRACT_DATA_OO personalizado) utilizado por el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] quita los campos duplicados de la instrucción antes de ejecutar.</span><span class="sxs-lookup"><span data-stu-id="345d0-173">The custom RFC (Z_EXTRACT_DATA_OO) used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] removes the duplicate fields from the statement before executing.</span></span> <span data-ttu-id="345d0-174">Por ejemplo, esta instrucción:</span><span class="sxs-lookup"><span data-stu-id="345d0-174">For example, this statement:</span></span>  
  
     `SELECT BUKRS, BUKRS, BUKRS from T001`  
  
     <span data-ttu-id="345d0-175">se ejecuta como si se escriben como esta instrucción:</span><span class="sxs-lookup"><span data-stu-id="345d0-175">executes as though written like this statement:</span></span>  
  
     `SELECT BUKRS from T001`  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="345d0-176"> no admite nombres de alias duplicados en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="345d0-176"> does not support duplicate alias names in a SELECT statement.</span></span> <span data-ttu-id="345d0-177">Por lo tanto, la siguiente instrucción SELECT produce un error:</span><span class="sxs-lookup"><span data-stu-id="345d0-177">Therefore, the following SELECT statement throws an error:</span></span>  
  
    ```  
    SELECT KUNNR AS [MYKNA1], JMJAH AS MYKNA1 from KNA1 where KUNNR LIKE 'T-S62A08' AND JMJAH=1995  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="345d0-178"> no se admite una instrucción SELECT con nombres de columna duplicados.</span><span class="sxs-lookup"><span data-stu-id="345d0-178"> does not support a SELECT statement with duplicate column names.</span></span> <span data-ttu-id="345d0-179">Por lo tanto, la siguiente instrucción SELECT produce un error:</span><span class="sxs-lookup"><span data-stu-id="345d0-179">Therefore, the following SELECT statement throws an error:</span></span>  
  
    ```  
    SELECT KUNNR AS [MYKNA1], KUNNR AS MYKNA2 from KNA1 where MYKNA2='T-S62A08'  
    ```  
  
-   <span data-ttu-id="345d0-180">SAP no almacenar valores NULL en las tablas.</span><span class="sxs-lookup"><span data-stu-id="345d0-180">SAP does not store NULL values in the tables.</span></span> <span data-ttu-id="345d0-181">Como resultado, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no es compatible con un valor "IS NULL" en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="345d0-181">As a result, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support an "IS NULL" value in a SELECT statement.</span></span> <span data-ttu-id="345d0-182">Por lo tanto, la siguiente instrucción SELECT produce un error:</span><span class="sxs-lookup"><span data-stu-id="345d0-182">Therefore, the following SELECT statement throws an error:</span></span>  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where CITY IS NULL AND NAME1 LIKE '%MODE%'  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="345d0-183"> no admite una cláusula ORDER BY en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="345d0-183"> does not support an ORDER BY clause in a SELECT statement.</span></span> <span data-ttu-id="345d0-184">Por lo tanto, la siguiente instrucción SELECT produce un error:</span><span class="sxs-lookup"><span data-stu-id="345d0-184">Therefore, the following SELECT statement throws an error:</span></span>  
  
    ```  
    SELECT NAME1  AS [MYNAME],  LAND1, KUNNR  from KNA1 where NAME1 LIKE '%MODE%'  ORDER BY NAME1  ASC  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="345d0-185"> no se admite la especificación de un asterisco (\*) para seleccionar todos los campos de una tabla SAP.</span><span class="sxs-lookup"><span data-stu-id="345d0-185"> does not support specifying an asterisk (\*) to select all the fields in an SAP table.</span></span> <span data-ttu-id="345d0-186">Por lo tanto, la siguiente instrucción SELECT produce un error:</span><span class="sxs-lookup"><span data-stu-id="345d0-186">Therefore, the following SELECT statement throws an error:</span></span>  
  
    ```  
    SELECT spfli.* from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
     <span data-ttu-id="345d0-187">Para seleccionar todos los campos, debe especificar los nombres de campo de forma individual.</span><span class="sxs-lookup"><span data-stu-id="345d0-187">To select all the fields, you must specify the field names individually.</span></span>  
  
-   <span data-ttu-id="345d0-188">Como parte de la instrucción SELECT, puede especificar un archivo en el que se escribirá el resultado de la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="345d0-188">As part of the SELECT statement, you can specify a file to which the output of the SELECT statement will be written.</span></span> <span data-ttu-id="345d0-189">Sin embargo, si el archivo de salida está en un recurso compartido de red, asegúrese de que la cuenta de servicio SAP en que se ejecuta el servicio SAP tiene permiso de escritura al recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="345d0-189">However, if the output file is on a network share, make sure the SAP service account under which the SAP service is running has write permission to the network share.</span></span> <span data-ttu-id="345d0-190">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="345d0-190">For example:</span></span>  
  
    ```  
    SELECT * into file '\\share\output.txt' from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
     <span data-ttu-id="345d0-191">En el ejemplo anterior, la cuenta de servicio SAP debe tener permiso de escritura al recurso compartido de red con el nombre "comparten".</span><span class="sxs-lookup"><span data-stu-id="345d0-191">In the preceding example, the SAP service account must have write permission to the network share with the name "share."</span></span>  
  
-   <span data-ttu-id="345d0-192">Una instrucción SELECT utilizando [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] admite nombres de parámetro de valores de argumento en una consulta SELECT.</span><span class="sxs-lookup"><span data-stu-id="345d0-192">A SELECT statement using [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports parameter names for argument values in a SELECT query.</span></span> <span data-ttu-id="345d0-193">Sin embargo, asegúrese de que seguir estas reglas con respecto a los nombres de parámetro:</span><span class="sxs-lookup"><span data-stu-id="345d0-193">However, make sure you follow these rules with respect to parameter names:</span></span>  
  
    -   <span data-ttu-id="345d0-194">En la consulta SELECT, una "@" símbolo debe preceder al nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="345d0-194">In the SELECT query, an "@" symbol must precede the parameter name.</span></span>  
  
    -   <span data-ttu-id="345d0-195">El "@" símbolo debe ir seguido por un carácter alfabético (A-z o a-z).</span><span class="sxs-lookup"><span data-stu-id="345d0-195">The "@" symbol must be followed by an alphabetic character (A-Z or a-z).</span></span>  
  
    -   <span data-ttu-id="345d0-196">El nombre del parámetro puede contener caracteres alfanuméricos (A-z, a-z o 0-9) y caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="345d0-196">The parameter name can contain alphanumeric characters (A-Z, a-z, or 0-9) and special characters.</span></span> <span data-ttu-id="345d0-197">Los únicos caracteres especiales que se pueden incluir en el nombre del parámetro son caracteres de subrayado "_" y el hash "#".</span><span class="sxs-lookup"><span data-stu-id="345d0-197">The only special characters that can be included in the parameter name are underscore "_" and hash "#".</span></span>  
  
-   <span data-ttu-id="345d0-198">Cuando ejecute una consulta SELECT en una vista, asegúrese de que todas las columnas de clave principales de la tabla base también están presentes en la vista.</span><span class="sxs-lookup"><span data-stu-id="345d0-198">When you run a SELECT query on a View, make sure that all the primary key columns of the base table are also present in the View.</span></span> <span data-ttu-id="345d0-199">Además, como un procedimiento, debe marcar las columnas como columnas de clave principal en la vista también.</span><span class="sxs-lookup"><span data-stu-id="345d0-199">Also, as a practice, you must mark the columns as primary key columns in the View also.</span></span>  
  
     <span data-ttu-id="345d0-200">Si no están presentes en la vista de las columnas de clave principales, una consulta SELECT en la vista se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="345d0-200">If the primary key columns are not present in the View, a SELECT query on the View will result in an exception.</span></span>  
  
-   <span data-ttu-id="345d0-201">Al ejecutar una consulta SELECT en una tabla para seleccionar los campos de tipo LRAW, asegúrese de que seleccionar el campo PREC correspondiente.</span><span class="sxs-lookup"><span data-stu-id="345d0-201">When you run a SELECT query on a table to select fields of type LRAW, make sure you select the corresponding PREC field.</span></span> <span data-ttu-id="345d0-202">Además, el campo PREC debe aparecer inmediatamente antes del campo LRAW en la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="345d0-202">Also, the PREC field must appear immediately before the LRAW field in the SELECT clause.</span></span>  
  
     <span data-ttu-id="345d0-203">Cada campo LRAW en una tabla tiene un campo PREC correspondiente que almacena la longitud de datos en el campo LRAW.</span><span class="sxs-lookup"><span data-stu-id="345d0-203">Every LRAW field in a table has a corresponding PREC field that stores the length of data in the LRAW field.</span></span> <span data-ttu-id="345d0-204">Especificar el campo de LRAW en la cláusula SELECT sin el campo PREC puede dar lugar a que se extraen los datos incorrectos.</span><span class="sxs-lookup"><span data-stu-id="345d0-204">Specifying just the LRAW field in the SELECT clause without the PREC field may result in incorrect data being extracted.</span></span>  
  
-   <span data-ttu-id="345d0-205">En un sistema SAP, las comparaciones de caracteres distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="345d0-205">In an SAP system, character comparisons are case sensitive.</span></span> <span data-ttu-id="345d0-206">Por lo tanto, las dos consultas siguientes pueden devolver resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="345d0-206">So, the following two queries may return different results.</span></span>  
  
    ```  
    SELECT * FROM KNA1 WHERE LAND1 LIKE 'D%'  
    ```  
  
     <span data-ttu-id="345d0-207">And</span><span class="sxs-lookup"><span data-stu-id="345d0-207">And</span></span>  
  
    ```  
    SELECT * FROM KNA1 WHERE LAND1 LIKE 'd%'  
    ```  
  
     <span data-ttu-id="345d0-208">Asegúrese de que usar los casos derecha cuando una consulta select de tramas.</span><span class="sxs-lookup"><span data-stu-id="345d0-208">Make sure you use the right cases when framing a select query.</span></span> <span data-ttu-id="345d0-209">Además, en un sistema SAP, no todas las columnas pueden contener caracteres en mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="345d0-209">Also, in an SAP system, not all columns can contain lowercase or uppercase characters.</span></span> <span data-ttu-id="345d0-210">Puede usar la GUI de SAP para averiguar si una columna de una tabla almacena los caracteres en mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="345d0-210">You can use the SAP GUI to find out whether a column in a table stores lowercase or uppercase characters.</span></span> <span data-ttu-id="345d0-211">Para obtener instrucciones sobre cómo usar la GUI de SAP, consulte [determinar si una columna almacenes en minúsculas o mayúsculas valores](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md).</span><span class="sxs-lookup"><span data-stu-id="345d0-211">For instructions on using the SAP GUI, see [Determining Whether a Column Stores Lowercase or Uppercase Values](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md).</span></span>  
  
-   <span data-ttu-id="345d0-212">La condición WHERE solo se admite para la comparación de un valor de campo con algún valor de datos, y *no* con algún otro valor de campo de tabla.</span><span class="sxs-lookup"><span data-stu-id="345d0-212">The WHERE condition is supported only for comparison of a field value with some data value, and *not* with some other table field value.</span></span> <span data-ttu-id="345d0-213">Dado que el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] consulta SELECT admite una única tabla, las consultas de campo de tabla en condiciones de combinación debe usar la condición de combinación para admitir el mismo.</span><span class="sxs-lookup"><span data-stu-id="345d0-213">Because the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports only one table SELECT query, table field queries in join conditions should use the join condition to support the same.</span></span>  
  
-   <span data-ttu-id="345d0-214">Una condición de combinación debe contener un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="345d0-214">A join condition must contain a table name.</span></span>  
  
     <span data-ttu-id="345d0-215">La siguiente es una instrucción SELECT correcta</span><span class="sxs-lookup"><span data-stu-id="345d0-215">The following is a correct SELECT statement</span></span>  
  
    ```  
    select A.x, B.y from A inner join B on A.m = B.n  
    ```  
  
     <span data-ttu-id="345d0-216">La siguiente es una instrucción SELECT incorrecta</span><span class="sxs-lookup"><span data-stu-id="345d0-216">The following is an incorrect SELECT statement</span></span>  
  
    ```  
    select A.x, B.y from A inner join B on m = n  
    ```  
  
-   <span data-ttu-id="345d0-217">En una condición de combinación, la tabla izquierda en una condición de combinación debe estar en el lado izquierdo de la condición y la tabla derecha de la condición de combinación debe especificarse en el lado derecho de la condición de combinación.</span><span class="sxs-lookup"><span data-stu-id="345d0-217">In a join condition, the left table in a join condition should be on the left side of the condition, and the right table of the join condition should be specified on the right side of the join condition.</span></span>  
  
     <span data-ttu-id="345d0-218">La siguiente es la forma correcta de especificar una condición de combinación:</span><span class="sxs-lookup"><span data-stu-id="345d0-218">The following is the correct way of specifying a join condition:</span></span>  
  
    ```  
    select A.x, B.y from A inner join B on A.m = B.n  
    ```  
  
     <span data-ttu-id="345d0-219">La siguiente es una manera de especificar una condición de combinación incorrecta:</span><span class="sxs-lookup"><span data-stu-id="345d0-219">The following is an incorrect way of specifying a join condition:</span></span>  
  
    ```  
    select A.x, B.y from A inner join B on B.n = A.m  
    ```  
  
-   <span data-ttu-id="345d0-220">Una instrucción SELECT solo puede contener una condición de "igual a" en una cláusula de combinación.</span><span class="sxs-lookup"><span data-stu-id="345d0-220">A SELECT statement can only contain an “equal to” condition in a JOIN clause.</span></span> <span data-ttu-id="345d0-221">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="345d0-221">For example:</span></span>  
  
    ```  
    select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
-   <span data-ttu-id="345d0-222">Una instrucción SELECT no recupera columnas de tipo STRING desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="345d0-222">A SELECT statement does not retrieve columns of type STRING from the SAP system.</span></span>  
  
-   <span data-ttu-id="345d0-223">Una instrucción SELECT debe contener solo una combinación única.</span><span class="sxs-lookup"><span data-stu-id="345d0-223">A SELECT statement must contain only a single JOIN.</span></span> <span data-ttu-id="345d0-224">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="345d0-224">For example:</span></span>  
  
    ```  
    select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="345d0-225">Vea también</span><span class="sxs-lookup"><span data-stu-id="345d0-225">See Also</span></span>  
 [<span data-ttu-id="345d0-226">Acerca del proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="345d0-226">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)