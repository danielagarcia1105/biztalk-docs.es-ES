---
title: "Recepción de sondeo el mensajes a través de varios puertos de recepción de SQL con BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21cf4875-1c04-41cf-98f5-d1307987ca55
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be084ca9e0a90813a541563bf6f600ea277aec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk-server"></a><span data-ttu-id="2cea0-102">Recepción de sondeo mensajes a través de varios puertos de recepción de SQL con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2cea0-102">Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server</span></span>
<span data-ttu-id="2cea0-103">Considere un escenario donde desea crear una aplicación de BizTalk que incluye dos operaciones de sondeo.</span><span class="sxs-lookup"><span data-stu-id="2cea0-103">Consider a scenario where you want to create a BizTalk application that includes two polling operations.</span></span> <span data-ttu-id="2cea0-104">Cada operación de sondeo sondea tablas independientes, empleados y clientes, desde la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="2cea0-104">Each polling operation polls separate tables, Employee and Customer, from the same database.</span></span> <span data-ttu-id="2cea0-105">Al implementar este tipo de aplicación en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe crear dos puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="2cea0-105">When you deploy such an application in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you will need to create two receive ports.</span></span> <span data-ttu-id="2cea0-106">El URI de conexión para cada puerto de recepción será:</span><span class="sxs-lookup"><span data-stu-id="2cea0-106">The connection URI for each receive port will be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>  
```  
  
 <span data-ttu-id="2cea0-107">Dado que los procesos de recepción puertos están recibiendo mensajes de sondeo de la misma base de datos en el mismo servidor, el URI de conexión para ambos serán los mismos.</span><span class="sxs-lookup"><span data-stu-id="2cea0-107">Because both receive ports are receiving polling messages from the same database on the same server, the connection URI for both will be the same.</span></span> <span data-ttu-id="2cea0-108">Sin embargo, una aplicación de BizTalk no puede tener dos puertos con el mismo URI de conexión de recepción.</span><span class="sxs-lookup"><span data-stu-id="2cea0-108">However, a BizTalk application cannot have two receive ports with the same connection URI.</span></span>  
  
 <span data-ttu-id="2cea0-109">Para permitir que los clientes de adaptador tiene dos puertos de recepción que sondean la misma base de datos (o incluso la misma tabla en una base de datos) en una aplicación de BizTalk, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] proporciona una propiedad de conexión, **InboundID**.</span><span class="sxs-lookup"><span data-stu-id="2cea0-109">To enable adapter clients to have two receive ports that poll the same database (or even the same table in a database) in a BizTalk application, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] provides a connection property, **InboundID**.</span></span> <span data-ttu-id="2cea0-110">Puede especificar cualquier valor para esta propiedad de conexión.</span><span class="sxs-lookup"><span data-stu-id="2cea0-110">You can specify any value for this connection property.</span></span> <span data-ttu-id="2cea0-111">Al agregar el identificador de entrada, una conexión URI se convierte en único.</span><span class="sxs-lookup"><span data-stu-id="2cea0-111">By adding the inbound ID, a connection URI becomes unique.</span></span> <span data-ttu-id="2cea0-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2cea0-112">For example:</span></span>  
  
 <span data-ttu-id="2cea0-113">El URI de conexión para el puerto de recepción de mensajes de sondeo de la tabla de empleados puede ser:</span><span class="sxs-lookup"><span data-stu-id="2cea0-113">The connection URI for the port receiving polling messages for the Employee table can be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Employee  
```  
  
 <span data-ttu-id="2cea0-114">De forma similar, puede ser el URI de conexión para el puerto de recepción de mensajes de sondeo para la tabla Customer:</span><span class="sxs-lookup"><span data-stu-id="2cea0-114">Similarly, the connection URI for the port receiving polling messages for the Customer table can be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Customer  
```  
  
 <span data-ttu-id="2cea0-115">Dado que el URI de conexión se convierten en únicos agregando el **InboundID** propiedad, ahora puede tener varios sondear la misma base de datos o tabla en una sola aplicación de BizTalk de puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="2cea0-115">Because the connection URIs become unique by adding the **InboundID** property, you can now have multiple receive ports polling the same database or table in a single BizTalk application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2cea0-116">Puede especificar el **InboundID** propiedad de conexión tanto para el **sondeo** y **TypedPolling** operaciones.</span><span class="sxs-lookup"><span data-stu-id="2cea0-116">You can choose to specify the **InboundID** connection property for both the **Polling** and **TypedPolling** operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cea0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cea0-117">See Also</span></span>  
 [<span data-ttu-id="2cea0-118">Sondear el servidor de SQL con el adaptador de SQL BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2cea0-118">Poll SQL Server using the SQL Adapter with BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)