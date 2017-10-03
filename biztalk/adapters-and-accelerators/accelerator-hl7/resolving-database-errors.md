---
title: Resolver errores de base de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases
- errors, databases
ms.assetid: d7b1cc9f-3f3e-464a-8249-1fd03b2b4d76
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47a22877cf06f03f875138208281420e56963da9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="resolving-database-errors"></a>Resolver errores de base de datos
En la base de datos de Access HL7 que publica la organización HL7, DataItems y TableValues son dos tablas vinculadas mediante table_id y hl7_version. La siguiente base de datos entre-consulta muestra que algunos elementos de datos hacen referencia a un table_id, que no tienen valores enumerados en la tabla:  
  
```  
select distinct d.table_id, d.hl7_version, t.table_item from DataElements as d left join TableValues as t on   
   d.table_id = t.table_id and d.hl7_version = t.hl7_version where d.table_id <>0 order by d.table_id  
```  
  
 Si la base de datos de Access de HL7 tiene los valores de enumeración que faltan, debe cross Compruebe los valores manualmente con las especificaciones de HL7 y utilizar esos valores en el esquema. Una manera de solucionarlo es agregar una lista de enumeración al esquema. Para ello, consulte [extender enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md).  
  
## <a name="see-also"></a>Vea también  
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)