---
title: Configuración del equipo del desarrollador para la solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developer servers
- process management solution tutorial, developer servers
- process management solution tutorial, deploying
ms.assetid: cf975323-53ec-45a8-9f68-80ad423f298b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e2491d755062828a3204d895fa7be7552ef06d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238884"
---
# <a name="developer-machine-setup-for-the-business-process-management-solution"></a><span data-ttu-id="c33e4-102">Configuración del equipo del programador para la solución Administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="c33e4-102">Developer Machine Setup for the Business Process Management Solution</span></span>
<span data-ttu-id="c33e4-103">La solución de administración de procesos empresariales (BPM) muestra una forma de construir un administrador de procesos en una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c33e4-103">The Business Process Management (BPM) solution shows one way to construct a process manager in a BizTalk application.</span></span> <span data-ttu-id="c33e4-104">La solución utiliza un componente para seleccionar y controlar la secuencia de fases en el procesamiento de pedidos.</span><span class="sxs-lookup"><span data-stu-id="c33e4-104">The solution uses a component to select and control the sequence of stages in order processing.</span></span> <span data-ttu-id="c33e4-105">La solución toma un pedido, que puede ser de un nuevo servicio, una actualización o la terminación del servicio, lo registra y lo confirma antes de pasarlo para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="c33e4-105">The solution takes an order—which may be for new service, an upgrade, or termination of service—logs it, and acknowledges the order before passing it on for processing.</span></span> <span data-ttu-id="c33e4-106">El procesamiento consta de uno o más fases de control del pedido.</span><span class="sxs-lookup"><span data-stu-id="c33e4-106">The processing consists of one or more stages that handle the order.</span></span> <span data-ttu-id="c33e4-107">Por último, la solución devuelve una respuesta a la solicitud de pedido original.</span><span class="sxs-lookup"><span data-stu-id="c33e4-107">Finally, the solution returns a response to the original order request.</span></span>  
  
 <span data-ttu-id="c33e4-108">Como programador, primero debe ejecutar el escenario en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="c33e4-108">As a developer, you first get the scenario running on a single computer.</span></span> <span data-ttu-id="c33e4-109">Después de probar las funcionalidades en este equipo, deberá llegar a un acuerdo con los profesionales de TI sobre cómo se va a implementar la solución en los servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="c33e4-109">After testing functionalities on the single computer, you will discuss how to deploy the solution on production servers with IT professionals.</span></span> <span data-ttu-id="c33e4-110">Tiene que ayudarles a diseñar la arquitectura del sistema para satisfacer las necesidades de servicio como una alta disponibilidad, un mayor rendimiento y un mantenimiento más sencillo.</span><span class="sxs-lookup"><span data-stu-id="c33e4-110">You need to help them to design the system architecture to satisfy service requirements such as high availability, better performance, and easier maintenance.</span></span> <span data-ttu-id="c33e4-111">A continuación, deberá preparar los recursos para la implementación de la producción en función del diseño.</span><span class="sxs-lookup"><span data-stu-id="c33e4-111">You will then prepare resources for production deployment based on the design.</span></span>  
  
 <span data-ttu-id="c33e4-112">Esta guía de implementación describe cómo instalar y probar la solución Administración de procesos empresariales en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="c33e4-112">This deployment guide describes how to install and test the business process management solution on a single computer.</span></span>  
  
 <span data-ttu-id="c33e4-113">Para obtener más información acerca de la solución de administración de procesos empresariales, vea [descripción de la solución de administración de procesos empresariales](../core/understanding-the-business-process-management-solution.md).</span><span class="sxs-lookup"><span data-stu-id="c33e4-113">For more information about the business process management solution, see [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c33e4-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c33e4-114">In This Section</span></span>  
  
-   [<span data-ttu-id="c33e4-115">Antes de instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="c33e4-115">Before Installing the Business Process Management Solution</span></span>](../core/before-installing-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="c33e4-116">Cómo instalar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="c33e4-116">How to Install the Business Process Management Solution</span></span>](../core/how-to-install-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="c33e4-117">Cómo ejecutar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="c33e4-117">How to Run the Business Process Management Solution</span></span>](../core/how-to-run-the-business-process-management-solution.md)