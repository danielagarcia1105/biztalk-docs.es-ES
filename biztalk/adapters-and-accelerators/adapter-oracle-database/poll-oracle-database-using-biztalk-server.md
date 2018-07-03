---
title: Sondeo de base de datos de Oracle con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c3aef30-956d-4585-b2de-7eebb919fab5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d819abc957eb46dc430befb01cbcae0b8b55ca48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996101"
---
# <a name="poll-oracle-database-using-biztalk-server"></a><span data-ttu-id="6b023-102">Sondeo de base de datos de Oracle con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6b023-102">Poll Oracle Database using BizTalk Server</span></span>
<span data-ttu-id="6b023-103">Puede configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para recibir mensajes basados en sondeos de base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="6b023-103">You can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive polling-based messages from Oracle database.</span></span> <span data-ttu-id="6b023-104">El adaptador proporciona dos maneras de sondear la base de datos de Oracle:</span><span class="sxs-lookup"><span data-stu-id="6b023-104">The adapter provides two ways of polling the Oracle database:</span></span>  
  
- <span data-ttu-id="6b023-105">**Utilizar las instrucciones SELECT**.</span><span class="sxs-lookup"><span data-stu-id="6b023-105">**Using SELECT statements**.</span></span> <span data-ttu-id="6b023-106">Puede especificar una instrucción SELECT simple para sondear las tablas y vistas de la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="6b023-106">You can specify a simple SELECT statement to poll the tables and views in the Oracle database.</span></span> <span data-ttu-id="6b023-107">El adaptador ejecuta la instrucción SELECT a intervalos especificados y devuelve el resultado a los clientes del adaptador.</span><span class="sxs-lookup"><span data-stu-id="6b023-107">The adapter executes the SELECT statement at specified intervals and returns the result to the adapter clients.</span></span>  
  
- <span data-ttu-id="6b023-108">**Mediante procedimientos almacenados, funciones, procedimientos o funciones dentro de un paquete**.</span><span class="sxs-lookup"><span data-stu-id="6b023-108">**Using stored procedures, functions, or procedures or functions within a package**.</span></span> <span data-ttu-id="6b023-109">Puede especificar un procedimiento almacenado, función o procedimiento o función dentro de un paquete para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="6b023-109">You can specify a stored procedure, function, or procedure or function within a package to poll the Oracle database.</span></span> <span data-ttu-id="6b023-110">El adaptador el mensaje de solicitud ejecuta a intervalos especificados y devuelve el resultado a los clientes del adaptador.</span><span class="sxs-lookup"><span data-stu-id="6b023-110">The adapter executes the request message at specified intervals and returns the result to the adapter clients.</span></span>  
  
  <span data-ttu-id="6b023-111">La diferencia clave en los dos enfoques es que los clientes del adaptador de manera especifican una instrucción de sondeo que utiliza el adaptador para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="6b023-111">The key difference in the two approaches is the way adapter clients specify a polling statement that the adapter uses to poll the Oracle database.</span></span> <span data-ttu-id="6b023-112">Aunque la instrucción de sondeo para el primer enfoque es una instrucción SELECT simple, la instrucción de sondeo para el otro enfoque es un mensaje de solicitud que se ejecuta el procedimiento almacenado, función o procedimiento o función dentro de un paquete.</span><span class="sxs-lookup"><span data-stu-id="6b023-112">While the polling statement for the first approach is a simple SELECT statement, the polling statement for the other approach is a request message that executes the stored procedure, function, or procedure or function within a package.</span></span> <span data-ttu-id="6b023-113">Los clientes del adaptador especifican la instrucción de sondeo para cualquier enfoque, en el **PollingStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6b023-113">Adapter clients specify the polling statement, for either approach, in the **PollingStatement** binding property.</span></span> <span data-ttu-id="6b023-114">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6b023-114">For more information about the binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
  <span data-ttu-id="6b023-115">Los temas de esta sección proporcionan instrucciones sobre cómo sondear con una instrucción SELECT y un procedimiento almacenado, función o procedimiento o función dentro de un paquete.</span><span class="sxs-lookup"><span data-stu-id="6b023-115">The topics in this section provide instructions on how to poll using a SELECT statement and a stored procedure, function, or procedure or function within a package.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b023-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6b023-116">In This Section</span></span>  
  
-   [<span data-ttu-id="6b023-117">Sondeo de base de datos de Oracle mediante la instrucción SELECT</span><span class="sxs-lookup"><span data-stu-id="6b023-117">Poll Oracle Database using the SELECT statement</span></span>](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-the-select-statement.md)  
  
-   [<span data-ttu-id="6b023-118">Sondeo de base de datos de Oracle mediante procedimientos almacenados, funciones, o empaquetados procedimientos y funciones</span><span class="sxs-lookup"><span data-stu-id="6b023-118">Poll Oracle Database Using Stored Procedures, Functions, or Packaged Procedures and Functions</span></span>](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-db-using-stored-procedures-functions-or-packaged-procedures.md)  
  
## <a name="see-also"></a><span data-ttu-id="6b023-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b023-119">See Also</span></span>  
[<span data-ttu-id="6b023-120">Desarrollar aplicaciones de BizTalk con el adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="6b023-120">Develop BizTalk applications using the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)