---
title: Operaciones en tablas con tipos de datos BFILE de base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on tables with BFILE data types
- BFILE data type
- BFILE
ms.assetid: 7937564e-4423-459f-9824-6a27113ebfb3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c236651e6c44248ea8f6cf0f73f0c9bc17e46ac5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214316"
---
# <a name="operations-on-tables-with-bfile-data-types-in-oracle-database"></a>Operaciones en tablas con tipos de datos BFILE de base de datos de Oracle
El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con el tipo de datos BFILE en tablas y procedimientos almacenados. En la tabla siguiente se resume el tipo de datos BFILE expuestos por el adaptador en función de la operación realizada y el artefacto LOB (tabla o procedimiento) tiene acceso:  
  
|Artefacto|Operación|Tipo de datos expuesto para BFILE col/param|Comentarios|  
|--------------|---------------|--------------------------------------------|--------------|  
|TABLE|INSERT|String|Representa la ruta de acceso lógica del directorio de Oracle en el archivo que se va a insertar en la columna BFILE<br /><br /> Por ejemplo: MYDIR/screen.jpg donde MYDIR es un directorio lógico de Oracle|  
|TABLE|UPDATE|String|Representa la ruta de acceso lógica del directorio de Oracle en el archivo se actualicen en la columna BFILE|  
|TABLE|SELECT|byte[]|Representa los datos binarios que constituyen el BFILE|  
|PROCEDIMIENTO ALMACENADO|PARÁMETRO DE ENTRADA|String|Representa la ruta de acceso lógica del directorio de Oracle en el archivo que se va a insertar en la columna BFILE<br /><br /> Por ejemplo: MYDIR/screen.jpg donde MYDIR es un directorio lógico de Oracle|  
|PROCEDIMIENTO ALMACENADO|PARÁMETRO DE SALIDA|String|Representa la ruta de acceso lógica del directorio de Oracle en el archivo que se va a insertar en la columna BFILE<br /><br /> Por ejemplo: MYDIR/screen.jpg donde MYDIR es un directorio lógico de Oracle|  
|PROCEDIMIENTO ALMACENADO|INOUT PARAM|No se admite|-|  
  
 La operación especial ReadLOB también se admite en las tablas con el tipo de datos BFILE. No se admite la operación de UpdateLOB. Los clientes de adaptador o bien pueden usar la operación de actualización.  
  
 Para obtener más información acerca de:  
  
-   Realizar operaciones en tablas que contienen tipos de datos BFILE utilizando [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones en tablas con tipos de datos BFILE de base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)