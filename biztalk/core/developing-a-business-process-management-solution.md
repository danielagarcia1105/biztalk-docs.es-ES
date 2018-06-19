---
title: Desarrollar una solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, process management solution tutorial
- process management solution tutorial, developing
ms.assetid: 3b590533-2b18-4e78-b9e5-88f4a680532f
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60632efe6cfc8d48d395d20949012354874c7e46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239644"
---
# <a name="developing-a-business-process-management-solution"></a><span data-ttu-id="b8f46-102">Desarrollar una solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="b8f46-102">Developing a Business Process Management Solution</span></span>
<span data-ttu-id="b8f46-103">En esta sección se describen los modelos básicos relacionados con el diseño de la solución y cómo estos modelos se traducen en componentes y estructuras de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b8f46-103">This section describes the basic patterns involved in the design of the solution and how those patterns translate into BizTalk components and structures.</span></span> <span data-ttu-id="b8f46-104">También sigue un mensaje de pedido mediante el procesamiento en la solución, proporciona detalles adicionales sobre la implementación, le indica cómo realizar versiones de la solución y cómo escalarla y ofrece referencias de mensajes y archivos.</span><span class="sxs-lookup"><span data-stu-id="b8f46-104">It also follows an order message through processing in the solution, provides additional implementation details, tells you how to version and scale the solution, and provides message and file references.</span></span> <span data-ttu-id="b8f46-105">Para obtener más información acerca de la solución y los requisitos empresariales tras su diseño, vea "Requisitos empresariales" en [descripción de la solución de administración de procesos empresariales](../core/understanding-the-business-process-management-solution.md).</span><span class="sxs-lookup"><span data-stu-id="b8f46-105">For more information about the solution and the business requirements behind its design, see "Business Requirements" in [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b8f46-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b8f46-106">In This Section</span></span>  
  
-   [<span data-ttu-id="b8f46-107">Patrones de la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="b8f46-107">Patterns in the Business Process Management Solution</span></span>](../core/patterns-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="b8f46-108">Componentes de la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="b8f46-108">Components of the Business Process Management Solution</span></span>](../core/components-of-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="b8f46-109">Procesamiento en la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="b8f46-109">Processing in the Business Process Management Solution</span></span>](../core/processing-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="b8f46-110">Aspectos destacados de la implementación de la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="b8f46-110">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="b8f46-111">Supervisión de la solución de administración de procesos empresariales con BAM</span><span class="sxs-lookup"><span data-stu-id="b8f46-111">Monitoring the Business Process Management Solution with BAM</span></span>](../core/monitoring-the-business-process-management-solution-with-bam.md)  
  
-   [<span data-ttu-id="b8f46-112">Control de versiones de la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="b8f46-112">Versioning the Business Process Management Solution</span></span>](../core/versioning-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="b8f46-113">Referencia de solución de administración de proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="b8f46-113">Business Process Management Solution Reference</span></span>](../core/business-process-management-solution-reference.md)