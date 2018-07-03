---
title: Ejecutar funciones con valores de tabla en SQL Server mediante el adaptador de SQL | Microsoft Docs
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
ms.openlocfilehash: dab49fa57a3132a75fd937f1d89333577d28c420
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007237"
---
# <a name="execute-table-valued-functions-in-sql-server-using-the-sql-adapter"></a><span data-ttu-id="97e35-102">Ejecutar funciones con valores de tabla en SQL Server mediante el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="97e35-102">Execute Table-Valued Functions in SQL Server using the SQL adapter</span></span>
<span data-ttu-id="97e35-103">Las funciones con valores de tabla de Transact-SQL y CLR en SQL Server se exponen como operaciones en [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97e35-103">The Transact-SQL and CLR table valued functions in SQL Server are surfaced as operations in [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span> <span data-ttu-id="97e35-104">El nombre de la operación en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es el mismo que el nombre de la tabla con valores de función en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="97e35-104">The operation name in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is the same as the name of the table valued function in SQL Server.</span></span>  
  
 <span data-ttu-id="97e35-105">Todos los parámetros de la función con valores de tabla se exponen en la operación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="97e35-105">All the parameters in the table valued function are exposed in the corresponding operation.</span></span> <span data-ttu-id="97e35-106">Si no especifica un parámetro de entrada para una función con valores de tabla, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] llama internamente a la función mediante la palabra clave DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="97e35-106">If you do not specify an input parameter for a table valued function, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] internally invokes the function using the DEFAULT keyword.</span></span> <span data-ttu-id="97e35-107">Esto implica que la función con valores de tabla se ejecuta con el valor predeterminado especificado durante la definición de la función.</span><span class="sxs-lookup"><span data-stu-id="97e35-107">This implies that the table valued function is executed using the default value specified while defining the function.</span></span>  
  
 <span data-ttu-id="97e35-108">Para obtener más información acerca de:</span><span class="sxs-lookup"><span data-stu-id="97e35-108">For more information about:</span></span>  
  
- <span data-ttu-id="97e35-109">Mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con BizTalk Server para invocar funciones con valores de tabla en SQL Server, vea [Invoking Table-Valued funciones en SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="97e35-109">Using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with BizTalk Server to invoke table valued functions in SQL Server, see [Invoking Table-Valued Functions in SQL Server by Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="97e35-110">Mensaje de la estructura y las acciones de SOAP para las funciones con valores de tabla, vea [esquemas de mensaje para procedimientos y funciones](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md).</span><span class="sxs-lookup"><span data-stu-id="97e35-110">Message structure and SOAP actions for table valued functions, see [Message Schemas for Procedures and Functions](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97e35-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="97e35-111">See Also</span></span>  
 <span data-ttu-id="97e35-112">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="97e35-112">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>