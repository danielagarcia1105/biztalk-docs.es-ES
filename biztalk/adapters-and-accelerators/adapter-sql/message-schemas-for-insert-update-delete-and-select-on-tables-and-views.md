---
title: Esquemas de mensajes para Insert, Update, Delete y seleccione las operaciones en tablas y vistas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fff9cd3-26c0-4d5c-8162-3fd7966a5020
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73270b3d096a8d72de5b339835737cc74d264c9c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "25967218"
---
# <a name="message-schemas-for-insert-update-delete-and-select-operations-on-tables-and-views"></a>Esquemas de mensaje para insertar, actualizar, eliminar y seleccione las operaciones en tablas y vistas
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] superficies de Insert, Update, Delete y las operaciones Select para cada tabla y la vista en la base de datos de SQL Server. Estas operaciones realizan la instrucción SQL correspondiente calificada por una cláusula WHERE. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] usa fuertemente tipada de registros y conjuntos de registros en estas operaciones.  
  
## <a name="message-structure-for-table-operations"></a>Estructura de los mensajes para las operaciones de tabla  
 En la tabla siguiente se muestra la estructura del mensaje XML para las operaciones de tabla básico expuestas por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en SQL Server las tablas de base de datos. La tabla de destino para una operación se especifica en la acción de mensaje y también aparece en el espacio de nombres de destino.  
  
|Operación|Mensaje XML|Description|Ejecutada el adaptador de SQL|  
|---------------|-----------------|-----------------|---------------------------------|  
|Insert|`<Insert xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <[TABLE_NAME]>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </Rows> </Insert>`|Inserta el conjunto de registros proporcionado de datos fuertemente tipados en la tabla de destino.|`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …) VALUES (value1, value2, …);`|  
|Insertar la respuesta|`<InsertResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <InsertResult>     <long>[Value]</long>   </InsertResult> </InsertResponse>`|El mensaje de respuesta Insertar contiene una matriz de tipo de datos Long. La matriz almacena los valores de identidad de las filas insertadas, si lo hay. Si no hay ninguna columna de identidad en una tabla, el valor devuelto es NULL.|--|  
|Select|Seleccionar todos los registros:<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>*</COLUMNS>   <Query></Query> </Select>`<br /><br /> Seleccionar columnas específicas en un conjunto de registros:<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>[COLUMN_list]</COLUMNS>   <Query>where [WHERE_clause]</Query> </Select>`<br /><br /> Actualizar registros como parte de la operación Select:<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>[COLUMN_list]</Columns>   <Query>where [WHERE_clause];UPDATE [TABLE_NAME] SET [FIELD1_NAME] = [value1] where [WHERE_clause]</Query> </Select>`|Se realiza una consulta SELECT en la tabla de destino utilizando la cláusula WHERE especificada en el elemento. El conjunto de resultados contiene las columnas en la lista separada por comas de nombres de columna especificados en la \<columnas\> elemento.<br /><br /> Es obligatorio para proporcionar el valor en el \<columnas\> elemento. Si todas las columnas tienen que recuperarse de una tabla o vista, * debe especificarse en el \<columnas\> elemento. Si las columnas concretas tienen que recuperarse, los nombres de columna deben separados por comas y especificados en el mismo orden, tal y como se definen en la tabla o vista.<br /><br /> Es obligatorio incluir la cláusula WHERE en la instrucción SELECT. Si no desea especificar una cláusula WHERE, puede que en eliminar el \<consulta\> elemento o déjela en blanco.<br /><br /> Puede actualizar los registros mediante la operación de selección. Una instrucción UPDATE se coloca en el \<consulta\> elemento de la solicitud seleccione XML, separada de la cláusula WHERE con un punto y coma. Tenga en cuenta que la instrucción UPDATE realiza la operación not en el conjunto de resultados de la instrucción SELECT.|Seleccionar todos los registros:<br /><br /> `SELECT * FROM [TABLE_NAME] WHERE [WHERE_clause];`<br /><br /> Seleccionar columnas específicas en un conjunto de registros:<br /><br /> `SELECT [COLUMN_list] FROM [TABLE_NAME] WHERE [WHERE_clause];`<br /><br /> Actualizar registros como parte de la operación Select:<br /><br /> `SELECT [COLUMN_list] FROM [TABLE_NAME] WHERE [WHERE_clause]; UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1 [WHERE_clause];`|  
|Seleccionar respuesta|`<SelectResponse  xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <SelectResult>     <[TABLE_NAME]>       <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>       <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </SelectResult> <SelectResponse>`|Conjunto de resultados fuertemente tipado generado por la consulta SELECT.|--|  
|Update|`<SelectResponse  xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <SelectResult>     <[TABLE_NAME]>       <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>       <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </SelectResult> </SelectResponse>`<br /><br /> `<Update xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <RowPair>       <After>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>         …       </After>       <Before>         <[FIELD1_NAME]>[value3]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value4]</[FIELD2_NAME]>         …       </Before>     </RowPair>   </Rows> </Update>`|Usar una matriz de pares de registros como entrada. Cada par de registros es una colección de dos registros fuertemente tipado:<br /><br /> Debe registrar (en el `<After>` elemento) corresponde a los nuevos valores que deben actualizarse.<br /><br /> Segundo registro (en la `<Before>`) corresponde a los valores anteriores de las filas.|`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE [FIELD1_NAME] = value3, [FIELD2_NAME] = value4, …;`|  
|Respuesta de actualización|`<UpdateResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <UpdateResult>[rows updated]</UpdateResult> </UpdateResponse>`|Se devuelve el número de filas actualizadas en el **UpdateResult** elemento.|--|  
|Delete|`<Delete xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <[TABLE_NAME]>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </Rows> </Delete>`|--|`DELETE FROM [TABLE_NAME] WHERE [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, …;`|  
|Respuesta de eliminación|`<DeleteResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <DeleteResult>[rows deleted]</DeleteResult> </DeleteResponse>`|Se devuelve el número de filas eliminadas en el **DeleteResult** elemento.|--|  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://schemas.microsoft.com/Sql/2008/05.  
  
 [Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.  
  
 [NombreTabla] = nombre de la tabla; Por ejemplo, el empleado.  
  
 [FIELD1_NAME] = nombre de campo de la tabla; Por ejemplo, el nombre.  
  
 [COLUMN_list] = lista separada por comas de las columnas; Por ejemplo, nombre, edad, designación.  
  
 [SELECT_query] = la instrucción SELECT de SQL A especificada en el elemento de consulta de una operación de inserción masiva; Por ejemplo, "Seleccione * from MyTable"  
  
 [WHERE_clause] = WHERE_clause para la instrucción SELECT utilizada por la operación; Por ejemplo, el Id. > 10.  
  
> [!IMPORTANT]
>  La estructura del mensaje para las operaciones básicas de la tabla en las vistas es igual que en las tablas salvo que la vista reemplaza la tabla: `Insert xmlns="[VERSION]/ViewOp/[SCHEMA]/[VIEW_NAME]"`.  
  
## <a name="message-actions-for-basic-table-operations"></a>Acciones de mensaje para las operaciones de tabla básico  
 La siguiente tabla muestra las acciones de mensaje utilizados por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para las operaciones básicas de la tabla en tablas. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] usa el nombre de tabla especificado en la acción de mensaje para determinar la tabla de destino de la operación.  
  
|Operación|Acción de mensaje|Ejemplo|  
|---------------|--------------------|-------------|  
|Insert|TableOp/Insert/[SCHEMA]/[TABLE_NAME]|TableOp/Insert/dbo/Employee|  
|Insertar la respuesta|TableOp/Insert/[SCHEMA]/[TABLE_NAME]/response|TableOp/Insert/dbo/Employee/response|  
|Select|TableOp/Select/[SCHEMA]/[TABLE_NAME]|TableOp/seleccione/dbo/Employee|  
|Seleccionar respuesta|TableOp/Select/[SCHEMA]/[TABLE_NAME]/response|TableOp/seleccione/dbo/empleado/respuesta|  
|Update|TableOp/Update/[SCHEMA]/[TABLE_NAME]|TableOp/Update/dbo/Employee|  
|Respuesta de actualización|TableOp/Update/[SCHEMA]/[TABLE_NAME]/response|TableOp/Update/dbo/Employee/response|  
|Delete|TableOp/Delete/[SCHEMA]/[TABLE_NAME]|TableOp/Delete/dbo/Employee|  
|Respuesta de eliminación|TableOp/Delete/[SCHEMA]/[TABLE_NAME]/response|TableOp/Delete/dbo/Employee/response|  
  
 [Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.  
  
 [NombreTabla] = nombre de la tabla; Por ejemplo, el empleado.  
  
> [!IMPORTANT]
>  La acción de mensaje para una operación en una vista es el mismo que para una tabla salvo que "ViewOp" reemplaza "TableOp"; Por ejemplo, `ViewOp``/Insert/dbo/Employee_View`.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)