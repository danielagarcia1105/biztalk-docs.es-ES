---
title: Ejecutar operaciones compuestas en base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b877d8e3-2016-40e8-888f-6b768021d6b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd5595823fab4f25948e3d88db759ae525f62130
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215124"
---
# <a name="run-composite-operations-in-oracle-database"></a><span data-ttu-id="541a6-102">Ejecutar operaciones compuestas en base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="541a6-102">Run Composite Operations in Oracle Database</span></span>
<span data-ttu-id="541a6-103">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite a los clientes de adaptador realizar operaciones compuestas que pueden incluir cualquier número de las siguientes operaciones y en cualquier orden:</span><span class="sxs-lookup"><span data-stu-id="541a6-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enables adapter clients to perform composite operations that can include any number of the following operations, and in any order:</span></span>  
  
-   <span data-ttu-id="541a6-104">SELECT, Insert, Update y Delete operaciones en tablas y vistas.</span><span class="sxs-lookup"><span data-stu-id="541a6-104">Select, Insert, Update, and Delete operations on tables and views.</span></span>  
  
-   <span data-ttu-id="541a6-105">Procedimientos almacenados, funciones, procedimientos o funciones de los paquetes que aparecen como operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="541a6-105">Stored procedures, functions, and procedures or functions within packages that are surfaced as operations in the adapter.</span></span>  
  
 <span data-ttu-id="541a6-106">Las operaciones en una operación compuesta pueden tener como destino tablas y vistas de la misma base de datos o bases de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="541a6-106">The operations in a composite operation can target tables and views in the same database or different databases.</span></span> <span data-ttu-id="541a6-107">Sin embargo, los datos no se comparten o volver a usar en operaciones diferentes en una operación compuesta.</span><span class="sxs-lookup"><span data-stu-id="541a6-107">However, data cannot be shared or reused across different operations in a composite operation.</span></span> <span data-ttu-id="541a6-108">Por ejemplo, en una operación compuesta, el conjunto de resultados de una operación de selección no puede utilizarse como parámetro de entrada para un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="541a6-108">For example, in a composite operation, the result set of a Select operation cannot be used as the input parameter for a stored procedure.</span></span>  
  
 <span data-ttu-id="541a6-109">Cada operación en una operación compuesta se realiza mediante una conexión independiente.</span><span class="sxs-lookup"><span data-stu-id="541a6-109">Each operation in a composite operation is performed using a separate connection.</span></span> <span data-ttu-id="541a6-110">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consume tantas conexiones de la agrupación de conexiones ODP.NET como el número de operaciones en una operación compuesta y, a continuación, libera las conexiones que se ejecutan las operaciones.</span><span class="sxs-lookup"><span data-stu-id="541a6-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consumes as many connections from the ODP.NET connection pool as the number of operations in a composite operation, and then releases the connections as the operations get executed.</span></span> <span data-ttu-id="541a6-111">Sin embargo, si una operación en la operación compuesta devuelve un conjunto de resultados, se libera la conexión solo después de que se consume el mensaje.</span><span class="sxs-lookup"><span data-stu-id="541a6-111">However, if an operation in the composite operation returns a result set, the connection is released only after the message is consumed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="541a6-112">Si tiene problemas de tiempo de espera mientras se ejecuta una operación compuesta, a continuación, podría deberse a que el número de conexiones es menor que el número de operaciones en una operación compuesta que implican:</span><span class="sxs-lookup"><span data-stu-id="541a6-112">If you experience time-out issues while executing a composite operation then it could be because the number of connections is less than the number of operations in a composite operation involving:</span></span>  
>   
>  -   <span data-ttu-id="541a6-113">Procedimientos almacenados que contengan BFILE, BLOB, CLOB, NCLOB y REF CURSOR como OUT o IN a parámetros.</span><span class="sxs-lookup"><span data-stu-id="541a6-113">Stored procedures containing BFILE, BLOB, CLOB, NCLOB, and REF CURSOR as OUT or IN OUT parameters.</span></span>  
> -   <span data-ttu-id="541a6-114">Seleccione la operación.</span><span class="sxs-lookup"><span data-stu-id="541a6-114">Select operation.</span></span>  
>   
>  <span data-ttu-id="541a6-115">Para resolver este problema, debe asegurarse de que si hay "n" número de tales operaciones en una operación compuesta, el valor especificado para la **MinPoolSize** enlaza la propiedad es "n + 1" o superior.</span><span class="sxs-lookup"><span data-stu-id="541a6-115">To resolve this issue, you must ensure that if there are “n” number of such operations in a composite operation, the value specified for the **MinPoolSize** binding property is “n+1” or greater.</span></span> <span data-ttu-id="541a6-116">Para obtener más información sobre la **MinPoolSize** enlace de propiedad, vea [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="541a6-116">For more information about the **MinPoolSize** binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="541a6-117">Para obtener información acerca de:</span><span class="sxs-lookup"><span data-stu-id="541a6-117">For information about:</span></span>  
  
-   <span data-ttu-id="541a6-118">Cómo realizar operaciones compuestas en [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones compuestas en la base de datos Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="541a6-118">How to perform composite operations in [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run Composite Operations on Oracle Database by Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="541a6-119">Esquemas para la operación compuesta de mensajes, vea [esquemas de mensaje para la operación compuesta](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md).</span><span class="sxs-lookup"><span data-stu-id="541a6-119">Message schemas for the composite operation, see [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="541a6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="541a6-120">See Also</span></span>  
 <span data-ttu-id="541a6-121">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="541a6-121">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>