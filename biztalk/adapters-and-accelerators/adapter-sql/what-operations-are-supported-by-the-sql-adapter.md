---
title: Las operaciones que son compatibles con el adaptador de SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b8f4099-df19-48c4-a135-1ec264af3513
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59d413a763823f49b0bf905b42d8513cbbb1e745
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-sql-adapter"></a><span data-ttu-id="670da-102">Las operaciones que son compatibles con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="670da-102">What operations are supported by the SQL adapter</span></span>
<span data-ttu-id="670da-103">Puede usar a los clientes de adaptador para realizar operaciones en la base de datos de SQL Server mediante:</span><span class="sxs-lookup"><span data-stu-id="670da-103">You can use the adapter clients to perform operations on the SQL Server database by:</span></span>  
  
-   <span data-ttu-id="670da-104">Crear proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="670da-104">Creating BizTalk projects</span></span>  
  
-   <span data-ttu-id="670da-105">Mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="670da-105">Using the WCF service model</span></span>  
  
-   <span data-ttu-id="670da-106">Mediante el modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="670da-106">Using the WCF channel model</span></span>  
  
 <span data-ttu-id="670da-107">La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="670da-107">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="670da-108">Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="670da-108">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="670da-109">Si es necesario recibir una respuesta, se devuelve en un mensaje SOAP en el mismo canal.</span><span class="sxs-lookup"><span data-stu-id="670da-109">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="670da-110">Para obtener información sobre la estructura del mensaje y la acción de SOAP asociada a cada operación, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="670da-110">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>  
  
 <span data-ttu-id="670da-111">Esta sección proporciona información acerca de las operaciones admitidas en la base de datos de SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="670da-111">This section provides information about the operations supported on the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="670da-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="670da-112">See Also</span></span>  
 [<span data-ttu-id="670da-113">Información general sobre el adaptador de BizTalk para SQL Server</span><span class="sxs-lookup"><span data-stu-id="670da-113">Overview of BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)