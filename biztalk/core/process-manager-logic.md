---
title: "Administrador de procesos lógica | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: 6b69fc71-0f01-4513-9361-d7787d0cde6d
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e562362fec8e13589f1860e74024ffe70dad1c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="process-manager-logic"></a><span data-ttu-id="5b3dd-102">Lógica del Administrador de procesos</span><span class="sxs-lookup"><span data-stu-id="5b3dd-102">Process Manager Logic</span></span>
<span data-ttu-id="5b3dd-103">Esta sección se describe cómo el Administrador de procesos, el **OrderManager** orquestación, procesa pedidos.</span><span class="sxs-lookup"><span data-stu-id="5b3dd-103">This section describes how the process manager, the **OrderManager** orchestration, processes orders.</span></span> <span data-ttu-id="5b3dd-104">Describe campos fundamentales en los distintos mensajes de pedido y realiza un seguimiento de los pedidos nuevos y actualizados a través de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="5b3dd-104">It describes key fields in the various order messages and follows new and updated orders through the orchestration.</span></span>  
  
 <span data-ttu-id="5b3dd-105">El **OrderManager** orquestación coordina orquestaciones subordinadas para procesar el pedido.</span><span class="sxs-lookup"><span data-stu-id="5b3dd-105">The **OrderManager** orchestration coordinates subordinate orchestrations to process the order.</span></span> <span data-ttu-id="5b3dd-106">Puede agregar, eliminar o modificar estas fases sin tener que cambiar la **OrderManager**.</span><span class="sxs-lookup"><span data-stu-id="5b3dd-106">You can add, delete, or modify these stages without having to change the **OrderManager**.</span></span> <span data-ttu-id="5b3dd-107">El **OrderManager** realiza gran parte de la coordinación mediante mensajes personalizados definidos por las clases. NET.</span><span class="sxs-lookup"><span data-stu-id="5b3dd-107">The **OrderManager** does much of the coordination through custom messages defined by .NET classes.</span></span> <span data-ttu-id="5b3dd-108">Para obtener una lista de todos los mensajes en la solución, vea [referencia de mensaje para la solución de administración de procesos empresariales](../core/message-reference-for-the-business-process-management-solution.md).</span><span class="sxs-lookup"><span data-stu-id="5b3dd-108">For a list of all messages in the solution, see [Message Reference for the Business Process Management Solution](../core/message-reference-for-the-business-process-management-solution.md).</span></span> <span data-ttu-id="5b3dd-109">Para obtener información acerca de cómo definir tipos de mensajes con las clases. NET, vea [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).</span><span class="sxs-lookup"><span data-stu-id="5b3dd-109">For information about defining message types with .NET classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b3dd-110">Debido al tamaño y ámbito de **OrderManager**, puede que desee leer estas secciones, especialmente la segunda, con la orquestación abierta en Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5b3dd-110">Because of the size and scope of **OrderManager**, you may want to read these sections, especially the second, with the orchestration open in Microsoft Visual Studio.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b3dd-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5b3dd-111">In This Section</span></span>  
  
-   [<span data-ttu-id="5b3dd-112">Campos y los mensajes de teclado</span><span class="sxs-lookup"><span data-stu-id="5b3dd-112">Key Messages and Fields</span></span>](../core/key-messages-and-fields.md)  
  
-   [<span data-ttu-id="5b3dd-113">Flujo de pedidos a través del Administrador de proceso</span><span class="sxs-lookup"><span data-stu-id="5b3dd-113">Order Flow through the Process Manager</span></span>](../core/order-flow-through-the-process-manager.md)