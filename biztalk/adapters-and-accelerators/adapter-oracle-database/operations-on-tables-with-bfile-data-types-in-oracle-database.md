---
title: Operaciones en tablas con tipos de datos BFILE de Oracle Database | Microsoft Docs
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
ms.openlocfilehash: ab9885497468f91b309eb51ac0abbf4c0807ca76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998261"
---
# <a name="operations-on-tables-with-bfile-data-types-in-oracle-database"></a>Operaciones en tablas con tipos de datos BFILE de Oracle Database
El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con el tipo de datos BFILE en tablas y procedimientos almacenados. La tabla siguiente resume el tipo de datos BFILE expuestos por el adaptador basado en la operación realizada y el artefacto LOB (tabla/procedimiento) acceso:  
  
|Artefacto|Operación|Tipo de datos expuesto para BFILE col/param|Comentarios|  
|--------------|---------------|--------------------------------------------|--------------|  
|TABLE|INSERT|String|Representa la ruta de acceso de directorio lógica de Oracle en el archivo que se va a insertar en la columna BFILE<br /><br /> Por ejemplo: MYDIR/screen.jpg donde MYDIR es un directorio lógico de Oracle|  
|TABLE|UPDATE|String|Representa la ruta de acceso de directorio lógica de Oracle para el archivo se actualice en la columna BFILE|  
|TABLE|SELECT|byte[]|Representa los datos binarios que constituyen el BFILE|  
|PROCEDIMIENTO ALMACENADO|PARÁMETRO DE ENTRADA|String|Representa la ruta de acceso de directorio lógica de Oracle en el archivo que se va a insertar en la columna BFILE<br /><br /> Por ejemplo: MYDIR/screen.jpg donde MYDIR es un directorio lógico de Oracle|  
|PROCEDIMIENTO ALMACENADO|PARÁMETRO DE SALIDA|String|Representa la ruta de acceso de directorio lógica de Oracle en el archivo que se va a insertar en la columna BFILE<br /><br /> Por ejemplo: MYDIR/screen.jpg donde MYDIR es un directorio lógico de Oracle|  
|PROCEDIMIENTO ALMACENADO|PARAM INOUT|No se admite|-|  
  
 La operación especial ReadLOB también se admite en tablas con el tipo de datos BFILE. No se admite la operación UpdateLOB. Los clientes del adaptador como alternativa pueden usar la operación de actualización.  
  
 Para obtener más información acerca de:  
  
- Realizar operaciones en tablas que contienen tipos de datos BFILE utilizando [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones en tablas con tipos de datos BFILE de base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)