---
title: Ejecutar ExecuteNonQuery, ExecuteReader y operaciones de ExecuteScalar mediante el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fda0544-a028-4a95-aae6-1f6a90764c5d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7374a0852c4f6689a0c092e5ddf0b11c038d6e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990325"
---
# <a name="run-executenonquery-executereader-and-executescalar-operations-using-the-sql-adapter"></a>Ejecutar ExecuteNonQuery, ExecuteReader y operaciones de ExecuteScalar mediante el adaptador de SQL
La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone las siguientes operaciones en el nivel raíz:  
  
- **ExecuteNonQuery**: Use esta operación para ejecutar cualquier instrucción SQL arbitraria en SQL Server si no desea que cualquier conjunto de resultados a devolverse. Puede utilizar esta operación para crear objetos de base de datos o cambiar datos en una base de datos mediante la ejecución de UPDATE, INSERT o DELETE. El valor devuelto de esta operación es de tipo de datos Int32 y:  
  
  -   Para las instrucciones UPDATE, INSERT y DELETE, el valor devuelto es el número de filas afectadas por la instrucción SQL.  
  
  -   Para los demás tipos de instrucciones, el valor devuelto es **-1**.  
  
- **ExecuteReader**: Use esta operación para ejecutar todas las instrucciones SQL arbitrarias en SQL Server si desea que el conjunto de resultados que se devolverán, si existe, como una matriz de conjunto de datos. Para obtener información sobre el conjunto de datos, vea "Clase de conjunto de datos" en [ http://go.microsoft.com/fwlink/?LinkID=196853 ](http://go.microsoft.com/fwlink/?LinkID=196853).  
  
- **ExecuteScalar**: Use esta operación para ejecutar cualquier instrucción SQL arbitraria en SQL Server para devolver un valor único. Esta operación devuelve el valor solo en la primera columna de la primera fila del conjunto de resultados devuelto por la instrucción SQL.  
  
  > [!NOTE]
  >  La ventaja de ExecuteScalar sobre ExecuteReader es que la carga del mensaje de respuesta de la operación ExecuteScalar es mucho menor en comparación con el devuelto por la operación ExecuteReader. Por lo tanto, si necesita solo un valor que se devolverá, debe usar ExecuteScalar en lugar de ExecuteReader.  
  
  Puede usar la operación ExecuteNonQuery, ExecuteReader y ExecuteScalar para ejecutar varias instrucciones SQL.  
  
  Para obtener más información acerca de cómo realizar estas operaciones mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ExecuteReader, ExecuteScalar o ExecuteNonQuery las operaciones mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)