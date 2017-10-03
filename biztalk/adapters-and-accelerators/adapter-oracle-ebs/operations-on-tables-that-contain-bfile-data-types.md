---
title: Operaciones en tablas que contienen tipos de datos BFILE | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d7ebeb9-c2d6-4024-a169-263b947eeeb1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 122d821754fb6df447067d18f6f5da02b79058e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-tables-that-contain-bfile-data-types"></a>Operaciones en tablas que contienen tipos de datos BFILE
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es compatible con el tipo de datos BFILE en tablas y procedimientos almacenados. 

## <a name="bfile-data-types"></a>Tipos de datos BFILE
En la tabla siguiente se resume el tipo de datos BFILE expuestos por el adaptador en función de la operación realizada y el artefacto LOB (tabla o procedimiento) tiene acceso:  
  
|Artefacto|Operación|Tipo de datos expuesto para BFILE col/param|Comentarios|  
|--------------|---------------|--------------------------------------------|--------------|  
|TABLE|INSERT|String|Representa la ruta de acceso lógica del directorio de Oracle en el archivo que se va a insertar en la columna BFILE<br /><br /> Por ejemplo: MYDIR/screen.jpg donde MYDIR es un directorio lógico de Oracle|  
|TABLE|UPDATE|String|Representa la ruta de acceso lógica del directorio de Oracle en el archivo se actualicen en la columna BFILE|  
|TABLE|SELECT|byte[]|Representa los datos binarios que constituyen el BFILE|  
|PROCEDIMIENTO ALMACENADO|PARÁMETRO DE ENTRADA|String|Representa la ruta de acceso lógica del directorio de Oracle en el archivo que se va a insertar en la columna BFILE<br /><br /> Por ejemplo: MYDIR/screen.jpg donde MYDIR es un directorio lógico de Oracle|  
|PROCEDIMIENTO ALMACENADO|PARÁMETRO DE SALIDA|String|Representa la ruta de acceso lógica del directorio de Oracle en el archivo que se va a insertar en la columna BFILE<br /><br /> Por ejemplo: MYDIR/screen.jpg donde MYDIR es un directorio lógico de Oracle|  
|PROCEDIMIENTO ALMACENADO|INOUT PARAM|No se admite|-|  
  
 La operación especial `Read_<LOBColName>` también se admite en las tablas con el tipo de datos BFILE, donde \<LOBColName > es el nombre de columna LOB de la tabla. El `Update_<LOBColName>` operación no es compatible con el tipo de datos BFILE. Los clientes de adaptador o bien pueden usar la operación de actualización.  
  
## <a name="more-good-info"></a>Más información válida  
  
-   El `Read_<LOBColName>` y `Update_<LOBColName>` operaciones, consulte [operaciones en tablas de interfaz, vistas de interfaz, tablas y vistas que contienen LOB datos](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)