---
title: Los esquemas de mensajes para la eliminación básicas Insert, Update y seleccione las operaciones en tablas y vistas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations on tables, message actions for
- table operations, message actions for
- table operations, message structure for
- operations on tables, message schemas for
- table operations, message schemas for
- operations on tables, message structure for
ms.assetid: 8228d5e6-14af-49e0-b34b-be03aea59189
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7f815f88144c2cb3659614c517fdc224c601e27
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989197"
---
# <a name="message-schemas-for-the-basic-insert-update-delete-and-select-operations-on-tables-and-views"></a><span data-ttu-id="03f00-102">Esquemas de mensaje para la inserción básica, actualizar, eliminar y seleccione las operaciones en tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="03f00-102">Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views</span></span>
<span data-ttu-id="03f00-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] superficies básicas inserción, Update, Delete, y las operaciones Select para cada tabla y ver en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="03f00-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces basic Insert, Update, Delete, and Select operations for each table and view in the Oracle database.</span></span> <span data-ttu-id="03f00-104">Estas operaciones realizan la instrucción SQL correspondiente calificada por una cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="03f00-104">These operations perform the appropriate SQL statement qualified by a WHERE clause.</span></span> <span data-ttu-id="03f00-105">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa fuertemente tipados y conjuntos de registros en estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="03f00-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses strongly-typed records and record sets in these operations.</span></span>  

## <a name="message-structure-for-basic-table-operations"></a><span data-ttu-id="03f00-106">Estructura de mensaje para operaciones básicas de tabla</span><span class="sxs-lookup"><span data-stu-id="03f00-106">Message Structure for Basic Table Operations</span></span>  
 <span data-ttu-id="03f00-107">En la tabla siguiente se muestra la estructura del mensaje XML para las operaciones de tabla básico expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en las tablas de base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="03f00-107">The following table shows the XML message structure for the basic table operations exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] on Oracle database tables.</span></span> <span data-ttu-id="03f00-108">La tabla de destino para una operación se especifica en la acción del mensaje y también aparece en el espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="03f00-108">The target table for an operation is specified in the message action and also appears in the target namespace.</span></span>  

### <a name="insert"></a><span data-ttu-id="03f00-109">Insert</span><span class="sxs-lookup"><span data-stu-id="03f00-109">Insert</span></span>  
<span data-ttu-id="03f00-110">Hay los siguientes tipos de operaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="03f00-110">There are the following types of Insert operations.</span></span> <span data-ttu-id="03f00-111">Un mensaje puede contener solamente un tipo de operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="03f00-111">A message can contain only one kind of Insert operation.</span></span>

- <span data-ttu-id="03f00-112">Insertar varios de registro, el conjunto de registros proporcionado de datos fuertemente tipados se inserta en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="03f00-112">Multiple Record Insert inserts the supplied record set of strongly-typed data into the target table.</span></span>
- <span data-ttu-id="03f00-113">Para cada registro en una inserción de varios registros, puede especificar el valor de un atributo opcional denominado **InlineValue**.</span><span class="sxs-lookup"><span data-stu-id="03f00-113">For each record in a multiple record insert, you can specify value for an optional attribute called **InlineValue**.</span></span> <span data-ttu-id="03f00-114">Si se especifica, invalida el valor del elemento.</span><span class="sxs-lookup"><span data-stu-id="03f00-114">If specified, it overrides the value of the element.</span></span>
- <span data-ttu-id="03f00-115">Bulk Insert inserta el conjunto de registros devuelto por una consulta de selección especificada en el elemento de consulta en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="03f00-115">Bulk Insert inserts the record set returned by a SELECT query specified in the QUERY element into the target table.</span></span> <span data-ttu-id="03f00-116">Esto se hace mediante el uso de la lista separada por comas de las columnas especificadas en el elemento COLUMN_NAMES.</span><span class="sxs-lookup"><span data-stu-id="03f00-116">This is done by using the comma-separated list of columns specified in the COLUMN_NAMES element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="03f00-117">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="03f00-117">XML message</span></span>  

<span data-ttu-id="03f00-118">**Inserción de registros múltiples**</span><span class="sxs-lookup"><span data-stu-id="03f00-118">**Multiple record insert**</span></span>  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<RECORDSET>     
<[TABLE_NAME]RECORDINSERT>       
<[FIELD1_NAME InlineValue="value"]>value1</[FIELD1_NAME]>       
<[FIELD2_NAME InlineValue="value"]>value2</[FIELD2_NAME]>       
…     
</[TABLE_NAME]RECORDINSERT>       
<[TABLE_NAME]RECORDINSERT >       
<[FIELD1_NAME InlineValue="value"]>value1</[FIELD1_NAME]>       
<[FIELD2_NAME InlineValue="value"]>value2</[FIELD2_NAME]>       
…     
</[TABLE_NAME]RECORDINSERT>     
…   
</RECORDSET> 
</Insert>
```

<span data-ttu-id="03f00-119">Ejecutado por el adaptador SQL: `INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`</span><span class="sxs-lookup"><span data-stu-id="03f00-119">SQL executed by the adapter: `INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`</span></span>


<span data-ttu-id="03f00-120">**Inserción masiva**</span><span class="sxs-lookup"><span data-stu-id="03f00-120">**Bulk Insert**</span></span>  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>
<QUERY>[SELECT_query]</QUERY>
</Insert>
```

<span data-ttu-id="03f00-121">Ejecutado por el adaptador SQL: `INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`</span><span class="sxs-lookup"><span data-stu-id="03f00-121">SQL executed by the adapter: `INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`</span></span>

### <a name="insert-response"></a><span data-ttu-id="03f00-122">Insertar la respuesta</span><span class="sxs-lookup"><span data-stu-id="03f00-122">Insert Response</span></span>
<span data-ttu-id="03f00-123">Se devuelve el número de filas insertadas en el elemento InsertResult.</span><span class="sxs-lookup"><span data-stu-id="03f00-123">The number of rows inserted is returned in the InsertResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="03f00-124">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="03f00-124">XML message</span></span>  

```
<InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<InsertResult>[rows inserted]</InsertResult> 
</InsertResponse>
```

### <a name="select"></a><span data-ttu-id="03f00-125">Select</span><span class="sxs-lookup"><span data-stu-id="03f00-125">Select</span></span>
<span data-ttu-id="03f00-126">Se realiza una consulta SELECT en la tabla de destino mediante la cláusula WHERE especificada en el elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="03f00-126">A SELECT query is performed on the target table using the WHERE clause specified in the FILTER element.</span></span> <span data-ttu-id="03f00-127">El conjunto de resultados contiene las columnas en la lista separada por comas de nombres de columna especificados en el elemento COLUMN_NAMES.</span><span class="sxs-lookup"><span data-stu-id="03f00-127">The result set contains the columns in the comma-separated list of column names specified in the COLUMN_NAMES element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="03f00-128">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="03f00-128">XML message</span></span>  
```
<Select xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   
<FILTER>WHERE_clause</FILTER> 
</Select>
```

<span data-ttu-id="03f00-129">Ejecutado por el adaptador SQL: `SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="03f00-129">SQL executed by the adapter: `SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`</span></span>

### <a name="select-response"></a><span data-ttu-id="03f00-130">Seleccionar respuesta</span><span class="sxs-lookup"><span data-stu-id="03f00-130">Select Response</span></span>
<span data-ttu-id="03f00-131">El conjunto de resultados generado por la consulta SELECT.</span><span class="sxs-lookup"><span data-stu-id="03f00-131">The result set generated by the SELECT query.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="03f00-132">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="03f00-132">XML message</span></span>  
```
<SelectResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<SelectResult>     
<[TABLE_NAME]RECORDSELECT>       
<[FIELD1_NAME]>value1</[FIELD1_NAME]>       
<[FIELD2_NAME]>value2</[FIELD2_NAME]>       
…     
</[TABLE_NAME]RECORDSELECT>   
</SelectResult> 
</SelectResponse>
``` 

### <a name="update"></a><span data-ttu-id="03f00-133">Update</span><span class="sxs-lookup"><span data-stu-id="03f00-133">Update</span></span>
<span data-ttu-id="03f00-134">Las filas que coinciden con where cláusula especificada en el elemento de filtro se actualizan a los valores especificados en el conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="03f00-134">Rows that match the where clause specified in the FILTER element are updated to the values specified in the RECORDSET.</span></span> <span data-ttu-id="03f00-135">Solo las columnas que se especifican en el conjunto de registros se actualizan en cada fila coincidente.</span><span class="sxs-lookup"><span data-stu-id="03f00-135">Only the columns that are specified in the RECORDSET are updated in each matching row.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="03f00-136">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="03f00-136">XML message</span></span>  
```
<Update xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<RECORDSET>     
<[FIELD1_NAME]>value1</[FIELD1_NAME]>     
<[FIELD2_NAME]>value2</[FIELD2_NAME]>       
…   
</RECORDSET>   
<FILTER>WHERE_clause</FILTER> </Update>
```

<span data-ttu-id="03f00-137">Ejecutado por el adaptador SQL: `UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="03f00-137">SQL executed by the adapter: `UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`</span></span>

### <a name="update-response"></a><span data-ttu-id="03f00-138">Respuesta de actualización</span><span class="sxs-lookup"><span data-stu-id="03f00-138">Update Response</span></span>
<span data-ttu-id="03f00-139">Se devuelve el número de filas actualizadas en el elemento UpdateResult.</span><span class="sxs-lookup"><span data-stu-id="03f00-139">The number of rows updated is returned in the UpdateResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="03f00-140">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="03f00-140">XML message</span></span>  
```
<UpdateResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<UpdateResult>[rows inserted]</UpdateResult> 
</UpdateResponse>
```

### <a name="delete"></a><span data-ttu-id="03f00-141">DELETE</span><span class="sxs-lookup"><span data-stu-id="03f00-141">Delete</span></span>
<span data-ttu-id="03f00-142">Se eliminan las filas que coincidan con la cláusula WHERE especificada por el elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="03f00-142">Rows matching the WHERE clause specified by the FILTER element are deleted.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="03f00-143">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="03f00-143">XML message</span></span> 
```
<Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<FILTER>WHERE_clause</FILTER> 
</Delete>
```

<span data-ttu-id="03f00-144">Ejecutado por el adaptador SQL: `DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="03f00-144">SQL executed by the adapter: `DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`</span></span>

### <a name="delete-response"></a><span data-ttu-id="03f00-145">Respuesta de eliminación</span><span class="sxs-lookup"><span data-stu-id="03f00-145">Delete Response</span></span>
<span data-ttu-id="03f00-146">Se devuelve el número de filas eliminadas en el elemento DeleteResult.</span><span class="sxs-lookup"><span data-stu-id="03f00-146">The number of rows deleted is returned in the DeleteResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="03f00-147">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="03f00-147">XML message</span></span> 
```
<DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<DeleteResult>[rows inserted]</DeleteResult> 
</DeleteResponse>
```

  | <span data-ttu-id="03f00-148">Valor de marcador de posición</span><span class="sxs-lookup"><span data-stu-id="03f00-148">Placeholder value</span></span>| <span data-ttu-id="03f00-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="03f00-149">Description</span></span> |
  | --- | --- |
  | <span data-ttu-id="03f00-150">[VERSIÓN]</span><span class="sxs-lookup"><span data-stu-id="03f00-150">[VERSION]</span></span> | <span data-ttu-id="03f00-151">La cadena de versión de mensaje; Por ejemplo, `http://Microsoft.LobServices.OracleDB/2007/03`</span><span class="sxs-lookup"><span data-stu-id="03f00-151">The message version string; for example, `http://Microsoft.LobServices.OracleDB/2007/03`</span></span>|
  | <span data-ttu-id="03f00-152">[ESQUEMA]</span><span class="sxs-lookup"><span data-stu-id="03f00-152">[SCHEMA]</span></span> | <span data-ttu-id="03f00-153">Colección de artefactos de Oracle; Por ejemplo, `SCOTT`</span><span class="sxs-lookup"><span data-stu-id="03f00-153">Collection of Oracle artifacts; for example, `SCOTT`</span></span>|
  | <span data-ttu-id="03f00-154">[NOMBRETABLA]</span><span class="sxs-lookup"><span data-stu-id="03f00-154">[TABLE_NAME]</span></span> | <span data-ttu-id="03f00-155">Nombre de la tabla; Por ejemplo, `EMP`</span><span class="sxs-lookup"><span data-stu-id="03f00-155">Name of the table; for example, `EMP`</span></span>|
  | <span data-ttu-id="03f00-156">[FIELD1_NAME]</span><span class="sxs-lookup"><span data-stu-id="03f00-156">[FIELD1_NAME]</span></span> | <span data-ttu-id="03f00-157">Nombre de campo de tabla; Por ejemplo, `EMPNAME`</span><span class="sxs-lookup"><span data-stu-id="03f00-157">Table field name; for example, `EMPNAME`</span></span>|
  | <span data-ttu-id="03f00-158">[COLUMN_list]</span><span class="sxs-lookup"><span data-stu-id="03f00-158">[COLUMN_list]</span></span> | <span data-ttu-id="03f00-159">Lista separada por comas de las columnas; Por ejemplo, `NAME`</span><span class="sxs-lookup"><span data-stu-id="03f00-159">Comma-separated list of columns; for example, `NAME`</span></span>|
  | <span data-ttu-id="03f00-160">[SELECT_query]</span><span class="sxs-lookup"><span data-stu-id="03f00-160">[SELECT_query]</span></span> | <span data-ttu-id="03f00-161">Una instrucción SELECT de SQL especificada en el elemento de consulta de una operación Bulk Insert; Por ejemplo, `SELECT * from MyTable`</span><span class="sxs-lookup"><span data-stu-id="03f00-161">A SQL SELECT statement specified in the QUERY element of a Bulk Insert operation; for example, `SELECT * from MyTable`</span></span>|
  | <span data-ttu-id="03f00-162">[WHERE_clause]</span><span class="sxs-lookup"><span data-stu-id="03f00-162">[WHERE_clause]</span></span> | <span data-ttu-id="03f00-163">WHERE_clause para la instrucción SELECT utilizada para la operación. Por ejemplo, `ID > 10`</span><span class="sxs-lookup"><span data-stu-id="03f00-163">WHERE_clause for the SELECT statement used for the operation; for example, `ID > 10`</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="03f00-164">La estructura del mensaje para las operaciones de tabla básico en las vistas es el mismo que en las tablas, pero el espacio de nombres para la operación especifica una vista en lugar de una tabla: `<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`.</span><span class="sxs-lookup"><span data-stu-id="03f00-164">The message structure for the basic table operations on views is the same as that on tables, but the namespace for the operation specifies a view rather than a table: `<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`.</span></span>  

## <a name="message-actions-for-basic-table-operations"></a><span data-ttu-id="03f00-165">Acciones de mensaje para operaciones básicas de tabla</span><span class="sxs-lookup"><span data-stu-id="03f00-165">Message Actions for Basic Table Operations</span></span>  
 <span data-ttu-id="03f00-166">La siguiente tabla muestra las acciones de mensaje utilizados por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para las operaciones de tabla básico en las tablas.</span><span class="sxs-lookup"><span data-stu-id="03f00-166">The following table shows the message actions that are used by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] for the basic table operations on tables.</span></span> <span data-ttu-id="03f00-167">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa el nombre de tabla especificado en la acción de mensaje para determinar la tabla de destino de la operación.</span><span class="sxs-lookup"><span data-stu-id="03f00-167">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the table name specified in the message action to determine the target table of the operation.</span></span>  


|    <span data-ttu-id="03f00-168">Operación</span><span class="sxs-lookup"><span data-stu-id="03f00-168">Operation</span></span>    |                    <span data-ttu-id="03f00-169">Acción de mensaje</span><span class="sxs-lookup"><span data-stu-id="03f00-169">Message Action</span></span>                     |                                    <span data-ttu-id="03f00-170">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03f00-170">Example</span></span>                                    |
|-----------------|-------------------------------------------------------|-------------------------------------------------------------------------------|
|     <span data-ttu-id="03f00-171">Insert</span><span class="sxs-lookup"><span data-stu-id="03f00-171">Insert</span></span>      |     <span data-ttu-id="03f00-172">[Versión] / [esquema] /Table/ [NombreTabla] / inserción</span><span class="sxs-lookup"><span data-stu-id="03f00-172">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Insert</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert      |
| <span data-ttu-id="03f00-173">Insertar la respuesta</span><span class="sxs-lookup"><span data-stu-id="03f00-173">Insert Response</span></span> | <span data-ttu-id="03f00-174">[Versión] / respuesta/Insert//Table/ [NombreTabla] de [esquema]</span><span class="sxs-lookup"><span data-stu-id="03f00-174">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Insert/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert/response |
|     <span data-ttu-id="03f00-175">Select</span><span class="sxs-lookup"><span data-stu-id="03f00-175">Select</span></span>      |     <span data-ttu-id="03f00-176">[Versión] / [esquema] /Table/ [NombreTabla] / seleccione</span><span class="sxs-lookup"><span data-stu-id="03f00-176">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Select</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select      |
| <span data-ttu-id="03f00-177">Seleccionar respuesta</span><span class="sxs-lookup"><span data-stu-id="03f00-177">Select Response</span></span> | <span data-ttu-id="03f00-178">[Versión] / [esquema] /Table/ [NombreTabla] o seleccionar solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="03f00-178">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Select/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select/response |
|     <span data-ttu-id="03f00-179">Update</span><span class="sxs-lookup"><span data-stu-id="03f00-179">Update</span></span>      |     <span data-ttu-id="03f00-180">[Versión] / [esquema] /Table/ [NombreTabla] / actualizar</span><span class="sxs-lookup"><span data-stu-id="03f00-180">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update      |
| <span data-ttu-id="03f00-181">Respuesta de actualización</span><span class="sxs-lookup"><span data-stu-id="03f00-181">Update Response</span></span> | <span data-ttu-id="03f00-182">[Versión] / [NombreTabla] /Table//actualización/respuesta de [esquema]</span><span class="sxs-lookup"><span data-stu-id="03f00-182">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update/response |
|     <span data-ttu-id="03f00-183">DELETE</span><span class="sxs-lookup"><span data-stu-id="03f00-183">Delete</span></span>      |     <span data-ttu-id="03f00-184">[Versión] / [esquema] /Table/ [NombreTabla] / Delete</span><span class="sxs-lookup"><span data-stu-id="03f00-184">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete      |
| <span data-ttu-id="03f00-185">Respuesta de eliminación</span><span class="sxs-lookup"><span data-stu-id="03f00-185">Delete Response</span></span> | <span data-ttu-id="03f00-186">[Versión] / [NombreTabla] /Table//Delete/respuesta de [esquema]</span><span class="sxs-lookup"><span data-stu-id="03f00-186">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete/response |

 <span data-ttu-id="03f00-187">[Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.OracleDB/2007/03.</span><span class="sxs-lookup"><span data-stu-id="03f00-187">[VERSION] = The message version string; for example, http://Microsoft.LobServices.OracleDB/2007/03.</span></span>  

 <span data-ttu-id="03f00-188">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="03f00-188">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  

 <span data-ttu-id="03f00-189">[NombreTabla] = nombre de la tabla; Por ejemplo, EMP.</span><span class="sxs-lookup"><span data-stu-id="03f00-189">[TABLE_NAME] = Name of the table; for example, EMP.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="03f00-190">La acción de mensaje para una operación en una vista es el mismo que para una tabla, salvo que la "Vista" reemplaza "Table"; Por ejemplo, `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`.</span><span class="sxs-lookup"><span data-stu-id="03f00-190">The message action for an operation on a view is the same as that for a table except that "View" replaces "Table"; for example, `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="03f00-191">Vea también</span><span class="sxs-lookup"><span data-stu-id="03f00-191">See Also</span></span>  
 [<span data-ttu-id="03f00-192">Mensajes y esquemas de mensaje para el adaptador de BizTalk para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="03f00-192">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)