---
title: Esquemas de mensaje para la eliminación de básicas Insert, Update y seleccione las operaciones en tablas y vistas | Documentos de Microsoft
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
ms.openlocfilehash: 571a6a192ca85eb0bd3e5abeb8ef8f3715818236
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216004"
---
# <a name="message-schemas-for-the-basic-insert-update-delete-and-select-operations-on-tables-and-views"></a>Esquemas de mensaje para la inserción básico, actualizar, eliminar y seleccione las operaciones en tablas y vistas
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] superficies básicas inserción, Update, Delete, y las operaciones Select para cada tabla y ver en la base de datos de Oracle. Estas operaciones realizan la instrucción SQL correspondiente calificada por una cláusula WHERE. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa fuertemente tipada de registros y conjuntos de registros en estas operaciones.  
  
## <a name="message-structure-for-basic-table-operations"></a>Estructura de los mensajes para las operaciones de tabla básico  
 En la tabla siguiente se muestra la estructura del mensaje XML para las operaciones de tabla básico expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en tablas de base de datos de Oracle. La tabla de destino para una operación se especifica en la acción de mensaje y también aparece en el espacio de nombres de destino.  

### <a name="insert"></a>Insert  
Hay los siguientes tipos de operaciones de inserción. Un mensaje puede contener solamente un tipo de operación de inserción.

- Insertar varios de registro, el conjunto de registros proporcionado de datos fuertemente tipados se inserta en la tabla de destino.
- Para cada registro en una inserción varios registra, puede especificar el valor para un atributo opcional llamado **InlineValue**. Si se especifica, invalida el valor del elemento.
- Bulk Insert inserta el conjunto de registros devuelto por una consulta de selección especificada en el elemento de consulta en la tabla de destino. Esto se realiza mediante la lista separada por comas de las columnas especificadas en el elemento COLUMN_NAMES.

#### <a name="xml-message"></a>Mensaje XML  

**Inserción de registros múltiples**  
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

SQL ejecutada por el adaptador:`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`


**Inserción masiva**  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>
<QUERY>[SELECT_query]</QUERY>
</Insert>
```

SQL ejecutada por el adaptador:`INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`

### <a name="insert-response"></a>Insertar la respuesta
Se devuelve el número de filas insertadas en el elemento InsertResult.

#### <a name="xml-message"></a>Mensaje XML  

```
<InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<InsertResult>[rows inserted]</InsertResult> 
</InsertResponse>
```

### <a name="select"></a>Select
Se realiza una consulta SELECT en la tabla de destino utilizando la cláusula WHERE especificada en el elemento de filtro. El conjunto de resultados contiene las columnas en la lista separada por comas de nombres de columna especificados en el elemento COLUMN_NAMES.

#### <a name="xml-message"></a>Mensaje XML  
```
<Select xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   
<FILTER>WHERE_clause</FILTER> 
</Select>
```

SQL ejecutada por el adaptador:`SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`

### <a name="select-response"></a>Seleccionar respuesta
El conjunto de resultados generado por la consulta SELECT.

#### <a name="xml-message"></a>Mensaje XML  
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

### <a name="update"></a>Update
Filas que coinciden con where cláusula especificada en el elemento del filtro se actualizan con los valores especificados en el conjunto de registros. Solo las columnas que se especifican en el conjunto de registros se actualizan en cada fila coincidente.

#### <a name="xml-message"></a>Mensaje XML  
```
<Update xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<RECORDSET>     
<[FIELD1_NAME]>value1</[FIELD1_NAME]>     
<[FIELD2_NAME]>value2</[FIELD2_NAME]>       
…   
</RECORDSET>   
<FILTER>WHERE_clause</FILTER> </Update>
```

SQL ejecutada por el adaptador:`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`

### <a name="update-response"></a>Respuesta de actualización
Se devuelve el número de filas actualizadas en el elemento UpdateResult.

#### <a name="xml-message"></a>Mensaje XML  
```
<UpdateResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<UpdateResult>[rows inserted]</UpdateResult> 
</UpdateResponse>
```

### <a name="delete"></a>DELETE
Se eliminan filas que coinciden con la cláusula WHERE especificada por el elemento de filtro.

#### <a name="xml-message"></a>Mensaje XML 
```
<Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<FILTER>WHERE_clause</FILTER> 
</Delete>
```

SQL ejecutada por el adaptador:`DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`

### <a name="delete-response"></a>Respuesta de eliminación
Se devuelve el número de filas eliminadas en el elemento DeleteResult.

#### <a name="xml-message"></a>Mensaje XML 
```
<DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<DeleteResult>[rows inserted]</DeleteResult> 
</DeleteResponse>
```
  
  | Valor de marcador de posición| Description |
  | --- | --- |
  | [VERSIÓN] | La cadena de versión de mensaje; Por ejemplo,`http://Microsoft.LobServices.OracleDB/2007/03`|
  | [ESQUEMA] | Colección de artefactos de Oracle; Por ejemplo,`SCOTT`|
  | [NOMBRETABLA] | Nombre de la tabla; Por ejemplo,`EMP`|
  | [FIELD1_NAME] | Nombre de campo de la tabla; Por ejemplo,`EMPNAME`|
  | [COLUMN_list] | Lista separada por comas de las columnas; Por ejemplo,`NAME`|
  | [SELECT_query] | Una instrucción SELECT de SQL especificada en el elemento de consulta de una operación de inserción masiva; Por ejemplo,`SELECT * from MyTable`|
  | [WHERE_clause] | WHERE_clause para la instrucción SELECT utilizada por la operación; Por ejemplo,`ID > 10`|
  
> [!IMPORTANT]
>  La estructura del mensaje para las operaciones básicas de la tabla en las vistas es el mismo que en las tablas, pero el espacio de nombres para la operación especifica una vista en lugar de una tabla: `<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`.  
  
## <a name="message-actions-for-basic-table-operations"></a>Acciones de mensaje para las operaciones de tabla básico  
 La siguiente tabla muestra las acciones de mensaje utilizados por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para las operaciones básicas de la tabla en tablas. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa el nombre de tabla especificado en la acción de mensaje para determinar la tabla de destino de la operación.  
  
|Operación|Acción de mensaje|Ejemplo|  
|---------------|--------------------|-------------|  
|Insert|[Versión] / [esquema] /Table/ [NombreTabla] / inserción|http://Microsoft.LobServices.oracledb/2007/03/Scott/Table/emp/INSERT|  
|Insertar la respuesta|[Versión] / respuesta/Insert//Table/ [NombreTabla] de [esquema]|http://Microsoft.LobServices.oracledb/2007/03/Scott/Table/emp/INSERT/Response|  
|Select|[Versión] / [esquema] /Table/ [NombreTabla] / Select|http://Microsoft.LobServices.oracledb/2007/03/Scott/Table/emp/SELECT|  
|Seleccionar respuesta|[Versión] / [esquema] /Table/ [NombreTabla] / seleccione solicitud-respuesta|http://Microsoft.LobServices.oracledb/2007/03/Scott/Table/emp/SELECT/Response|  
|Update|[Versión] / [esquema] /Table/ [NombreTabla] o la actualización|http://Microsoft.LobServices.oracledb/2007/03/Scott/Table/emp/Update|  
|Respuesta de actualización|[Versión] / /Table/ [NombreTabla] / actualización/respuesta de [esquema]|http://Microsoft.LobServices.oracledb/2007/03/Scott/Table/emp/Update/Response|  
|DELETE|[Versión] / [esquema] /Table/ [NombreTabla] / eliminar|http://Microsoft.LobServices.oracledb/2007/03/Scott/Table/emp/Delete|  
|Respuesta de eliminación|[Versión] / /Table/ [NombreTabla] / Delete/respuesta de [esquema]|http://Microsoft.LobServices.oracledb/2007/03/Scott/Table/emp/Delete/Response|  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.OracleDB/2007/03.  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [NombreTabla] = nombre de la tabla; Por ejemplo, EMP.  
  
> [!IMPORTANT]
>  La acción de mensaje para una operación en una vista es igual que para una tabla excepto en que "Vista" reemplaza "Table"; Por ejemplo, `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)