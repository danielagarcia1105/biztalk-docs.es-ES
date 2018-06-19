---
title: Sondear el servidor SQL mediante el adaptador de SQL con el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eef2e868-bd51-4393-b091-f67299b4759d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20d0ab576e5feddb0b5f3e867ca549a45bb2af97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222916"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-wcf-service-model"></a><span data-ttu-id="76166-102">Sondear el servidor SQL mediante el adaptador de SQL con el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="76166-102">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>
<span data-ttu-id="76166-103">Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de cambio de datos basado en sondeo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="76166-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive polling-based data-changed messages from SQL Server.</span></span> <span data-ttu-id="76166-104">Puede especificar una instrucción de sondeo que el adaptador se ejecuta para sondear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="76166-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="76166-105">La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="76166-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="76166-106">Según el tipo de mensaje de sondeo recibido, el adaptador expone las operaciones de sondeo diferentes:</span><span class="sxs-lookup"><span data-stu-id="76166-106">Based on the type of polling message received, the adapter exposes different polling operations:</span></span>  
  
-   <span data-ttu-id="76166-107">**Sondeo**.</span><span class="sxs-lookup"><span data-stu-id="76166-107">**Polling**.</span></span> <span data-ttu-id="76166-108">Esta operación devuelve un conjunto de datos como parte del mensaje de sondeo.</span><span class="sxs-lookup"><span data-stu-id="76166-108">This operation returns a data set as part of the polling message.</span></span>  
  
-   <span data-ttu-id="76166-109">**TypedPolling**.</span><span class="sxs-lookup"><span data-stu-id="76166-109">**TypedPolling**.</span></span> <span data-ttu-id="76166-110">Esta operación devuelve un mensaje de sondeo fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="76166-110">This operation returns a strongly-typed polling message.</span></span>  
  
-   <span data-ttu-id="76166-111">**XmlPolling**.</span><span class="sxs-lookup"><span data-stu-id="76166-111">**XmlPolling**.</span></span> <span data-ttu-id="76166-112">Esta operación devuelve el mensaje de sondeo como un mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="76166-112">This operation returns the polling message as an XML message.</span></span> <span data-ttu-id="76166-113">Debe usar esta operación si desea utilizar las instrucciones SELECT o procedimientos almacenados que utilizan la cláusula FOR XML para devolver los datos como mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="76166-113">You must use this operation if you want to use SELECT statements or stored procedures that use the FOR XML clause to return data as XML messages.</span></span> <span data-ttu-id="76166-114">[Cláusula FOR XML](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server) proporciona más información.</span><span class="sxs-lookup"><span data-stu-id="76166-114">[FOR XML clause](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server) provides more info.</span></span> 
  
 <span data-ttu-id="76166-115">Para obtener más información acerca de estas operaciones de sondeo, consulte [sondeo en SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="76166-115">For more information about these polling operations, see [Polling in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76166-116">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes de adaptador tiene una sola aplicación con más de un sondeo o TypedPolling operaciones para la misma base de datos o una tabla.</span><span class="sxs-lookup"><span data-stu-id="76166-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to have a single application with more than one Polling or TypedPolling operations for the same database or table.</span></span> <span data-ttu-id="76166-117">Para admitir este escenario, el adaptador incluye un identificador único, **InboundID**: en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="76166-117">To support such a scenario, the adapter includes a unique ID— **InboundID**—in the connection URI.</span></span> <span data-ttu-id="76166-118">Este Id., cuando se agrega a la conexión URI, hace único, lo que permite varias operaciones de sondeo en una sola aplicación.</span><span class="sxs-lookup"><span data-stu-id="76166-118">This ID, when added to the connection URI, makes it unique, thereby enabling multiple polling operations in a single application.</span></span>  
  
 <span data-ttu-id="76166-119">Los temas de esta sección proporcionan instrucciones sobre cómo usar las operaciones de sondeo y TypedPolling en una aplicación. NET.</span><span class="sxs-lookup"><span data-stu-id="76166-119">The topics in this section provide instructions on how to use both Polling and TypedPolling operations in a .NET application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76166-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="76166-120">In This Section</span></span>  
  
-   [<span data-ttu-id="76166-121">Recibir mensajes de cambio de datos basado en sondeo de SQL Server mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="76166-121">Receive Polling-based Data-changed Messages from SQL Server Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-service.md)  
  
-   [<span data-ttu-id="76166-122">Recibir fuertemente tipado mensajes de cambio de datos basado en sondeo de SQL Server mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="76166-122">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="76166-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="76166-123">See Also</span></span>  
[<span data-ttu-id="76166-124">Desarrollar aplicaciones de SQL con el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="76166-124">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)