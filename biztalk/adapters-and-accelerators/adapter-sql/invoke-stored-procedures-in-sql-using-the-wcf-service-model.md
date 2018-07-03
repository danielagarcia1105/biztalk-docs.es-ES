---
title: Invocar procedimientos almacenados en SQL mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd2fac-0b54-4406-932e-e3044a66b2e6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05ce43db33101dfc3849743e8480e66a8fd76f53
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023298"
---
# <a name="invoke-stored-procedures-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="d5e05-102">Invocar procedimientos almacenados en SQL mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="d5e05-102">Invoke Stored Procedures in SQL using the WCF Service Model</span></span>
<span data-ttu-id="d5e05-103">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] detecta los procedimientos almacenados como operaciones que los clientes del adaptador pueden invocar en el cliente WCF para invocar el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="d5e05-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers the stored procedures as operations that the adapter clients can invoke on the WCF client to invoke the stored procedure.</span></span> <span data-ttu-id="d5e05-104">Según cómo el procedimiento almacenado devuelve el conjunto de resultados, el adaptador clasifica todos los procedimientos almacenados como:</span><span class="sxs-lookup"><span data-stu-id="d5e05-104">Based on how the stored procedure returns the result set, the adapter categorizes all the stored procedures as:</span></span>  
  
- <span data-ttu-id="d5e05-105">**Procedimientos**.</span><span class="sxs-lookup"><span data-stu-id="d5e05-105">**Procedures**.</span></span> <span data-ttu-id="d5e05-106">Invocar procedimientos almacenados desde el **procedimientos** nodo devuelve una matriz de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="d5e05-106">Invoking stored procedures from the **Procedures** node returns an array of DataSet.</span></span>  
  
- <span data-ttu-id="d5e05-107">**Fuertemente tipado procedimientos**.</span><span class="sxs-lookup"><span data-stu-id="d5e05-107">**Strongly-Typed Procedures**.</span></span> <span data-ttu-id="d5e05-108">Invocar procedimientos almacenados desde el **Strongly-Typed procedimientos** nodo devuelve un conjunto de resultados fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="d5e05-108">Invoking stored procedures from the **Strongly-Typed Procedures** node returns a strongly-typed result set.</span></span>  
  
  <span data-ttu-id="d5e05-109">Tenga en cuenta que será el mismo conjunto de procedimientos almacenados en la base de datos que conectado aparece bajo el **procedimientos** y **Strongly-Typed procedimientos** nodo.</span><span class="sxs-lookup"><span data-stu-id="d5e05-109">Note that the same set of stored procedures in the database you connected to will be listed both under the **Procedures** and **Strongly-Typed Procedures** node.</span></span> <span data-ttu-id="d5e05-110">Según el tipo de conjunto de resultados que desee, debe invocar el procedimiento almacenado desde el nodo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d5e05-110">Based on the kind of result set you want, you must invoke the stored procedure from the relevant node.</span></span> <span data-ttu-id="d5e05-111">Para obtener más información acerca de cómo los [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite procedimientos almacenados, vea [ejecutar procedimientos almacenados en SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="d5e05-111">For more information about how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports stored procedures, see [Execute Stored Procedures in SQL Server using BizTalk Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md).</span></span>  
  
  <span data-ttu-id="d5e05-112">Esta sección proporciona instrucciones sobre cómo invocar procedimientos almacenados desde el **procedimientos** y **Strongly-Typed procedimientos** nodo mediante un cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="d5e05-112">This section provides instructions on how to invoke stored procedures from both the **Procedures** and **Strongly-Typed Procedures** node by using a WCF client.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5e05-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d5e05-113">In This Section</span></span>  
  
-   [<span data-ttu-id="d5e05-114">Involk débilmente tipada los procedimientos almacenados de SQL mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="d5e05-114">Involk Weakly-typed Stored Procedures in SQL Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [<span data-ttu-id="d5e05-115">Invocación del procedimiento almacenado fuertemente tipado en SQL mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="d5e05-115">Invoke Strongly-typed Stored Procedure in SQL Using WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="d5e05-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5e05-116">See Also</span></span>  
[<span data-ttu-id="d5e05-117">Desarrollar aplicaciones con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="d5e05-117">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)