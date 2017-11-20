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
# <a name="resolving-database-errors"></a><span data-ttu-id="07f64-102">Resolver errores de base de datos</span><span class="sxs-lookup"><span data-stu-id="07f64-102">Resolving Database Errors</span></span>
<span data-ttu-id="07f64-103">En la base de datos de Access HL7 que publica la organización HL7, DataItems y TableValues son dos tablas vinculadas mediante table_id y hl7_version.</span><span class="sxs-lookup"><span data-stu-id="07f64-103">In the HL7 Access database that the HL7 organization publishes, DataItems and TableValues are two tables linked by table_id and hl7_version.</span></span> <span data-ttu-id="07f64-104">La siguiente base de datos entre-consulta muestra que algunos elementos de datos hacen referencia a un table_id, que no tienen valores enumerados en la tabla:</span><span class="sxs-lookup"><span data-stu-id="07f64-104">The following database cross-query shows that some data items refer to a table_id, which has no values listed in the table:</span></span>  
  
```  
select distinct d.table_id, d.hl7_version, t.table_item from DataElements as d left join TableValues as t on   
   d.table_id = t.table_id and d.hl7_version = t.hl7_version where d.table_id <>0 order by d.table_id  
```  
  
 <span data-ttu-id="07f64-105">Si la base de datos de Access de HL7 tiene los valores de enumeración que faltan, debe cross Compruebe los valores manualmente con las especificaciones de HL7 y utilizar esos valores en el esquema.</span><span class="sxs-lookup"><span data-stu-id="07f64-105">If the HL7 Access database has missing enumeration values, you must cross check the values manually with the HL7 specifications and use those values in your schema.</span></span> <span data-ttu-id="07f64-106">Una manera de solucionarlo es agregar una lista de enumeración al esquema.</span><span class="sxs-lookup"><span data-stu-id="07f64-106">One way to deal with this situation is to add an enumeration list to the schema.</span></span> <span data-ttu-id="07f64-107">Para ello, consulte [extender enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="07f64-107">To do so, see [Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f64-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="07f64-108">See Also</span></span>  
 <span data-ttu-id="07f64-109">[Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="07f64-109">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 [<span data-ttu-id="07f64-110">Extender HL7 2.X esquemas con objetos de Z</span><span class="sxs-lookup"><span data-stu-id="07f64-110">Extending HL7 2.X Schemas with Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)