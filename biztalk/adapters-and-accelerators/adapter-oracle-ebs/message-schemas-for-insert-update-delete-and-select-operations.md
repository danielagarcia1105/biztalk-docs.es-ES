---
title: Esquemas de mensajes para Insert, Update, Delete y seleccione operaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b8de271-67db-4279-8f95-0b4dd92fa3c4
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15bb515eee9a052852952f0ec245f8c954953a9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-insert-update-delete-and-select-operations"></a>Esquemas de mensaje para insertar, actualizar, eliminar y seleccionar operaciones
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]superficies básicas Insert, Update, Delete y las operaciones Select para cada tabla de interfaz en Oracle E-Business Suite y todas las tablas de la base de datos subyacente. El adaptador también expone la operación de selección para cada vista de la interfaz en Oracle E-Business Suite y cada vista en la base de datos subyacente. Estas operaciones realizan la instrucción SQL correspondiente calificada por una cláusula WHERE. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa fuertemente tipada de registros y conjuntos de registros en estas operaciones.  
  
## <a name="message-structure-for-basic-operations"></a>Estructura de los mensajes para operaciones básicas  
 En la tabla siguiente se muestra la estructura del mensaje XML para las operaciones básicas expuestos por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] en tablas de la interfaz de Oracle E-Business Suite y vistas de interfaz y en las vistas y tablas de base de datos subyacente. El objeto de destino para una operación se especifica en la acción de mensaje y también aparece en el espacio de nombres de destino.  
  
> [!NOTE]
>  Ver una descripción de atributo después de la tabla.  
  
|Operación|Mensaje XML|Description|Ejecutada el adaptador de SQL|  
|---------------|-----------------|-----------------|---------------------------------|  
|Insert|`<Insert xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <RECORDSET>     <InsertRecord>       <[FIELD1_NAME] InlineValue="value">[value1]</[FIELD1_NAME]>       <[FIELD2_NAME] InlineValue="value">[value2]</[FIELD2_NAME]>       …     </InsertRecord>   </RECORDSET> </Insert>`|El valor de la **InlineValue** atributo, si se especifica, invalida el valor de un elemento.|`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …) VALUES (value1, value2, …);`|  
|Insertar la respuesta|`<InsertResponse xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <InsertResult>[rows inserted]</InsertResult> </InsertResponse>`|Se devuelve el número de filas insertadas en la **InsertResult** elemento.|--|  
|Select|`<Select xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   <FILTER>WHERE_clause</FILTER> </Select>`|Se realiza una consulta SELECT en la tabla de destino utilizando la cláusula WHERE especificada en el elemento de filtro. El conjunto de resultados contiene las columnas en la lista separada por comas de nombres de columna especificados en la **COLUMN_NAMES** elemento.<br /><br /> **Importante:** es la única operación que se aplica para las vistas de base de datos y vistas de interfaz.|`SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`|  
|Seleccionar respuesta|`<SelectResponse  xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <SelectResult>     <SelectRecord>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </SelectRecord>   </SelectResult> </SelectResponse>`|El conjunto de resultados generado por la consulta SELECT.|--|  
|Update|`<Update xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <RECORDSET>     <[FIELD1_NAME]>value1</[FIELD1_NAME]>     <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …   </RECORDSET>   <FILTER>WHERE_clause</FILTER> </Update>`|Filas que coinciden con where cláusula especificada en el **filtro** elemento se actualizan con los valores especificados en la **conjunto de registros**. Solo las columnas que se especifican en el **RECORDSET** elemento se actualiza en cada fila coincidente.|`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`|  
|Respuesta de actualización|`<UpdateResponse xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <UpdateResult>[rows inserted]</UpdateResult> </UpdateResponse>`|Se devuelve el número de filas actualizadas en el **UpdateResult** elemento.|--|  
|DELETE|`<Delete xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <FILTER>WHERE_clause</FILTER> </Delete>`|Filas que coinciden con la cláusula WHERE especificada por el **filtro** se elimina el elemento.|`DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`|  
|Respuesta de eliminación|`<DeleteResponse xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <DeleteResult>[rows deleted]</DeleteResult> </DeleteResponse>`|Se devuelve el número de filas eliminadas en el **DeleteResult** elemento.|--|  
  
 Descripciones de atributos:  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://schemas.microsoft.com/OracleEBS/2008/05.  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [APP_NAME] = nombre corto de aplicación.  
  
 [INTERFACETABLE_NAME] = nombre de la tabla de interfaz.  
  
 [FIELD1_NAME] = nombre del campo de tabla.  
  
 [COLUMN_list] = lista de columnas separadas por comas.  
  
 [WHERE_clause] = WHERE_clause para la instrucción SELECT utilizada por la operación; Por ejemplo, el Id. > 10.  
  
> [!IMPORTANT]
>  La estructura del mensaje para las operaciones básicas en vistas de interfaz, tablas de base de datos y vistas de base de datos es el mismo que en las tablas de interfaz, pero el espacio de nombres para la operación especifica una vista de la interfaz, tabla de base de datos, o vista de base de datos en lugar de una interfaz tabla.  
  
## <a name="message-actions-for-basic-operations"></a>Acciones de mensaje para las operaciones básicas  
 La siguiente tabla muestra las acciones de mensaje que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] utiliza para las operaciones básicas en las tablas de interfaz y la vista de la interfaz en Oracle E-Business Suite y las tablas y vistas en la base de datos subyacente. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa la tabla de interfaz, vista de la interfaz, tabla de base de datos o vista de base de datos especificada en la acción de mensaje para determinar el destino de la operación.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|Operación|Acción de mensaje|Ejemplo|  
|---------------|--------------------|-------------|  
|Insert|**Aplicaciones**: InterfaceTables/Insert / [SHORT_NAME] / [APP_NAME] / [NombreTabla]<br /><br /> **Base de datos**: tablas/Insert / [esquema] / [NombreTabla]|**Aplicaciones**: InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **Base de datos**: tablas/Insert/GL/GL_ALLOC_HISTORY|  
|Insertar la respuesta|**Aplicaciones**: InterfaceTables/Insert / [SHORT_NAME] / [APP_NAME] / [NombreTabla] / respuesta<br /><br /> **Base de datos**: tablas/Insert / [esquema] / [NombreTabla] / respuesta|**Aplicaciones**: InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY/respuesta<br /><br /> **Base de datos**: tablas/Insert/GL/GL_ALLOC_HISTORY/respuesta|  
|Select|**Aplicaciones**: InterfaceTables o seleccionar / [SHORT_NAME] / [APP_NAME] / [NombreTabla]<br /><br /> **Base de datos**: tablas o seleccionar / [esquema] / [NombreTabla]|**Aplicaciones**: InterfaceTables/seleccione/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **Base de datos**: tablas y seleccione/GL/GL_ALLOC_HISTORY|  
|Seleccionar respuesta|**Aplicaciones**: InterfaceTables o seleccionar / [SHORT_NAME] / [APP_NAME] / [NombreTabla] / respuesta<br /><br /> **Base de datos**: tablas o seleccionar / [esquema] / [NombreTabla] / respuesta|**Aplicaciones**: Select/InterfaceTables/SQLGL/GL_ALLOC_HISTORY/GL/respuesta<br /><br /> **Base de datos**: tablas y seleccione/GL/GL_ALLOC_HISTORY/respuesta|  
|Update|**Aplicaciones**: InterfaceTables/actualizar / [SHORT_NAME] / [APP_NAME] / [NombreTabla]<br /><br /> **Base de datos**: tablas/actualizar / [esquema] / [NombreTabla]|**Aplicaciones**: InterfaceTables/actualización/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **Base de datos**: tablas/actualización/GL/GL_ALLOC_HISTORY|  
|Respuesta de actualización|**Aplicaciones**: InterfaceTables/actualizar / [SHORT_NAME] / [APP_NAME] / [NombreTabla] / respuesta<br /><br /> **Base de datos**: tablas/actualizar / [esquema] / [NombreTabla] / respuesta|**Aplicaciones**: InterfaceTables/actualización/SQLGL/GL/GL_ALLOC_HISTORY/respuesta<br /><br /> **Base de datos**: tablas/actualización/GL/GL_ALLOC_HISTORY/respuesta|  
|DELETE|**Aplicaciones**: InterfaceTables/Delete / [SHORT_NAME] / [APP_NAME] / [NombreTabla]<br /><br /> **Base de datos**: tablas/Delete / [esquema] / [NombreTabla]|**Aplicaciones**: InterfaceTables/Delete/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **Base de datos**: tablas/Delete/GL/GL_ALLOC_HISTORY|  
|Respuesta de eliminación|**Aplicaciones**: InterfaceTables/Delete / [SHORT_NAME] / [APP_NAME] / [NombreTabla] / respuesta<br /><br /> **Base de datos**: tablas/Delete / [esquema] / [NombreTabla] / respuesta|**Aplicaciones**: InterfaceTables/Delete/SQLGL/GL/GL_ALLOC_HISTORY/respuesta<br /><br /> **Base de datos**: tablas/Delete/GL/GL_ALLOC_HISTORY/respuesta|  
  
 Descripciones de entidad:  
  
-   [Esquema] - artefactos de la colección de Oracle (por ejemplo, GL).  
  
-   [NombreTabla] - nombre de la tabla (por ejemplo, GL_ALLOC_HISTORY).  
  
> [!IMPORTANT]
>  La acción de mensaje para la operación de selección en una vista de la interfaz es el mismo que para la tabla de interfaz, salvo que "InterfaceViews" reemplaza "InterfaceTables." De forma similar, la acción de mensaje para la operación de selección en una vista de base de datos es el mismo que para la tabla de base de datos, excepto en que "Vistas" reemplaza "Tablas".  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)