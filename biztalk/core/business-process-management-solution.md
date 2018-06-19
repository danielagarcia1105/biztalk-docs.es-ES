---
title: Solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business solutions, tutorials
- tutorials, orchestrations
- errors, tutorials
- business solutions, process management solutions
- process management solutions
- process management solutions, applications
- process management solutions, business solutions
- tutorials, applications
- tutorials, errors
- tutorials, process management solutions
- applications, tutorials
- tutorials, business solutions
- process management solutions, tutorials
- orchestrations, interrupting
- orchestrations, tutorials
- applications, process management solutions
ms.assetid: 30ebd248-7e31-4608-ae50-4fc6703ae613
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f37fa7691a3e780c0f972e1070a8bf639c4addcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232100"
---
# <a name="business-process-management-solution"></a><span data-ttu-id="4cf21-102">Solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="4cf21-102">Business Process Management Solution</span></span>
<span data-ttu-id="4cf21-103">La solución Administración de procesos empresariales muestra cómo diseñar una aplicación de BizTalk para administrar un proceso empresarial como, por ejemplo, el procesamiento de pedidos de servicio.</span><span class="sxs-lookup"><span data-stu-id="4cf21-103">The Business Process Management solution shows how to design a BizTalk application to manage a business process such as service order processing.</span></span> <span data-ttu-id="4cf21-104">La solución demuestra cómo construir un administrador de procesos y proporciona instrucciones para dividir un proceso en distintas fases.</span><span class="sxs-lookup"><span data-stu-id="4cf21-104">The solution demonstrates how to construct a process manager and provides guidance about dividing a process into distinct stages.</span></span> <span data-ttu-id="4cf21-105">La solución también describe cómo construir orquestaciones ininterrumpibles así como un control de excepciones amplio y sofisticado.</span><span class="sxs-lookup"><span data-stu-id="4cf21-105">The solution also describes how to construct interruptible orchestrations as well as extensive, sophisticated exception handling.</span></span>  
  
 <span data-ttu-id="4cf21-106">Las secciones proporcionan información general sobre la solución, explicaciones detalladas de los patrones y opciones de diseño, e información sobre la generación y ejecución de la solución.</span><span class="sxs-lookup"><span data-stu-id="4cf21-106">The sections provide an overview of the solution, detailed explanations of the patterns and design choices, and information about building and running the solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cf21-107">Los patrones y las directrices que se documentan en esta sección pretenden ilustrar un enfoque hacia un tipo concreto de solución empresarial.</span><span class="sxs-lookup"><span data-stu-id="4cf21-107">The patterns and guidance documented in these sections are intended to illustrate an approach to a particular kind of business solution.</span></span> <span data-ttu-id="4cf21-108">Los patrones son mecanismos sencillos que se combinan unos con otros y cuya finalidad radica en aplicarse a un problema específico.</span><span class="sxs-lookup"><span data-stu-id="4cf21-108">Patterns are simple mechanisms that are meant to be applied to a specific problem and are usually combined with other patterns.</span></span> <span data-ttu-id="4cf21-109">No están diseñados para incluirse en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4cf21-109">They are not meant to be plugged into an application.</span></span> <span data-ttu-id="4cf21-110">El código de ejemplo se proporciona tal cual y no está orientado a utilizarse en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="4cf21-110">Example code is provided "as is" and is not intended for production use.</span></span> <span data-ttu-id="4cf21-111">Tan sólo pretende ilustrar un patrón y, por tanto, no incluye ningún código adicional, como la validación, la seguridad, el registro y el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="4cf21-111">It is only intended to illustrate the pattern and therefore does not include extra code, such as exception handling, logging, security, and validation.</span></span> <span data-ttu-id="4cf21-112">Microsoft no admite la implementación de códigos de ejemplo tal y como están expresados en las fases de producción.</span><span class="sxs-lookup"><span data-stu-id="4cf21-112">Microsoft does not support deploying the example code "as is" to production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4cf21-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4cf21-113">In This Section</span></span>  
  
-   [<span data-ttu-id="4cf21-114">Descripción de la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="4cf21-114">Understanding the Business Process Management Solution</span></span>](../core/understanding-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="4cf21-115">Desarrollar una solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="4cf21-115">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)  
  
-   [<span data-ttu-id="4cf21-116">Implementar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="4cf21-116">Deploying the Business Process Management Solution</span></span>](../core/deploying-the-business-process-management-solution.md)