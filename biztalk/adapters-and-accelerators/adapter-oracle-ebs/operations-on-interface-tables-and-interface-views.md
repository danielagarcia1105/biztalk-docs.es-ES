---
title: Operaciones en tablas de interfaz y vistas de interfaz | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c7f3453-848f-42df-b092-725d9ff466cf
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ec9b7c5f952b6be60a3c3463e6ea0682faa9d4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217108"
---
# <a name="operations-on-interface-tables-and-interface-views"></a>Operaciones en tablas de interfaz y vistas de interfaz
La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone un conjunto de operaciones estándar (Select, Insert, Update y Delete para cada tabla de interfaz) y la operación de selección para cada vista de la interfaz en Oracle E-Business Suite. Mediante el uso de estas operaciones, puede realizar la SELECT, INSERT, UPDATE y eliminar instrucciones calificadas por una cláusula WHERE en la tabla de interfaz de destino y la instrucción SELECT calificado por una cláusula WHERE en la vista de la interfaz de destino. Estas operaciones también se denominan operaciones de DML (lenguaje) de manipulación de datos.  
  
> [!IMPORTANT]
>  Para poder realizar operaciones en tablas de interfaz y vistas de interfaz, debe establecer el contexto de las aplicaciones para estos artefactos en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Esto es porque el contexto de las aplicaciones de configuración facilita transacciones seguras en Oracle E-Business Suite estableciendo las preferencias del usuario (como la configuración de responsabilidad, su organización y language) y control de acceso de un artefacto. Para obtener más información sobre el contexto de las aplicaciones y cómo configurarlo, vea [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  

## <a name="supported-dml-operations"></a>Operaciones de DML admitidas  
 La siguiente tabla muestra las operaciones DML que la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con:  
  
|Operación|Description|  
|---------------|-----------------|  
|Select|Realiza una operación seleccionar en la vista tabla o la interfaz de interfaz destino basándose en una lista de nombres de columna y una cadena de filtro que especifica una cláusula WHERE de SQL especificada.<br /><br /> El valor devuelto para una operación de selección es un conjunto de resultados fuertemente tipadas que contiene las filas y columnas especificadas.|  
|Insert|Realiza una operación de inserción en la tabla de interfaz de destino. Inserte la inserción operación admite varios registros en la tabla de interfaz de destino basándose en un conjunto de registros proporcionado.<br /><br /> El valor devuelto para una operación de inserción es el número de filas insertadas.<br /><br /> **InlineValue**<br /><br /> Para todos los registros de datos simple en una operación de inserción, puede elegir invalidar el valor de un registro especificando un valor para un atributo opcional llamado **InlineValue**. El atributo InlineValue se puede usar para insertar valores calculados en tablas de interfaz como rellenar la columna de clave principal mediante una secuencia o insertar la fecha del sistema (mediante SYSDATE) en una columna de fecha. Por ejemplo, en la siguiente instrucción de INSERCIÓN:<br /><br /> `<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR_ARCHIVE_PURGE_INTERIM">   <RECORDSET>     <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">       <TRNS_DATE InlineValue="sysdate">2008-06-21T15:52:19</TRNS_DATE>       <EMPNAME>John</EMPNAME>     </InsertRecord>   </RECORDSET>   </Insert>`<br /><br /> Aunque "2008-06-21T15:52:19" se especifica como un valor para TRNS_DATE, el valor de la **InlineValue** atributo, "SYSDATE," (fecha del sistema) se insertarán en la tabla de interfaz de destino.<br /><br /> Al usar el InlineValue atributo:<br /><br /> -Evite el uso de valores constantes para el atributo InlineValue. Por ejemplo, en la instrucción INSERT, si especifica `<EMPNAME InlineValue="John"/>` , a continuación, se producirá un error. Esto es porque se pasa el valor del atributo InlineValue como-consiste en Oracle y en este caso *John* se pasa a Oracle E-Business Suite, que no es el valor esperado (se esperaba el valor *'John'*). Tendría que usar comillas en el nombre del empleado. Por ejemplo: `<EMPNAME InlineValue="’John’"/>`.<br /><br /> -Si desea utilizar una consulta select para el atributo InlineValue, debe incluir la instrucción SELECT entre paréntesis y asegúrese también de que la consulta select captura solo un único registro. Por ejemplo: `<EMPNAME InlineValue="(SELECT NAME FROM MS_SAMPLE_EMPLOYEES WHERE ID=123)"/>`.<br /><br /> **Nota:** si un elemento se marca como NOT NULL en Oracle E-Business Suite, debe especificar un valor para dicho elemento incluso si ha especificado un valor insertado. Si no lo hará que la validación de esquema producirá un error.|  
|Update|Realiza una operación de actualización en la tabla de interfaz de destino. Los registros que se actualizarán se especifican mediante una cadena de filtro que especifica una cláusula WHERE de SQL. Los valores para la actualización se especifican en un registro de plantilla.<br /><br /> El valor devuelto para una operación de actualización es el número de filas actualizadas.|  
|DELETE|Realiza una operación de eliminación en la tabla de interfaz de destino basándose en una cláusula WHERE de SQL que se especifica en una cadena de filtro.<br /><br /> El valor devuelto para una operación de eliminación es el número de filas eliminadas.|  

## <a name="important-details"></a>Detalles importantes  
  -   La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone el mismo conjunto de operaciones estándar (Select, Insert, Update y Delete para cada tabla) y la operación de selección para cada vista en la base de datos de Oracle subyacente. Las operaciones de DML anteriores también son válidas para las tablas de base de datos de Oracle subyacentes y vistas.  

 -   No es necesario para establecer el contexto de las aplicaciones para realizar operaciones en tablas y vistas en la base de datos de Oracle. Sin embargo, para aplicaciones personalizadas de Oracle E-Business Suite, los usuarios pueden o no pueden registrar las tablas de base de datos como tablas de interfaz. Si una tabla de base de datos no está registrada como una tabla de interfaz, está disponible en la **tablas** subnodo en el **basado en el artefacto vista** nodo o en la **vista esquema** nodo en tiempo de diseño durante el uso de [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
    Estas tablas están asociadas a una aplicación de Oracle E-Business. Por lo que para cualquier operación en estas tablas, debe establecer el contexto de la aplicación. Vea Establecer contexto de la aplicación[escriba la descripción del vínculo](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)