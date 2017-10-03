---
title: Esquemas de mensajes para los cursores REF cursor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- REF CURSORS, message schemas for
- IN REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: b62e7a9f-278c-41b3-90f0-2f621a34327b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bddfde0b0897c7d8c21a20126d2fa1d2f0f8c78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-ref-cursors"></a>Esquemas de mensaje para los cursores REF cursor
Un REF CURSOR es un tipo de datos de Oracle PL/SQL que representa un puntero a un conjunto de resultados en la base de datos de Oracle. Tipos de REF CURSOR habilitar la entrada y salida de transmisión por secuencias de datos y son ideales para transferir grandes cantidades de datos a y desde un bloque de código de PL/SQL. [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]proporciona compatibilidad para pasar parámetros REF CURSOR fuertemente tipadas y débilmente tipada a procedimientos de PL/SQL y funciones como en horizontal y los parámetros OUT en.  
  
 En la base de datos de Oracle, un tipo de REF CURSOR puede ser fuertemente tipado o débilmente tipada:  
  
-   Inflexible REF CURSOR se declara con una cláusula RETURN como en `TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`. Una variable de REF CURSOR fuertemente tipado solo puede representar un conjunto de resultados que contiene los datos que coincida con el tipo con el que se declara el tipo de REF CURSOR. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] devuelve un resultado fuertemente tipado establecidas para un CURSOR de REF fuertemente tipada.  
  
-   Débilmente tipada REF CURSOR se declara sin una cláusula RETURN como en `TYPE WeakCurType IS REF CURSOR;`. Oracle también proporciona un tipo especial de REF CURSOR denominado SYS_REFCURSOR que puede usarse para declarar variables de REF CURSOR débilmente tipada. Variables de REF CURSOR débilmente tipada pueden representar un conjunto de resultados que contiene cualquier tipo de datos de la fila. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] devuelve un conjunto de resultados débilmente tipada de registros genéricos para débilmente tipada REF CURSOR.  
  
## <a name="in-ref-cursor-parameters"></a>EN parámetros REF CURSOR  
 No hay ninguna API ODP.NET para crear un REF CURSOR en el servidor de Oracle, por lo que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no puede proporcionar la capacidad de un programa de cliente crear y mantener las variables de REF CURSOR.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] , sin embargo, habilitar al cliente para pasar parámetros REF CURSOR de IN a funciones o procedimientos almacenados mediante la especificación de un bloque de código de PL/SQL que devuelve un REF CURSOR. El adaptador usa este código para crear y abrir una variable de REF CURSOR en el servidor de Oracle; a continuación, llama a la función o el uso de esta variable como parámetro en el procedimiento almacenado.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] representa parámetros IN REF CURSOR como cadenas que contienen el bloque de código de PL/SQL. Dentro de este bloque, se especifica la ubicación de REF CURSOR con un signo de interrogación (?). El bloque de código de PL/SQL puede contener una instrucción FOR abierto que contiene una consulta SQL; o bien puede contener una llamada de función o un procedimiento en la que se devuelven un REF CURSOR abierto en un parámetro OUT.  
  
 A continuación muestra cómo especificar una en REF CURSOR mediante una llamada a un procedimiento almacenado o función para abrir el REF CURSOR.  
  
```  
<[IN_REF_CURSOR_PARAM_NAME]>begin [SP_NAME]([SP_PARAMS...], ?, [SP_PARAMS...]); end;</[IN_REF_CURSOR_PARAM_NAME]>  
  
Example:  
<EMP_RC>begin GETEMP(1, ?); end; </EMP_RC>  
```  
  
 A continuación muestra cómo especificar una en REF CURSOR mediante una consulta SELECT para abrir el REF CURSOR.  
  
```  
<IN_REF_CURSOR_PARAM_NAME>begin open ? for select [FIELD_NAMES] from [TABLE_NAME]; end;</IN_REF_CURSOR_PARAM_NAME>  
  
Example:  
<EMP_RC>begin open ? for select * from EMP; end;</EMP_RC>  
```  
  
## <a name="out-ref-cursor-parameters"></a>LOS parámetros REF CURSOR  
 SALIDA de REF CURSOR parámetros se devuelven como conjuntos de resultados fuertemente tipado o débilmente tipada. El tipo del conjunto de resultados devuelto depende de si el parámetro REF CURSOR se declara como un REF CURSOR fuertemente tipado o débilmente tipada en la definición de función o un procedimiento almacenada en el servidor Oracle. Se devuelve un conjunto de resultados fuertemente tipado para fuertemente tipado parámetros REF CURSOR y se devuelve un conjunto de resultados débilmente tipada para débilmente tipada parámetros REF CURSOR (por ejemplo, parámetros se declaran con un tipo SYS_REFCURSOR).  
  
 A continuación muestra el código XML para un parámetro de salida de REF CURSOR fuertemente tipada.  
  
```  
<[PARAM_NAME]>  
 <[PARAM_NAME]RECORD>  
  <[COL1_NAME]>value1</[COL1_NAME]>  
  <[COL2_NAME]>value2</[COL2_NAME]>  
  ...  
 </[PARAM_NAME]RECORD>  
</[PARAM_NAME]>  
  
[PARAM_NAME] = OUT REF CURSOR parameter name; for example, EMP_REFCURSOR  
[COL_NAME] = Name of a column in the REF CURSOR type; for example, Name.  
```  
  
 A continuación muestra el código XML para un parámetro de salida de REF CURSOR débilmente tipada.  
  
```  
<[PARAM_NAME]>  
 <GenRecordRow xmlns="oracledb">  
  <GenRecordColumn>  
   <ColumnName>COL_NAME</ColumnName>  
   <ColumnValue>COL_VALUE</ColumnValue>  
   <ColumnType>COL_TYPE</ColumnType>  
  </GenRecordColumn>  
  …  
 </GenRecordRow>  
 …  
</[PARAM_NAME]>  
  
[COL_NAME] = Name of column; for example, Name  
[COL_VALUE] = Column value; for example, Scott  
[COL_TYPE] = Column data type; for example, System.String  
```  
  
## <a name="in-out-ref-cursor-parameters"></a>EN los parámetros REF CURSOR  
 Dado que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] modela parámetros IN REF CURSOR como cadenas y parámetros de salida de REF CURSOR como tipos complejos, que no admite un único tipo para un parámetro OUT en REF CURSOR. Por esta razón, trata los parámetros OUT en REF CURSOR como dos parámetros diferentes: un parámetro IN en el mensaje de solicitud y un parámetro OUT en el mensaje de respuesta.  
  
 Para evitar un conflicto de nombres en la programación del modelo de servicio, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] anexa la cadena "_IN" para el parámetro en el mensaje de solicitud para que para un parámetro dado denominado [PARAM_NAME], se crean dos parámetros:  
  
-   _IN [PARAM_NAME] es un parámetro IN REF CURSOR en el procedimiento almacenado o un mensaje de solicitud de función. Contiene una instrucción de PL/SQL (una consulta select o una llamada de función o procedimiento almacenada) que devuelve un REF CURSOR.  
  
-   [PARAM_NAME] es un parámetro de salida de REF CURSOR en el procedimiento almacenado o el mensaje de respuesta de la función. Contiene la salida REF CURSOR como un conjunto de resultados fuertemente tipado o débilmente tipada.  
  
> [!IMPORTANT]
>  El adaptador no admite un procedimiento o función que contiene un parámetro IN denominado _IN [PARAM_NAME] y un parámetro de salida en REF CURSOR denominado [PARAM_NAME]. Esto es porque el adaptador espera un parámetro denominado _IN [PARAM_NAME] para representar la entrada para el parámetro REF CURSOR y no se puede especificar los dos parámetros en el mensaje de solicitud.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)