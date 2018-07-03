---
title: INSERT, Update, Delete y las operaciones Select en las tablas de Oracle y vistas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on tables and views
- operations, performing
- data manipulation language
- Delete operation
- Insert operation
- Update operation
- DELETE statement
- DML operation
- Select operation
- INSERT statement
- UPDATE statement
ms.assetid: af65fac4-3c16-40c4-ae7a-9c1757223f99
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b8ea0ed25119e43565a29c6d7c94a2e81a6ca6e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989973"
---
# <a name="insert-update-delete-and-select-operations-on-oracle-tables-and-views"></a>Insertar, actualizar, eliminar y seleccione las operaciones en tablas de Oracle y vistas
La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un conjunto de operaciones estándar en cada tabla de base de datos de Oracle y la vista. Mediante el uso de estas operaciones, puede realizar SELECT SQL INSERT, UPDATE, simple y eliminar instrucciones calificadas por una cláusula WHERE en la tabla de destino (o vista). Estas operaciones también se denominan operaciones (DML) de lenguaje de manipulación de datos. Para llevar a cabo operaciones más complejas, por ejemplo una consulta de SQL SELECT que utiliza el operador de combinación, puede usar la operación SQLEXECUTE. Para obtener más información acerca de la operación SQLEXECUTE, consulte [operación SQLEXECUTE en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md).  
  
 La siguiente tabla muestra las operaciones DML el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con:  
  
|Operación|Descripción|  
|---------------|-----------------|  
|Insert|Realiza una operación de inserción en la tabla de destino o vista. La operación de inserción admite varias inserciones de registro o de forma masiva en la vista o tabla de destino:<br /><br /> -Una operación de inserción varios registra inserta filas en una tabla o vista en función de un conjunto de registros proporcionado.<br /><br /> -Una operación de inserción masiva inserta filas en una tabla o vista basándose en una lista proporcionada de consulta y la columna SELECT de SQL. Los registros que devuelve la consulta se insertan en la tabla de destino basándose en la lista de columnas.<br /><br /> El valor devuelto para una operación de inserción es el número de filas insertadas.<br /><br /> **Nota:** insertar ambos varios registros y la inserción masiva no se pueden combinar en el mismo mensaje.<br /><br /> **InlineValue**<br /><br /> Para todos los registros de datos simple en una operación de insertar varios registro, puede elegir invalidar el valor de un registro especificando un valor para un atributo opcional denominado **InlineValue**. El atributo InlineValue puede usarse para insertar valores calculados en tablas o vistas como rellenar la columna de clave principal mediante una secuencia o insertar la fecha del sistema (mediante SYSDATE) en una columna de fecha. Por ejemplo, en la siguiente instrucción de INSERCIÓN:<br /><br /> `<Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">   <RECORDSET>     <ACCOUNTACTIVITYRECORDINSERT>       <ACCOUNT>10001</ACCOUNT>       <EMPNAME>John</EMPNAME>       <AMOUNT>1500</AMOUNT>       <TRANSDATE InlineValue="SYSDATE">2008-06-21T15:52:19</TRANSDATE>       </ACCOUNTACTIVITYRECORDINSERT >   </RECORDSET> </Insert>`<br /><br /> Aunque "2008-06-21T15:52:19" está especificada como un valor para la columna TRANSDATE, el valor del atributo InlineValue, "SYSDATE," (fecha del sistema) se insertará en la tabla de destino.<br /><br /> Al usar el InlineValue atributo:<br /><br /> -Evite el uso de valores constantes para el atributo InlineValue. Por ejemplo, en la instrucción INSERT, si especifica `<EMPNAME InlineValue="John"/>` , a continuación, se producirá un error. Esto es porque se pasa el valor del atributo InlineValue como-consiste en Oracle y en este caso *John* se pasa a la base de datos de Oracle, que no es el valor esperado (se esperaba el valor *'John'*). Se tendría que usar comillas simples para el nombre del empleado. Por ejemplo: `<EMPNAME InlineValue="’John’"/>`.<br /><br /> -Si quiere usar una consulta select para el atributo InlineValue, debe ir entre paréntesis la instrucción SELECT y asegúrese también de que la consulta select que recupera sólo un único registro. Por ejemplo: `<EMPNAME InlineValue="(SELECT NAME FROM MS_SAMPLE_EMPLOYEES WHERE ID=123)"/>`.<br /><br /> **Nota:** si un elemento está marcado como NOT NULL en la base de datos de Oracle, debe especificar un valor para ese elemento incluso si ha especificado un valor insertado. No se puede hacer esto provocará un error en la validación del esquema.|  
|Select|Realiza una consulta SELECT de SQL en la tabla de destino o una vista basada en una lista proporcionada de nombres de columna y una cadena de filtro que especifica una cláusula WHERE de SQL.<br /><br /> El valor devuelto para una operación de selección es un conjunto de resultados fuertemente tipado que contiene las filas y columnas especificadas.|  
|Update|Realiza una operación de actualización en la tabla de destino o vista. Los registros que se va a actualizarse se especifican mediante una cadena de filtro que especifica una cláusula WHERE de SQL. Los valores de la actualización se especifican en un registro de plantilla.<br /><br /> El valor devuelto para una operación de actualización es el número de filas actualizadas.|  
|DELETE|Realiza una operación de eliminación en la tabla de destino o una vista basada en una cláusula WHERE de SQL que se especifica en una cadena de filtro.<br /><br /> El valor devuelto para una operación de eliminación es el número de filas eliminadas.|  
  
 Para obtener más información acerca de:  
  
- Realizar estas operaciones mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [Insert, Update, Delete y seleccione las operaciones mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-using-biztalk-server-with-oracle-db.md).  
  
- Realizar estas operaciones mediante el modelo de servicio WCF, consulte [Insert, Update, Delete y seleccione las operaciones mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md).  
  
- Realizar estas operaciones mediante el modelo de canal WCF, consulte [ejecutar una operación de inserción en la base de datos de Oracle mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md).  
  
- Mensaje de acción SOAP para realizar operaciones de DML y estructuras, vea [esquemas de mensaje para insertar básica, Update, Delete y seleccione operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)