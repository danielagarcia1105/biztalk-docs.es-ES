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
ms.openlocfilehash: 53fd454b644cea6c509ec167740bd5e3c2bebb1a
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752541"
---
# <a name="node-types-and-ids-for-the-oracle-database-adapter"></a>Tipos de nodo e identificadores para el adaptador de base de datos de Oracle

## <a name="metadata-node-types-and-ids"></a>Identificadores y tipos de nodo de metadatos 
El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies de Oracle de base de datos los artefactos de forma jerárquica. La tabla siguiente enumeran los tipos de nodo e identificadores de nodo para los artefactos de base de datos de Oracle que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies. El identificador de nodo es la ruta de acceso absoluta del nodo que se usa en el **IMetadataRetrievalContractBrowse**, **búsqueda**, y **GetMetadata** métodos.  

**Nombre de presentación de artefacto:--**  
Tipo de nodo: categoría  
Id. de nodo: /  
Ejemplo: /  
Descripción: [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] nodo raíz. Devuelve todos los nodos de primer nivel; Esto incluye todos los nodos de esquema, el nodo de operación POLLINGSTMT y el nodo de operación SQLEXECUTE

**Nombre de presentación de artefacto: SQLEXECUTE**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / SQLEXECUTE  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE`  
Descripción: Nodo de operación SQLEXECUTE. Devuelve el WSDL para la operación SQLEXECUTE.

**Nombre de presentación de artefacto: POLLINGSTMT**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / POLLINGSTMT  
Ejemplo: `http://Microsoft.LobServices. OracleDB/2007/03/POLLINGSTMT`  
Descripción: Nodo de operación POLLINGSTMT. Devuelve el WSDL para la operación POLLINGSTMT.

**Nombre para mostrar de artefacto: [DB_SCHEMA]**  
Tipo de nodo: categoría  
Id. de nodo: [Versión] / [DB_SCHEMA]  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT`  
Descripción: Nodo de esquema. Devuelve los nodos de categoría general (tabla, vista, procedimiento, función y paquete) para el esquema especificado.

**Nombre de presentación de artefacto: tabla**  
Tipo de nodo: categoría  
Id. de nodo: [Versión] / [DB_SCHEMA] / Table  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table`  
Descripción: Nodo de tablas esquema. Devuelve todos los nodos de tabla para el esquema especificado.

**Nombre para mostrar de artefacto: [DB_TABLE]**  
Tipo de nodo: categoría  
Id. de nodo: [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE]  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP`  
Descripción: Nodo de la tabla. Devuelve todos los nodos de operación (Insert, Select, Update, Delete, ReadLOB y UpdateLOB) de la tabla especificada. (ReadLOB y UpdateLOB son solo devuelve las tablas que contienen una columna LOB.)

**Nombre de presentación de artefacto: insertar**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / inserción  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert`  
Descripción: Nodo de operación de inserción de la tabla. Devuelve el WSDL para la operación de inserción de la tabla especificada.

**Nombre de presentación de artefacto: seleccionar**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / seleccione  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select`  
Descripción: Nodo de operación de selección de tabla. Devuelve el WSDL para la operación de selección de la tabla especificada.

**Nombre de presentación de artefacto: actualización**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / actualizar  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update`  
Descripción: Nodo de operación de actualización de la tabla. Devuelve el WSDL para la operación de actualización de la tabla especificada.

**Nombre de presentación de artefacto: eliminar**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / Delete  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete`  
Descripción: Nodo de operación de eliminación de la tabla. Devuelve el WSDL para la operación de eliminación de la tabla especificada.

**Nombre de presentación de artefacto: ReadLOB**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / ReadLOB  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/ReadLOB`  
Descripción: Nodo de operación de tabla ReadLOB. Devuelve el WSDL de la operación ReadLOB para la tabla especificada. (Solo aparece si la tabla contiene una columna LOB.)

**Nombre de presentación de artefacto: UpdateLOB**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /Table/ [DB_TABLE] / UpdateLOB  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/UpdateLOB`  
Descripción: Nodo de operación de tabla UpdateLOB. Devuelve el WSDL de la operación UpdateLOB para la tabla especificada. (Solo aparece si la tabla contiene una columna LOB.)

**Nombre de presentación de artefacto: vista**  
Tipo de nodo: categoría  
Id. de nodo: [Versión] / [DB_SCHEMA] / View  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View`  
Descripción: Nodo de vistas de esquema. Devuelve todos los nodos de la vista para el esquema especificado.

**Nombre para mostrar de artefacto: [DB_VIEW]**  
Tipo de nodo: categoría  
Id. de nodo: [Versión] / [DB_SCHEMA] /View/ [DB_VIEW]  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW`  
Descripción: Nodo de la vista. Devuelve todos los nodos de operación (Insert, Select, Update, Delete, ReadLOB y UpdateLOB) para la vista especificada. (ReadLOB y UpdateLOB son sólo devuelve para las vistas que contienen una columna LOB.)

**Nombre de presentación de artefacto: insertar**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / inserción  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Insert`  
Descripción: Nodo de operación de inserción de la vista. Devuelve el WSDL para la operación de inserción para la vista especificada.

**Nombre de presentación de artefacto: seleccionar**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / seleccione  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Select`  
Descripción: Nodo de operación de selección de vista. Devuelve el WSDL para la operación de selección de la vista especificada.

**Nombre de presentación de artefacto: actualización**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / actualizar  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Update`  
Descripción: Nodo de operación de actualización de la vista. Devuelve el WSDL para la operación de actualización de la vista especificada.

**Nombre de presentación de artefacto: eliminar**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / Delete  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Delete`  
Descripción: Nodo de operación de eliminación de la vista. Devuelve el WSDL para la operación de eliminación de la vista especificada.

**Nombre de presentación de artefacto: ReadLOB**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / ReadLOB  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/ReadLOB`  
Descripción: Nodo de operación ReadLOB de vista. Devuelve el WSDL de la operación ReadLOB para la vista especificada. (Solo aparece si la vista contiene una columna LOB.)

**Nombre de presentación de artefacto: UpdateLOB**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /View/ [DB_VIEW] / UpdateLOB  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/UpdateLOB`  
Descripción: Nodo de operación de actualización de la vista. Devuelve el WSDL de la operación UpdateLOB para la tabla especificada. (Solo aparece si la vista contiene una columna LOB.)

**Nombre de presentación de artefacto: procedimiento**  
Tipo de nodo: categoría  
Id. de nodo: [Versión] / [DB_SCHEMA] / procedimiento  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure`  
Descripción: Nodo de procedimientos esquema. Devuelve todos los procedimientos para el esquema especificado.

**Nombre para mostrar de artefacto: [DB_PROCEDURE]**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /Procedure/ [DB_PROCEDURE]  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_GENREPORT`  
Descripción: Nodo procedimiento. Devuelve el WSDL para el procedimiento especificado.

**Nombre de presentación de artefacto: función**  
Tipo de nodo: categoría  
Id. de nodo: [Versión] / [DB_SCHEMA] de función  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function`  
Descripción: Nodo de funciones esquema. Devuelve todas las funciones para el esquema especificado.

**Nombre para mostrar de artefacto: [DB_FUNCTION]**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /Function/ [DB_FUNCTION]  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETUSERID`  
Descripción: Nodo función. Devuelve el WSDL para la función especificada.

**Nombre de presentación de artefacto: paquete**  
Tipo de nodo: categoría  
Id. de nodo: [Versión] / [DB_SCHEMA] / paquete  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package`  
Descripción: Nodo de paquetes esquema. Devuelve todos los paquetes para el esquema especificado.

**Nombre para mostrar de artefacto: [DB_PACKAGE]**  
Tipo de nodo: categoría  
Id. de nodo: [Versión] / [DB_SCHEMA] /Package/ [DB_PACKAGE]  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG`  
Descripción: Nodo del paquete. Devuelve todos los procedimientos y funciones para el paquete especificado.

**Nombre para mostrar de artefacto: [PACK_PROCEDURE]**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /Package/ [DB_PACKAGE] / [PACK_PROCEDURE]  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT`  
Descripción: Nodo de procedimiento paquete. Devuelve el WSDL para el procedimiento de paquete especificado.

**Nombre para mostrar de artefacto: [PACK_FUNCTION]**  
Tipo de nodo: operación  
Id. de nodo: [Versión] / [DB_SCHEMA] /Package/ [DB_PACKAGE] / [PACK_FUNCTION]  
Ejemplo: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT`  
Descripción: Nodo de función paquete. Devuelve el WSDL para la función del paquete especificado.

[Versión] = la cadena de versión; Por ejemplo, `http://Microsoft.LobServices.OracleDB/2007/03`.  

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

 [Versión] = la cadena de versión; Por ejemplo, `http://Microsoft.LobServices/2007/03`.  

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
