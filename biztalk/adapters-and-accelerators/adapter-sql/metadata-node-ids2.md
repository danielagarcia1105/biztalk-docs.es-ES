---
title: Identificadores de nodo de metadatos para el adaptador SQL en BizTalk Adapter Pack | Microsoft Docs
description: Metadatos, búsqueda, tipos de nodos de recuperación y los identificadores usados en los componentes SQL que se exponen en el adaptador de SQL Server - módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8601a328-5380-4577-a121-c926e0fd3140
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80dd7d58f220f7c7fdf8c70851373311999927f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022626"
---
# <a name="node-types-and-ids-for-the-sql-server-adapter"></a>Tipos de nodo e identificadores para el adaptador de SQL Server

## <a name="metadata-node-ids"></a>Identificadores de nodo de metadatos
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] superficies de SQL Server de base de datos los artefactos de forma jerárquica. La tabla siguiente enumeran los tipos de nodo e identificadores de nodo para los artefactos de base de datos de SQL Server que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] superficies. El identificador de nodo es la ruta de acceso absoluta del nodo que se usa en el **IMetadataRetrievalContractBrowse**, **búsqueda**, y **GetMetadata** métodos.  


| Nombre de presentación de artefacto  |     Tipo de nodo      |                        Id. de nodo                         |                    Ejemplo                     |                                                                                                                                                    Descripción                                                                                                                                                    |
|------------------------|--------------------|--------------------------------------------------------|------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           --           |      CATEGORÍA      |                           /                            |                       /                        | [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] nodo raíz. Devuelve todos los nodos de primer nivel; Esto incluye los nodos de operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar y todos los nodos de esquema para las operaciones de salida y el nodo de operación de sondeo para la operación de entrada. |
|    ExecuteNonQuery     | OPERACIÓN DE SALIDA |               GenericOp/ExecuteNonQuery                |           GenericOp/ExecuteNonQuery            |                                                                                                                  Nodo de operación ExecuteNonQuery. Devuelve el WSDL para la operación ExecuteNonQuery.                                                                                                                  |
|     ExecuteReader      | OPERACIÓN DE SALIDA |                GenericOp/ExecuteReader                 |            GenericOp/ExecuteReader             |                                                                                                                    Nodo de operación ExecuteReader. Devuelve el WSDL para la operación ExecuteReader.                                                                                                                    |
|     ExecuteScalar      | OPERACIÓN DE SALIDA |                GenericOp/ExecuteScalar                 |            GenericOp/ExecuteScalar             |                                                                                                                    Nodo de operación ExecuteScalar. Devuelve el WSDL para la operación ExecuteScalar.                                                                                                                    |
|        Sondeo         | OPERACIÓN DE ENTRADA  |                        Sondeo                         |                    Sondeo                     |                                                                                                                          Nodo de operación de sondeo. Devuelve el WSDL para la operación de sondeo.                                                                                                                          |
|      Notification      | OPERACIÓN DE ENTRADA  |                      Notification                      |                  Notification                  |                                                                                                                     Nodo de operación de notificación. Devuelve el WSDL para la operación de notificación.                                                                                                                     |
|       Procedimientos       |      CATEGORÍA      |                      Procedimientos /                       |                  Procedimientos /                   |                                                                                                                     Nodo de procedimientos de esquema. Devuelve todos los procedimientos para el esquema especificado.                                                                                                                      |
|     [DB_PROCEDURE]     | OPERACIÓN DE SALIDA |         Procedimiento / [DB_SCHEMA] / [Procedure_Name]         |         Procedimiento/dbo/ADD_EMP_DETAILS          |                                                                                                                           Nodo de procedimiento. Devuelve el WSDL para el procedimiento especificado.                                                                                                                           |
|         Tablas         |      CATEGORÍA      |                        Tablas /                         |                    Tablas /                     |                                                                                                                       Nodo de tablas del esquema. Devuelve todos los nodos de tabla para el esquema especificado.                                                                                                                       |
|       [DB_TABLE]       |      CATEGORÍA      |                           -                            |                       -                        |                   Nodo de la tabla. Devuelve todos los nodos de operación (Insert, Select, Update, Delete y Set) para la tabla especificada.<br /><br /> Solo se devuelve la operación de establecimiento de las tablas que contienen columnas con cualquiera de los siguientes tipos de datos: varchar (max), nvarchar (max) o varbinary (max).                   |
|         Insert         | OPERACIÓN DE SALIDA |         TableOp/Insert / [DB_SCHEMA] / [DB_TABLE]          |          TableOp/Insert/dbo/Employee           |                                                                                                            Nodo de operación de inserción de tabla. Devuelve el WSDL para la operación de inserción de la tabla especificada.                                                                                                            |
|         Select         | OPERACIÓN DE SALIDA |         TableOp/seleccionar / [DB_SCHEMA] / [DB_TABLE]          |          TableOp/seleccionar/dbo/Employee           |                                                                                                            Nodo de operación de selección de tabla. Devuelve el WSDL para la operación de selección de la tabla especificada.                                                                                                            |
|         Update         | OPERACIÓN DE SALIDA |         TableOp/actualizar / [DB_SCHEMA] / [DB_TABLE]          |          TableOp/actualización/dbo/Employee           |                                                                                                            Nodo de operación de actualización de la tabla. Devuelve el WSDL para la operación de actualización de la tabla especificada.                                                                                                            |
|         DELETE         | OPERACIÓN DE SALIDA |         TableOp/Delete / [DB_SCHEMA] / [DB_TABLE]          |          TableOp/Delete/dbo/Employee           |                                                                                                            Nodo de operación de eliminación de tabla. Devuelve el WSDL para la operación de eliminación de la tabla especificada.                                                                                                            |
|    Conjunto [nombreColumna]    | OPERACIÓN DE SALIDA | TableOp/WriteText / [DB_SCHEMA] / [DB_TABLE] / [nombreColumna] | TableOp, WriteText, dbo, empleado/Job_Description |                                          Nodo de operación de conjunto de la tabla. Devuelve el WSDL para la operación de establecimiento de la columna especificada en la tabla. (Solo aparece si la tabla contiene columnas con cualquiera de los siguientes tipos: (Max), nvarchar (max) o varbinary.                                           |
|         Vistas          |      CATEGORÍA      |                         Vistas /                         |                     Vistas /                     |                                                                                                                        Nodo de las vistas de esquema. Devuelve todos los nodos de la vista para el esquema especificado.                                                                                                                        |
|       [DB_VIEW]        |      CATEGORÍA      |                           -                            |                       -                        |                                                                                                        Nodo de la vista. Devuelve todos los nodos de operación (Insert, Select, Update y Delete) para la vista especificada.                                                                                                        |
|         Insert         | OPERACIÓN DE SALIDA |          ViewOp/Insert / [DB_SCHEMA] / [DB_VIEW]           |        ViewOp/Insert/dbo/Employee_View         |                                                                                                             Ver el nodo de operación de inserción. Devuelve el WSDL para la operación de inserción para la vista especificada.                                                                                                             |
|         Select         | OPERACIÓN DE SALIDA |          ViewOp/seleccionar / [DB_SCHEMA] / [DB_VIEW]           |        ViewOp/seleccionar/dbo/Employee_View         |                                                                                                             Nodo de operación de selección de vista. Devuelve el WSDL para la operación de selección de la vista especificada.                                                                                                             |
|         Update         | OPERACIÓN DE SALIDA |          ViewOp/actualizar / [DB_SCHEMA] / [DB_VIEW]           |        ViewOp/actualización/dbo/Employee_View         |                                                                                                             Nodo de operación de actualización de la vista. Devuelve el WSDL para la operación de actualización de la vista especificada.                                                                                                             |
|         DELETE         | OPERACIÓN DE SALIDA |          ViewOp/Delete / [DB_SCHEMA] / [DB_VIEW]           |        ViewOp/Delete/dbo/Employee_View         |                                                                                                             Nodo de operación de eliminación de vista. Devuelve el WSDL para la operación de eliminación de la vista especificada.                                                                                                             |
|    Funciones escalares    |      CATEGORÍA      |                    ScalarFunctions /                    |                ScalarFunctions /                |                                                                                                               Nodo de esquema funciones escalares. Devuelve todas las funciones escalares para el esquema especificado.                                                                                                                |
|   [DB_SCLR_FUNCTION]   | OPERACIÓN DE SALIDA |     ScalarFunction / [DB_SCHEMA] / [DB_SCLR_FUNCTION]      |         ScalarFunction/dbo/GET_EMP_ID          |                                                                                                                     Nodo de función escalar. Devuelve el WSDL para la función escalar especificado.                                                                                                                     |
| Las funciones con valores de tabla |      CATEGORÍA      |                    TableFunctions /                     |                TableFunctions /                 |                                                                                                         Nodo de funciones con valores de tabla de esquema. Devuelve todas las funciones con valores de tabla para el esquema especificado.                                                                                                          |
|   [DB_TBL_FUNCTION]    | OPERACIÓN DE SALIDA |      TableFunction / [DB_SCHEMA] / [DB_TBL_FUNCTION]       |         TableFunction/dbo/TVF_EMPLOYEE         |                                                                                                               Nodo de función con valores de tabla. Devuelve el WSDL para la función con valores de tabla especificado.                                                                                                               |

 [DB_SCHEMA] = artefactos de la colección de SQL Server; Por ejemplo, dbo.  

 [DB_TABLE] = el nombre de una tabla de SQL Server; Por ejemplo, el empleado.  

 [DB_VIEW] = el nombre de una vista de SQL Server; Por ejemplo, Employee_View.  

 [DB_PROCEDURE] = el nombre de un procedimiento almacenado de SQL Server; Por ejemplo, ADD_EMP_DETAILS.  

 [DB_SCLR_FUNCTION] = el nombre de una función escalar de SQL Server; Por ejemplo, GET_EMP_ID.  

 [DB_TBL_FUNCTION] = el nombre de una función con valores de tabla de SQL Server; Por ejemplo, TVF_EMPLOYEE.  

## <a name="metadata-search-and-node-ids"></a>Búsqueda de metadatos y los identificadores de nodo  
 Búsqueda de metadatos es una potente característica que el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] superficies como parte de su **MetadataRetrievalContract** interfaz. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] usa esta característica para admitir la búsqueda en los siguientes artefactos de SQL Server. El ámbito de búsqueda de metadatos está restringido al nivel inmediatamente debajo del nodo en el que se realiza la operación de búsqueda. Por ejemplo, para buscar una función escalar, debe ser escalar o búsqueda en función / [esquema]. No se admite una búsqueda recursiva.  

|Artefacto|Id. de nodo|Tipo de nodo devuelto|Descripción|  
|--------------|-------------|------------------------|-----------------|  
|/ (es decir, el nodo raíz)|/|CATEGORÍA|Devolver todos los nodos de esquema que coincide con la expresión de búsqueda.|  
|[DB_PROCEDURE]|/PROCEDURE/ [DB_SCHEMA]|OPERACIÓN DE SALIDA|Devolver todos los nodos de procedimiento en el esquema especificado que coinciden con la expresión de búsqueda.|  
|[DB_TABLE]|/Table/ [DB_SCHEMA]|CATEGORÍA|Devolver todos los nodos de la tabla en el esquema especificado que coinciden con la expresión de búsqueda.|  
|[DB_VIEW]|/View/ [DB_SCHEMA]|CATEGORÍA|Devolver todos los nodos de vista en el esquema especificado que coinciden con la expresión de búsqueda.|  
|[DB_SCLR_FUNCTION]|/ScalarFunction/ [DB_SCHEMA]|OPERACIÓN DE SALIDA|Devolver todos los nodos de la función escalar en el esquema especificado que coinciden con la expresión de búsqueda.|  
|[DB_TBL_FUNCTION]|/TableFunction/ [DB_SCHEMA]|OPERACIÓN DE SALIDA|Devolver todos los nodos de función con valores de tabla en el esquema especificado que coinciden con la expresión de búsqueda.|  

 [DB_SCHEMA] = artefactos de la colección de SQL Server; Por ejemplo, dbo.  

 [DB_TABLE] = el nombre de una tabla de SQL Server; Por ejemplo, el empleado.  

 [DB_VIEW] = el nombre de una vista de SQL Server; Por ejemplo, Employee_View.  

 [DB_PROCEDURE] = el nombre de un procedimiento de SQL Server; Por ejemplo, ADD_EMP_DETAILS.  

 [DB_SCLR_FUNCTION] = el nombre de una función escalar de SQL Server; Por ejemplo, GET_EMP_ID.  

 [DB_TBL_FUNCTION] = el nombre de una función con valores de tabla de SQL Server; Por ejemplo, TVF_EMPLOYEE.  

 Puede especificar las expresiones de búsqueda que son compatibles con cualquier expresión válida que puede usarse para el operador LIKE de SQL Server. Por ejemplo, para realizar una búsqueda en las tablas contenidas en un esquema, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejecuta la instrucción SQL siguiente: `SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE ‘[SEARCH_STR]’`.  

 La siguiente tabla se muestran caracteres especial que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite en las expresiones de búsqueda.  

|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|% (porcentaje)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, "%" coincide con "A", "AB", "ABC" y así sucesivamente.|  
|_ (carácter de subrayado)|Coincide exactamente 1 carácter.<br /><br /> Por ejemplo, "A_" coincide con "AB", "CA", "AD", y así sucesivamente.|  
|[ ]|-El significado especial de _ y % de secuencias de escape.<br />-Especifica un intervalo o conjunto de caracteres que se va a estar presente.<br /><br /> Por ejemplo:<br /><br /> -% [%] coincide con todos los nombres que incluyen un símbolo %.<br />-[a-f] coincide con todos los nombres que tienen caracteres entre la 'a' y 'f'.<br />-[abc] coincide con todos los nombres que tienen caracteres 'a', 'b' y 'c'.|  
|[^]|Especifica un intervalo o conjunto de caracteres que no se esté presente.<br /><br /> Por ejemplo:<br /><br /> -[^ a-f] coincide con todos los nombres que no tienen caracteres entre la 'a' y 'f'.<br />-[^ abc] coincide con todos los nombres que no tienen caracteres 'a', 'b' y 'c'.|  

## <a name="metadata-retrieval-and-node-ids"></a>Recuperación de metadatos y los identificadores de nodo  
 En la tabla siguiente se resume las características de los metadatos devueltas por [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

|Artefacto|Características de los metadatos|  
|--------------|------------------------------|  
|Tabla o vista|<ul><li>Nombre de la tabla.</li><li>Nombres de campo de tabla.</li><li>Tipos de datos del campo de tabla se asignan a tipos WSDL simples o complejos.</li><li>Longitud de campo de tabla se asigna a la faceta maxLength.</li><li>Restricción de clave principal de campo de tabla se asigna a la faceta minOccurs = 1.</li><li>Restricción de tabla campo NULL se asigna a la faceta isNillable = true.</li><li>Operaciones de tabla<br /><br /> <ul><li>INSERT</li><li>SELECT</li><li>UPDATE</li><li>Delete</li><li>ESTABLECER\<nombre de columna\></li></ul></li></ul>|  
|Procedimiento o función|Nombre procedimiento o función se asigna al nombre de la operación.<br />Los nombres de parámetro procedimiento o función.<br />Tipos de datos de parámetro procedimiento o función se asignan a tipos WSDL.<br />-Dirección del parámetro procedimiento o función se asigna a la dirección del parámetro WSDL.<br />-Procedimiento parámetro o una función datos longitud tipo de parámetro se asigna a la faceta maxLength.<br />-Orden de los parámetros procedimiento o función se asigna a la secuencia de elementos.<br />-Función devuelve el tipo de datos se asigna al tipo WSDL.<br />-Función devuelve la longitud del tipo de datos se asigna a la faceta maxLength.|  

 Para obtener información detallada sobre el formato de los metadatos que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone para artefactos específicos y las operaciones en la base de datos de SQL Server, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).  
