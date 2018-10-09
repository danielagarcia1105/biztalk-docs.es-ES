---
title: Identificadores de nodo de metadatos para el adaptador de Oracle DB en BizTalk Adapter Pack | Microsoft Docs
description: Metadatos, búsqueda, tipos de nodos de recuperación y los identificadores usados en los componentes de Oracle que se exponen en el adaptador de Oracle DB - módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 523c7611-b21f-4598-ac77-ba71075db073
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a131cc8e70311f6f57154b90e98ea1067ec5dc02
ms.sourcegitcommit: 51ce182c5b71d3999a3920dd884bc9ec8334a899
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "36969661"
---
# <a name="node-types-and-ids-for-the-oracle-database-adapter"></a>Tipos de nodo e identificadores para el adaptador de base de datos de Oracle

## <a name="metadata-node-types-and-ids"></a>Identificadores y tipos de nodo de metadatos 
El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies de Oracle de base de datos los artefactos de forma jerárquica. La tabla siguiente enumeran los tipos de nodo e identificadores de nodo para los artefactos de base de datos de Oracle que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies. El identificador de nodo es la ruta de acceso absoluta del nodo que se usa en el **IMetadataRetrievalContractBrowse**, **búsqueda**, y **GetMetadata** métodos.  


| Nombre de presentación de artefacto | Tipo de nodo |                           Id. de nodo                           |                                        Ejemplo                                         |                                                                                                     Descripción                                                                                                     |
|-----------------------|-----------|-------------------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          --           | CATEGORÍA  |                              /                              |                                           /                                            | [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] nodo raíz. Devuelve todos los nodos de primer nivel; Esto incluye todos los nodos de esquema, el nodo de operación POLLINGSTMT y el nodo de operación SQLEXECUTE |
|      SQLEXECUTE       | OPERATION |                    [VERSIÓN] / SQLEXECUTE                     |                http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE                |                                                                        Nodo de operación SQLEXECUTE. Devuelve el WSDL para la operación SQLEXECUTE.                                                                        |
|      POLLINGSTMT      | OPERATION |                    [VERSIÓN] / POLLINGSTMT                    |               http://Microsoft.LobServices  OracleDB/2007/03/POLLINGSTMT               |                                                                       Nodo de operación POLLINGSTMT. Devuelve el WSDL para la operación POLLINGSTMT.                                                                       |
|      [DB_SCHEMA]      | CATEGORÍA  |                    [VERSIÓN] / [DB_SCHEMA]                    |                  http://Microsoft.LobServices.OracleDB/2007/03/SCOTT                   |                                                Nodo de esquema. Devuelve los nodos de categoría general (tabla, vista, procedimiento, función y paquete) para el esquema especificado.                                                |
|         Table         | CATEGORÍA  |                 [Versión] / [DB_SCHEMA] / Table                 |               http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table                |                                                                        Nodo de tablas del esquema. Devuelve todos los nodos de tabla para el esquema especificado.                                                                        |
|      [DB_TABLE]       | CATEGORÍA  |           [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE]            |             http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP              |      Nodo de la tabla. Devuelve todos los nodos de operación (Insert, Select, Update, Delete, ReadLOB y UpdateLOB) de la tabla especificada. (ReadLOB y UpdateLOB son solo devuelve las tablas que contienen una columna LOB.)      |
|        Insert         | OPERATION |        [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / inserción        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert          |                                                             Nodo de operación de inserción de tabla. Devuelve el WSDL para la operación de inserción de la tabla especificada.                                                             |
|        Select         | OPERATION |        [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / seleccione        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select          |                                                             Nodo de operación de selección de tabla. Devuelve el WSDL para la operación de selección de la tabla especificada.                                                             |
|        Update         | OPERATION |        [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / actualizar        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update          |                                                             Nodo de operación de actualización de la tabla. Devuelve el WSDL para la operación de actualización de la tabla especificada.                                                             |
|        DELETE         | OPERATION |        [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / Delete        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete          |                                                             Nodo de operación de eliminación de tabla. Devuelve el WSDL para la operación de eliminación de la tabla especificada.                                                             |
|        ReadLOB        | OPERATION |       [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / ReadLOB        |         http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/ReadLOB          |                                  Nodo de operación ReadLOB de la tabla. Devuelve el WSDL de la operación ReadLOB para la tabla especificada. (Solo aparece si la tabla contiene una columna LOB.)                                  |
|       UpdateLOB       | OPERATION |      [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / UpdateLOB       |        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/UpdateLOB         |                                Nodo de operación UpdateLOB de la tabla. Devuelve el WSDL de la operación UpdateLOB para la tabla especificada. (Solo aparece si la tabla contiene una columna LOB.)                                |
|         Ver          | CATEGORÍA  |                 [Versión] / [DB_SCHEMA] / View                  |                http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View                |                                                                         Nodo de las vistas de esquema. Devuelve todos los nodos de la vista para el esquema especificado.                                                                         |
|       [DB_VIEW]       | CATEGORÍA  |            [Versión] / [DB_SCHEMA] /View/ [DB_VIEW]             |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW           |       Nodo de la vista. Devuelve todos los nodos de operación (Insert, Select, Update, Delete, ReadLOB y UpdateLOB) para la vista especificada. (ReadLOB y UpdateLOB son sólo devuelve para las vistas que contienen una columna LOB.)        |
|        Insert         | OPERATION |         [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / inserción         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Insert       |                                                              Ver el nodo de operación de inserción. Devuelve el WSDL para la operación de inserción para la vista especificada.                                                              |
|        Select         | OPERATION |         [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / seleccione         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Select       |                                                              Nodo de operación de selección de vista. Devuelve el WSDL para la operación de selección de la vista especificada.                                                              |
|        Update         | OPERATION |         [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / actualizar         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Update       |                                                              Nodo de operación de actualización de la vista. Devuelve el WSDL para la operación de actualización de la vista especificada.                                                              |
|        DELETE         | OPERATION |         [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / Delete         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Delete       |                                                              Nodo de operación de eliminación de vista. Devuelve el WSDL para la operación de eliminación de la vista especificada.                                                              |
|        ReadLOB        | OPERATION |        [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / ReadLOB         |      http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/ReadLOB       |                                   Ver el nodo de operación ReadLOB. Devuelve el WSDL de la operación ReadLOB para la vista especificada. (Solo aparece si la vista contiene una columna LOB.)                                    |
|       UpdateLOB       | OPERATION |       [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / UpdateLOB        |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/UpdateLOB      |                                  Nodo de operación de actualización de la vista. Devuelve el WSDL de la operación UpdateLOB para la tabla especificada. (Solo aparece si la vista contiene una columna LOB.)                                   |
|       Procedimiento       | CATEGORÍA  |               [Versión] / [DB_SCHEMA] / procedimiento               |             http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure              |                                                                      Nodo de procedimientos de esquema. Devuelve todos los procedimientos para el esquema especificado.                                                                       |
|    [DB_PROCEDURE]     | OPERATION |       [Versión] / [DB_SCHEMA] /Procedure/ [DB_PROCEDURE]        |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_GENREPORT       |                                                                            Nodo de procedimiento. Devuelve el WSDL para el procedimiento especificado.                                                                            |
|       Función        | CATEGORÍA  |               [Versión] / [DB_SCHEMA] de función                |              http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function              |                                                                       Nodo de las funciones de esquema. Devuelve todas las funciones para el esquema especificado.                                                                        |
|     [DB_FUNCTION]     | OPERATION |        [Versión] / [DB_SCHEMA] /Function/ [DB_FUNCTION]         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETUSERID        |                                                                             Nodo de función. Devuelve el WSDL para la función especificada.                                                                             |
|        Paquete        | CATEGORÍA  |                [Versión] / [DB_SCHEMA] / paquete                |              http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package               |                                                                        Nodo de paquetes del esquema. Devuelve todos los paquetes para el esquema especificado.                                                                         |
|     [DB_PACKAGE]      | CATEGORÍA  |         [Versión] / [DB_SCHEMA] /Package/ [DB_PACKAGE]          |        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG         |                                                                    Nodo de paquete. Devuelve todos los procedimientos y funciones para el paquete especificado.                                                                    |
|   [PACK_PROCEDURE]    | OPERATION | [Versión] / [DB_SCHEMA] /Package/ [DB_PACKAGE] / [PACK_PROCEDURE] |  http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT   |                                                                    Nodo de procedimiento del paquete. Devuelve el WSDL para el procedimiento de paquete especificado.                                                                    |
|    [PACK_FUNCTION]    | OPERATION | [Versión] / [DB_SCHEMA] /Package/ [DB_PACKAGE] / [PACK_FUNCTION]  | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT |                                                                     Nodo de función del paquete. Devuelve el WSDL para la función del paquete especificado.                                                                     |

 [Versión] = la cadena de versión; Por ejemplo, http://Microsoft.LobServices.OracleDB/2007/03.  

 [DB_SCHEMA] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  

 [DB_TABLE] = el nombre de una tabla de Oracle Por ejemplo, EMP.  

 [DB_VIEW] = el nombre de una vista de Oracle; Por ejemplo, SALES_VIEW.  

 [DB_PROCEDURE] = el nombre de un procedimiento de Oracle; Por ejemplo, SP_GENREPORT.  

 [DB_FUNCTION] = el nombre de una función de Oracle; Por ejemplo, FN_GETUSERID.  

 [DB_PACKAGE] = el nombre de un paquete de Oracle; Por ejemplo, ACCOUNT_PKG.  

 [PACK_PROCEDURE] = el nombre de un procedimiento de paquete. Por ejemplo, GET_ACCOUNT.  

 [PACK_FUNCTION] = el nombre de una función del paquete; Por ejemplo, CREATE_ACCOUNT.  

## <a name="metadata-search-and-node-ids"></a>Búsqueda de metadatos y los identificadores de nodo  
 Búsqueda de metadatos es una potente característica que el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] superficies como parte de su **MetadataRetrievalContract** interfaz. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa esta característica para admitir la búsqueda en los siguientes artefactos de Oracle. El ámbito de búsqueda de metadatos está restringido al nivel inmediatamente debajo del nodo en el que se realiza la operación de búsqueda. Por ejemplo, para buscar una función, se debe estar buscando en \\\Functions [esquema]. No se admite una búsqueda recursiva.  

|Artefacto|Id. de nodo|Tipo de nodo devuelto|Descripción|  
|--------------|-------------|------------------------|-----------------|  
|[DB_SCHEMA]|/ (es decir, el nodo raíz)|CATEGORÍA|Devolver todos los nodos de esquema que coincide con la expresión de búsqueda.|  
|[DB_TABLE]|/ [Versión] / [DB_SCHEMA] / Table|CATEGORÍA|Devolver todos los nodos de la tabla en el esquema especificado que coinciden con la expresión de búsqueda.|  
|[DB_VIEW]|/ [Versión] / [DB_SCHEMA] / View|CATEGORÍA|Devolver todos los nodos de vista en el esquema especificado que coinciden con la expresión de búsqueda.|  
|[DB_PROCEDURE]|/ [Versión] / [DB_SCHEMA] / procedimiento|OPERATION|Devolver todos los nodos de procedimiento en el esquema especificado que coinciden con la expresión de búsqueda.|  
|[DB_FUNCTION]|/ [Versión] / [DB_SCHEMA] de función|OPERATION|Devolver todos los nodos de la función en el esquema especificado que coinciden con la expresión de búsqueda.|  
|[DB_PACKAGE]|/ [Versión] / [DB_SCHEMA] / paquete|CATEGORÍA|Devolver todos los nodos de paquete (categoría) en el esquema especificado que coinciden con la expresión de búsqueda.|  
|[PACK_PROCEDURE] y [PACK_FUNCTION]|/ [Versión] / [DB_SCHEMA] /Package/ [DB_PACKAGE]|OPERATION|Devolver todos los nodos de función y procedimiento (operación) en el paquete especificado que coinciden con la expresión de búsqueda.|  

 [Versión] = la cadena de versión; Por ejemplo, http://Microsoft.LobServices/2007/03.  

 [DB_SCHEMA] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  

 [DB_TABLE] = el nombre de una tabla de Oracle Por ejemplo, EMP.  

 [DB_VIEW] = el nombre de una vista de Oracle; Por ejemplo, SALES_VIEW.  

 [DB_PROCEDURE] = el nombre de un procedimiento de Oracle; Por ejemplo, SP_GENREPORT.  

 [DB_FUNCTION] = el nombre de una función de Oracle; Por ejemplo, FN_GETUSERID.  

 [DB_PACKAGE] = el nombre de un paquete de Oracle; Por ejemplo, ACCOUNT_PKG.  

 [PACK_PROCEDURE] = el nombre de un procedimiento de paquete. Por ejemplo, GET_ACCOUNT.  

 [PACK_FUNCTION] = el nombre de una función del paquete; Por ejemplo, CREATE_ACCOUNT.  

 Puede especificar las expresiones de búsqueda que son compatibles con cualquier expresión válida que puede usarse para el operador LIKE de Oracle. Por ejemplo, para realizar una búsqueda en las tablas contenidas en un esquema, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ejecuta la instrucción SQL siguiente: `SELECT TABLE_NAME FROM ALL_TABLES WHERE OWNER = '[OWNER_NAME]' AND TABLE_NAME LIKE ‘[SEARCH_STR]’`.  

 La siguiente tabla se muestran caracteres especial que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite en las expresiones de búsqueda.  

|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|% (porcentaje)|Coincide con cero o más caracteres; Por ejemplo, "%" coincide con "A", "AB", "ABC" y así sucesivamente.|  
|_ (carácter de subrayado)|Coincide exactamente 1 carácter; Por ejemplo, "A_" coincide con "AB", "CA", "AD", y así sucesivamente.|  
|\ (escape)|Convierte el significado especial de '%' y '_'; Por ejemplo, "un\\_B" coincide con "A_B".|  

## <a name="metadata-retrieval-and-node-ids"></a>Recuperación de metadatos y los identificadores de nodo  
 En la tabla siguiente se resume las características de los metadatos devueltas por [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  

|Artefacto|Características de los metadatos|  
|--------------|------------------------------|  
|Tabla o vista|<ul><li>Nombre de la tabla.</li><li>Nombres de campo de tabla.</li><li>Tipos de datos del campo de tabla se asignan a tipos WSDL simples o complejos.</li><li>Longitud de campo de tabla se asigna a la faceta maxLength.</li><li>Restricción de clave principal de campo de tabla se asigna a la faceta minOccurs = 1.</li><li>Restricción de tabla campo NULL se asigna a la faceta isNillable = true.</li><li>Operaciones de tabla<br /><br /> <ul><li>INSERT</li><li>SELECT</li><li>UPDATE</li><li>Delete</li><li>READLOB (si la tabla contiene el campo de tipo LOB de Oracle)</li><li>UPDATELOB (si la tabla contiene el campo de tipo LOB de Oracle)</li></ul></li></ul>|  
|Procedimiento o función|Nombre procedimiento o función se asigna al nombre de la operación.<br />Los nombres de parámetro procedimiento o función.<br />Tipos de datos de parámetro procedimiento o función se asignan a tipos WSDL.<br />-Dirección del parámetro procedimiento o función se asigna a la dirección del parámetro WSDL.<br />-Procedimiento parámetro o una función datos longitud tipo de parámetro se asigna a la faceta maxLength.<br />-Orden de los parámetros procedimiento o función se asigna a la secuencia de elementos.<br />-Función devuelve el tipo de datos se asigna al tipo WSDL.<br />-Función devuelve la longitud del tipo de datos se asigna a la faceta maxLength.|  
|Paquete procedimiento o función.|-Nombre del paquete.<br />-Otras características de procedimiento y la función como se muestra anteriormente.|  

 Para obtener información detallada sobre el formato de los metadatos que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone para artefactos específicos y las operaciones en la base de datos de Oracle, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).  

## <a name="see-also"></a>Vea también  
[Obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](get-metadata-for-oracle-database-operations-in-visual-studio.md)