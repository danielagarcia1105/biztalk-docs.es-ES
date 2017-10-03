---
title: Esquemas de mensajes para LOB especiales Operations1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2e418a6-8bc7-42d9-9672-a9c149f32778
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ecc0554162b1cf8298b441c0d129bee83540011
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-special-lob-operations"></a>Esquemas de mensaje para operaciones especiales de LOB
El Read_\<LOBColName > y Update_\<LOBColName > se producen operaciones de tablas y vistas que contienen columnas LOB, donde \<LOBColName > es la columna LOB de la tabla o vista. Estas operaciones permiten leer o escribir los datos de LOB como un flujo de datos codificados de base64Binary. Que operan en una sola columna de datos LOB en una sola fila.  
  
 Para obtener información general de la Read_\<LOBColName > y Update_\<LOBColName > operaciones y de tipos de datos de LOB de Oracle admite, consulte [operaciones en tablas de interfaz, vistas de interfaz, tablas y vistas que contienen LOB Datos](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md).  
  
## <a name="message-structure-of-lob-data-type-operations"></a>Estructura de los mensajes de operaciones de tipo de datos LOB  
 En la tabla siguiente muestra la estructura de los mensajes de solicitud y respuesta de la Read_\<LOBColName > y Update_\<LOBColName > operaciones. La tabla de destino para la operación especificada en la acción de mensaje y también aparece en el espacio de nombres de destino.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|Operación|Mensaje XML|Description|  
|---------------|-----------------|-----------------|  
|Read_\<LOBColName >|`<Read_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</FILTER></Read_[LOBColName]>`|Los datos de LOB en la fila que coincide con la donde se devuelve la cláusula especificada en el elemento del filtro. Where cláusula debe coincidir con una única fila. Si hay más de una fila coincidente, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se iniciará una excepción.|  
|Read_\<LOBColName > respuesta|`<Read_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <Read_[LOBColName]Result>    [LOB_DATA]  </Read_[LOBColName]Result></Read_[LOBColName]Response>`|Los datos de LOB se devuelven como un flujo de datos codificados de base64Binary.|  
|Update_\<LOBColName >|`<Update_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</LOB_COLUMN>  <DATA>[Value]</DATA></Update_[LOBColName]>`|Los datos de LOB en la fila que coincide con where cláusula especificada en el elemento de filtro se actualiza con los datos en el \<datos > elemento. Where cláusula debe coincidir con una única fila. Si hay más de una fila coincidente, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] produce una excepción.<br /><br /> **Tenga en cuenta** al actualizar las columnas BLOB, el \<datos > elemento siempre debe contener un valor codificado en base64. Para CLOB y NCLOB, el \<datos > elemento puede tener valores de cadena.|  
|Update_\<LOBColName > respuesta|`<Update_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]"></Update_[LOBColName]Response>`|Se devuelve una respuesta vacía.|  
  
 Descripciones de entidad:  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, "http://schemas.microsoft.com/OracleEBS/2008/05".  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [NombreTabla] = la tabla que contiene la columna destino de LOB; Por ejemplo, el cliente.  
  
 [LOBCol_Name] = el nombre de una columna LOB; Por ejemplo, la fotografía.  
  
 [WHERE_clause] = la instrucción SELECT de base de datos de Oracle una cláusula WHERE que coincide con una sola fila; Por ejemplo, el Id. = 1.  
  
 [LOB_DATA] = el LOB de datos de columna en el tipo de base64Binary.  
  
> [!IMPORTANT]
>  La estructura del mensaje para la Read_\<LOBColName > y Update_\<LOBColName > operaciones en las vistas es el mismo que en las tablas salvo que el espacio de nombres para la operación especifica una vista en lugar de una tabla: `<ReadLOB xmlns ="[VERSION]/Views/[SCHEMA]/[VIEW_NAME]">`.  
  
## <a name="message-actions-for-lob-data-type-operations"></a>Acciones de mensaje para las operaciones de tipo de datos LOB  
 La siguiente tabla muestra las acciones de mensaje utilizados por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para el Read_\<LOBColName > y Update_\<LOBColName > operaciones en tablas. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa el nombre de tabla y el nombre de columna LOB especificado en la acción de mensaje para determinar la tabla de destino y la columna para la operación de LOB.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|Operación|Acción|Ejemplo|  
|---------------|------------|-------------|  
|Read_\<LOBColName >|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo`|  
|Read_\<LOBColName > respuesta|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo/response`|  
|Update_\<LOBColName >|**Para BLOB**:<br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`<br /><br /> **Para CLOB y NCLOB**:<br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|**Para BLOB**:<br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/`<br /><br /> **Para CLOB y NCLOB**:<br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/`|  
|Update_\<LOBColName > respuesta|**Para BLOB**:<br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`<br /><br /> **Para CLOB y NCLOB**:<br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|**Para BLOB**:<br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/response`<br /><br /> **Para CLOB y NCLOB**:<br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/response`|  
  
 Descripciones de entidad:  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [NombreTabla] = la tabla que contiene la columna destino de LOB; Por ejemplo, el cliente. (El SCOTT. Tabla CUSTOMER se instala mediante un script SQL incluido en los ejemplos).  
  
 [LOBCol_Name] = el nombre de una columna LOB; Por ejemplo, la fotografía.  
  
> [!IMPORTANT]
>  La acción de mensaje para Read_\<LOBColName > y Update_\<LOBColName > operaciones en las vistas es similar al usado para las tablas, salvo que la acción para la operación especifica una vista en lugar de una tabla: `Views/ReadLOB/[SCHEMA]/[VIEW_NAME]/[LOBColName]`.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)