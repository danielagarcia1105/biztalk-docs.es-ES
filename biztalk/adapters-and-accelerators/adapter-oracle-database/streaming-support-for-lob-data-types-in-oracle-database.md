---
title: Compatibilidad para tipos de datos LOB en la base de datos de Oracle de streaming | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- streaming, node-value
- streaming
- LOB data
- streaming, node
ms.assetid: a4943cdf-8336-48ac-b592-52ec514e7300
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3f052b5051e511179ed0a3b371a619b315a16af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="streaming-support-for-lob-data-types-in-oracle-database"></a>Compatibilidad con Streaming para tipos de datos LOB en la base de datos de Oracle
La base de datos de Oracle admite la transmisión por secuencias en objetos grandes (LOB) tipos de datos. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]mensaje admite la transmisión por secuencias, lo cual posibilita la secuencia LOB datos-to-end entre un cliente de adaptador y la base de datos de Oracle. Sin embargo, transmisión por secuencias no se admite en la misma manera a través de todos los modelos de programación al usar el adaptador.  
  
 La siguiente muestra cómo-to-end de tipos de datos LOB de transmisión por secuencias es compatible con el adaptador a través de diferentes modelos de programación.  
  
|Operación|Modelo del canal de WCF|Modelo de servicio WCF|BizTalk Server|  
|---------------|-----------------------|-----------------------|--------------------|  
|Operación de inserción de la tabla o vista|No compatible|No compatible|No compatible|  
|Seleccione la tabla o vista de operación|Admitida|No compatible|Admitida|  
|Operación de actualización de la tabla o vista|No compatible|No compatible|No compatible|  
|Operación Eliminar tabla/vista|No compatible|No compatible|No compatible|  
|Operación de tabla o vista ReadLOB|Admite; Sin embargo, las operaciones de ReadLOB aparece principalmente para admitir la transmisión por secuencias en el modelo de servicio WCF, no se recomienda para su uso en el modelo de canal WCF. Utilice en su lugar una operación de selección o la operación SQLEXECUTE.|Admitida|La operación de ReadLOB no es compatible con BizTalk Server. Utilice en su lugar una operación de selección.|  
|Operación de tabla o vista UpdateLOB|Admitida|No se admite|Admitida|  
|Operación SQLEXECUTE|Compatible con la respuesta|No se admite|Compatible con la respuesta|  
|Operación de procedimiento y la función almacenado|Compatible con la respuesta|No se admite|Compatible con la respuesta|  
|Operación POLLINGSTMT|Admitida|No se admite|Admitida|  
  
 Para obtener información más completa acerca de cómo la transmisión por secuencias de tipos de datos LOB es compatible con el adaptador y cómo se admite cuando se utilizan varios modelos de programación con el adaptador, vea [tipos de datos de objetos grandes de transmisión por secuencias](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)