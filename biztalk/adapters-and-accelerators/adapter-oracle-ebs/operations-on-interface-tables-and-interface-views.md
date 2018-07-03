---
title: Operaciones en tablas y vistas de interfaz | Microsoft Docs
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
ms.openlocfilehash: ffcf9b26f745112b4748c0020fd761f233caedd8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992037"
---
# <a name="operations-on-interface-tables-and-interface-views"></a>Operaciones en tablas y vistas de interfaz
La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone un conjunto de operaciones estándar (Select, Insert, Update y Delete para cada tabla de interfaz) y la operación de selección para cada vista de interfaz en Oracle E-Business Suite. Mediante el uso de estas operaciones, puede realizar la SELECT, INSERT, UPDATE y eliminar instrucciones calificadas por una cláusula WHERE en la tabla de la interfaz de destino y la instrucción SELECT calificada por una cláusula WHERE en la vista de la interfaz de destino. Estas operaciones también se denominan operaciones (DML) de lenguaje de manipulación de datos.  
  
> [!IMPORTANT]
>  Para poder realizar operaciones en tablas y vistas de interfaz, debe establecer el contexto de las aplicaciones por estos artefactos en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Esto es porque el contexto de las aplicaciones de configuración facilita transacciones seguras en Oracle E-Business Suite estableciendo las preferencias del usuario (por ejemplo, la configuración de idioma, la organización y la responsabilidad) y el control de acceso de un artefacto. Para obtener más información sobre el contexto de las aplicaciones y cómo configurarlo, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  

## <a name="supported-dml-operations"></a>Operaciones de DML admitidas  
 La siguiente tabla muestra las operaciones DML el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con:  
  
|Operación|Descripción|  
|---------------|-----------------|  
|Select|Realiza una operación seleccionar en la vista tabla o la interfaz de interfaz destino basándose en una lista proporcionada de nombres de columna y una cadena de filtro que especifica una cláusula WHERE de SQL.<br /><br /> El valor devuelto para una operación de selección es un conjunto de resultados fuertemente tipado que contiene las filas y columnas especificadas.|  
|Insert|Realiza una operación de inserción en la tabla de la interfaz de destino. Inserte la inserción operación admite varios registros en la tabla de la interfaz de destino basándose en un conjunto de registros proporcionado.<br /><br /> El valor devuelto para una operación de inserción es el número de filas insertadas.<br /><br /> **InlineValue**<br /><br /> Para todos los registros de datos simple en una operación de inserción, puede elegir invalidar el valor de un registro especificando un valor para un atributo opcional denominado **InlineValue**. El atributo InlineValue puede usarse para insertar valores calculados en tablas de interfaz como rellenar la columna de clave principal mediante una secuencia o insertar la fecha del sistema (mediante SYSDATE) en una columna de fecha. Por ejemplo, en la siguiente instrucción de INSERCIÓN:<br /><br /> `<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR_ARCHIVE_PURGE_INTERIM">   <RECORDSET>     <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">       <TRNS_DATE InlineValue="sysdate">2008-06-21T15:52:19</TRNS_DATE>       <EMPNAME>John</EMPNAME>     </InsertRecord>   </RECORDSET>   </Insert>`<br /><br /> Aunque "2008-06-21T15:52:19" se especifica como un valor para TRNS_DATE, el valor de la **InlineValue** atributo, "SYSDATE," (fecha del sistema) se insertará en la tabla de la interfaz de destino.<br /><br /> Al usar el InlineValue atributo:<br /><br /> -Evite el uso de valores constantes para el atributo InlineValue. Por ejemplo, en la instrucción INSERT, si especifica `<EMPNAME InlineValue="John"/>` , a continuación, se producirá un error. Esto es porque se pasa el valor del atributo InlineValue como-consiste en Oracle y en este caso *John* se pasa a Oracle E-Business Suite, no es el valor esperado (se esperaba el valor *'John'*). Se tendría que usar comillas simples para el nombre del empleado. Por ejemplo: `<EMPNAME InlineValue="’John’"/>`.<br /><br /> -Si quiere usar una consulta select para el atributo InlineValue, debe ir entre paréntesis la instrucción SELECT y asegúrese también de que la consulta select que recupera sólo un único registro. Por ejemplo: `<EMPNAME InlineValue="(SELECT NAME FROM MS_SAMPLE_EMPLOYEES WHERE ID=123)"/>`.<br /><br /> **Nota:** si un elemento está marcado como NOT NULL en Oracle E-Business Suite, debe especificar un valor para ese elemento incluso si ha especificado un valor insertado. No se puede hacer esto provocará un error en la validación del esquema.|  
|Update|Realiza una operación de actualización en la tabla de la interfaz de destino. Los registros que se va a actualizarse se especifican mediante una cadena de filtro que especifica una cláusula WHERE de SQL. Los valores de la actualización se especifican en un registro de plantilla.<br /><br /> El valor devuelto para una operación de actualización es el número de filas actualizadas.|  
|DELETE|Realiza una operación de eliminación en la tabla de interfaz de destino basándose en una cláusula WHERE de SQL que se especifica en una cadena de filtro.<br /><br /> El valor devuelto para una operación de eliminación es el número de filas eliminadas.|  

## <a name="important-details"></a>Detalles importantes  
- La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone el mismo conjunto de operaciones estándar (Select, Insert, Update y Delete para cada tabla) y la operación de selección para cada vista en la base de datos de Oracle subyacente. Las operaciones de DML anteriores también son válidas para las tablas subyacentes de base de datos de Oracle y vistas.  

  - No es necesario para establecer el contexto de las aplicaciones para realizar operaciones en tablas y vistas en la base de datos de Oracle. Sin embargo, para las aplicaciones personalizadas de Oracle E-Business Suite, los usuarios pueden o no pueden registrar las tablas de base de datos como tablas de interfaz. Si una tabla de base de datos no está registrada como una tabla de interfaz, está disponible en el **tablas** subnodo en el **vista basado en el artefacto** nodo o en el **vista esquema** nodo en tiempo de diseño mientras usa [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
    Estas tablas están asociadas con una aplicación de Oracle E-Business. Por lo que para cualquier operación en estas tablas, debe establecer el contexto de la aplicación. Consulte el contexto de la aplicación establezca[escribir descripción del vínculo](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)