---
title: Ejecutar operaciones compuestas en SQL Server mediante el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 906c6352-44f3-4624-9e32-aea3fbb7510d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5acf0eca210bd163c0d74e7d8d873ec6009d40a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999285"
---
# <a name="run-composite-operations-in-sql-server--using-the-sql-adapter"></a><span data-ttu-id="e065d-102">Ejecutar operaciones compuestas en SQL Server mediante el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="e065d-102">Run composite operations in SQL Server  using the SQL adapter</span></span>
<span data-ttu-id="e065d-103">El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] permite a los clientes del adaptador realizar operaciones compuestas en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e065d-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] enables adapter clients to perform composite operations on the SQL Server database.</span></span> <span data-ttu-id="e065d-104">Una operación compuesta puede incluir cualquier número de las siguientes operaciones y en cualquier orden:</span><span class="sxs-lookup"><span data-stu-id="e065d-104">A composite operation can include any number of the following operations, and in any order:</span></span>  
  
- <span data-ttu-id="e065d-105">Las operaciones Insert, Update y Delete en las tablas y vistas.</span><span class="sxs-lookup"><span data-stu-id="e065d-105">The Insert, Update, and Delete operations on the tables and views.</span></span>  
  
- <span data-ttu-id="e065d-106">Procedimientos almacenados que se exponen como operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="e065d-106">Stored procedures that are surfaced as operations in the adapter.</span></span>  
  
  <span data-ttu-id="e065d-107">Las operaciones en una operación compuesta *debe* tablas y vistas solo en una sola base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="e065d-107">The operations in a composite operation *must* target tables and views only in a single database.</span></span>  
  
  <span data-ttu-id="e065d-108">Para obtener información acerca de:</span><span class="sxs-lookup"><span data-stu-id="e065d-108">For information about:</span></span>  
  
- <span data-ttu-id="e065d-109">Cómo realizar operaciones compuestas en [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] utilizando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones compuestas en SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="e065d-109">How to perform composite operations in [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run Composite Operations on SQL Server Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="e065d-110">Los esquemas para la operación compuesta de mensajes, vea [esquemas de mensaje para operaciones compuestas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md).</span><span class="sxs-lookup"><span data-stu-id="e065d-110">Message schemas for the composite operation, see [Message Schemas for Composite Operations](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e065d-111">Si hay "n" número de operaciones en una operación compuesta que devuelven un número de resultados, a continuación, "n + 1" del conjunto de conexiones es necesario para la operación compuesta que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="e065d-111">If there are “n” number of operations in a composite operation that return a result set then “n+1” number of connections are required for the composite operation to be executed.</span></span> <span data-ttu-id="e065d-112">Por lo tanto, debe asegurarse de que el valor especificado para el **MaxConnectionPoolSize** enlaza la propiedad es n + 1 o mayor.</span><span class="sxs-lookup"><span data-stu-id="e065d-112">Therefore, you must ensure that the value specified for the **MaxConnectionPoolSize** binding property is n+1 or greater.</span></span> <span data-ttu-id="e065d-113">Para obtener más información sobre la **MaxConnectionPoolSize** enlaza la propiedad, vea [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e065d-113">For more information about the **MaxConnectionPoolSize** binding property, see [Read about BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e065d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e065d-114">See Also</span></span>  
 <span data-ttu-id="e065d-115">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="e065d-115">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>