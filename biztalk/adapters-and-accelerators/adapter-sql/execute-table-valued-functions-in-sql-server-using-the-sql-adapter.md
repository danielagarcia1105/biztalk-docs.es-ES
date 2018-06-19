---
title: Ejecutar funciones con valores de tabla en SQL Server mediante el adaptador de SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fb8c81c-9384-4eba-b0a0-baed1782245b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e69877f214a2a4b700de22ec043094510707114d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222284"
---
# <a name="execute-table-valued-functions-in-sql-server-using-the-sql-adapter"></a>Ejecutar funciones con valores de tabla en SQL Server mediante el adaptador de SQL
Las funciones con valores de tabla de Transact-SQL y CLR en SQL Server se exponen como operaciones en [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]. El nombre de la operación en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es el mismo que el nombre de la tabla con valores de función en SQL Server.  
  
 Todos los parámetros de la función con valores de tabla se exponen en la operación correspondiente. Si no especifica un parámetro de entrada para una función con valores de tabla, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] internamente, se invoca la función mediante la palabra clave DEFAULT. Esto implica que la función con valores de tabla se ejecuta con el valor predeterminado especificado al definir la función.  
  
 Para obtener más información acerca de:  
  
-   Mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con BizTalk Server para invocar funciones con valores de tabla en SQL Server, vea [Invoking Table-Valued funciones en SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md).  
  
-   Estructura y acciones de SOAP para las funciones con valores de tabla de mensajes, vea [esquemas de mensaje para los procedimientos y funciones](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)