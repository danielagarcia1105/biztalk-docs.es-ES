---
title: Esquemas de mensajes para LOB especiales Operations2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LOB data types, message structure of
- LOB data types, message actions for
ms.assetid: 031989d5-3209-41ab-8836-a40539781e74
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 203ffc81b6dc85fcaf7b80ff097bbeb001b747cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-special-lob-operations"></a>Esquemas de mensaje para operaciones especiales de LOB
Las operaciones de ReadLOB y UpdateLOB se exhibe para tablas y vistas que contienen columnas LOB; que es que las columnas que se utilizan para almacenar datos de objetos grandes (LOB) de Oracle. Estas operaciones permiten leer o escribir los datos de LOB como un flujo de datos codificados de base64Binary. Que operan en una sola columna de datos LOB en una sola fila.  
  
 Para obtener información general de las operaciones de ReadLOB y UpdateLOB y de los tipos de datos LOB de Oracle admite, consulte [operaciones en tablas y vistas que contienen datos LOB en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md).  
  
## <a name="message-structure-of-lob-data-type-operations"></a>Estructura de los mensajes de operaciones de tipo de datos LOB  
 En la tabla siguiente se muestra la estructura de los mensajes de solicitud y respuesta para las operaciones de ReadLOB y UpdateLOB. La tabla de destino para la operación especificada en la acción de mensaje y también aparece en el espacio de nombres de destino.  
  
|Operación|Mensaje XML|Description|  
|---------------|-----------------|-----------------|  
|ReadLOB|`<ReadLOB xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   <LOB_COLUMN>[COL_NAME]</LOB_COLUMN>   <FILTER>[WHERE_clause]</LOB_COLUMN> </ReadLOB>`|Los datos de LOB en el<br /><br /> -columna identificada por el elemento LOB_COLUMN y la<br /><br /> -fila que coincide con where cláusula especificada en el elemento de filtro<br /><br /> se devuelve.<br /><br /> Where cláusula debe coincidir con una única fila. Si hay más de una fila coincidente, se devuelven los datos de LOB en la primera fila coincidente.<br /><br /> **Importante** ReadLOB la operación está diseñado para admitir la transmisión de entrada de datos LOB en el modelo de servicio WCF. Debe usar una operación de selección de tabla para leer datos LOB de un modelo de canales de WCF o [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.|  
|Respuesta de ReadLOB|`<ReadLOBResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   <ReadLOBResult>     [LOB_DATA]   </ReadLOBResult> </ReadLOBResponse>`|Los datos de LOB se devuelven como un flujo de datos codificados de base64Binary.<br /><br /> **Importante** el WSDL devueltos por el adaptador no coincide con el esquema real utilizado por el adaptador para el mensaje de respuesta ReadLOB.|  
|UpdateLOB|`<UpdateLOB xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   <LOB_COLUMN>[COL_NAME]</LOB_COLUMN>   <FILTER>[WHERE_clause]</LOB_COLUMN>   <Stream>[LOB_DATA]</Stream> </UpdateLOB>`|Los datos de LOB en el<br /><br /> -columna identificada por el elemento LOB_COLUMN y la<br /><br /> -fila que coincide con where cláusula especificada en el elemento de filtro<br /><br /> se actualiza con los datos codificados de base64Binary en la secuencia.<br /><br /> Where cláusula debe coincidir con una única fila. Si hay más de una fila coincidente, se produce una excepción.<br /><br /> **Tenga en cuenta** UpdateLOB la operación reemplaza todos los datos en la columna especificada y la fila.|  
|Respuesta de UpdateLOB|`<UpdateLOBResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]"> </UpdateLOBResponse>`|Se devuelve una respuesta vacía.|  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, "http://Microsoft.LobServices/OracleDB/2007/03".  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [NombreTabla] = la tabla que contiene la columna destino de LOB; Por ejemplo, EMP.  
  
 [NombreColumna] = el nombre de la columna destino de LOB; Por ejemplo, LOB_FIELD.  
  
 [WHERE_clause] = la instrucción SELECT de base de datos de Oracle una cláusula WHERE que coincide con una sola fila; Por ejemplo, el Id. = 1.  
  
 [LOB_DATA] = el LOB de datos de columna en el tipo de base64Binary.  
  
> [!IMPORTANT]
>  La estructura del mensaje para las operaciones de ReadLOB y UpdateLOB en las vistas es igual que en las tablas salvo que el espacio de nombres para la operación especifica una vista en lugar de una tabla: `<ReadLOB xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`.  
  
## <a name="message-actions-for-lob-data-type-operations"></a>Acciones de mensaje para las operaciones de tipo de datos LOB  
 La siguiente tabla muestra las acciones de mensaje utilizados por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para las operaciones de ReadLOB y UpdateLOB en tablas. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa el nombre de tabla especificado en la acción de mensaje para determinar la tabla de destino para la operación.  
  
|Operación|Acción|Ejemplo|  
|---------------|------------|-------------|  
|ReadLOB|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/ReadLOB`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/ReadLOB`|  
|Respuesta de ReadLOB|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/ReadLOB/response`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/ReadLOB/response`|  
|UpdateLOB|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/UpdateLOB`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB`|  
|Respuesta de UpdateLOB|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/UpdateLOB/response`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB/response`|  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, "http://Microsoft.LobServices.OracleDB/2007/03".  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [NombreTabla] = la tabla que contiene la columna destino de LOB; Por ejemplo, el cliente. (El SCOTT. Tabla CUSTOMER se instala mediante un script SQL incluido en los ejemplos).  
  
> [!IMPORTANT]
>  La acción de mensaje para las operaciones de ReadLOB y UpdateLOB en las vistas es similar al usado para las tablas, excepto en que la acción para la operación especifica una vista en lugar de una tabla: `[VERSION]/[SCHEMA]/View/[VIEW_NAME]/ReadLOB`.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)