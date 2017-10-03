---
title: "Implementar la solución de administración de procesos empresariales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, process management solution tutorial
- process management solution tutorial, deploying
ms.assetid: e033e0cd-0333-4f16-a4a0-eaae9ce98fcc
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0a61048ecb90876b251657f00361c35587a7ec1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-the-business-process-management-solution"></a><span data-ttu-id="a1d80-102">Implementar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="a1d80-102">Deploying the Business Process Management Solution</span></span>
<span data-ttu-id="a1d80-103">La solución de administración de procesos empresariales (BPM) muestra una forma de construir un administrador de procesos en una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a1d80-103">The Business Process Management (BPM) solution shows one way to construct a process manager in a BizTalk application.</span></span> <span data-ttu-id="a1d80-104">La solución utiliza un componente para seleccionar y controlar la secuencia de fases en el procesamiento de pedidos.</span><span class="sxs-lookup"><span data-stu-id="a1d80-104">The solution uses a component to select and control the sequence of stages in order processing.</span></span> <span data-ttu-id="a1d80-105">La solución toma un pedido, que puede ser de un nuevo servicio, una actualización o la terminación del servicio, lo registra y lo confirma antes de pasarlo para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a1d80-105">The solution takes an order—which may be for a new service, an upgrade, or termination of service—logs it, and acknowledges the order before passing it on for processing.</span></span> <span data-ttu-id="a1d80-106">El procesamiento consta de uno o más fases de control del pedido.</span><span class="sxs-lookup"><span data-stu-id="a1d80-106">The processing consists of one or more stages that handle the order.</span></span> <span data-ttu-id="a1d80-107">Por último, la solución devuelve una respuesta a la solicitud de pedido original.</span><span class="sxs-lookup"><span data-stu-id="a1d80-107">Finally, the solution returns a response to the original order request.</span></span>  
  
 <span data-ttu-id="a1d80-108">Esta guía de implementación describe cómo instalar y ejecutar la solución de administración de procesos empresariales en un equipo de desarrollo y varios servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="a1d80-108">This deployment guide describes how to install and run the business process management solution on a development computer and multiple production servers.</span></span>  
  
 <span data-ttu-id="a1d80-109">Para obtener más información acerca de la solución de administración de procesos empresariales, vea [descripción de la solución de administración de procesos empresariales](../core/understanding-the-business-process-management-solution.md).</span><span class="sxs-lookup"><span data-stu-id="a1d80-109">For more information about the business process management solution, see [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="a1d80-110">**Instrucciones para el lector**</span><span class="sxs-lookup"><span data-stu-id="a1d80-110">**Reader Guidance**</span></span>  
  
 <span data-ttu-id="a1d80-111">En este documento se supone que el usuario ya conoce BizTalk Server, Windows Server y Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1d80-111">This document assumes that you are familiar with BizTalk Server, Windows Server, and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="a1d80-112">También supone que comprende conceptos básicos acerca de la integración de aplicaciones de negocio y servicios Web.</span><span class="sxs-lookup"><span data-stu-id="a1d80-112">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span> <span data-ttu-id="a1d80-113">Además, recomendamos que esté familiarizado con la generación de aplicaciones mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] así como con la creación de proyectos, establecimiento de referencias y utilización del modo de depuración para depurar y probar su solución.</span><span class="sxs-lookup"><span data-stu-id="a1d80-113">Additionally, we recommend that you are familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and that you are familiar with creating projects, setting references, and using the debug mode to debug and test your solution.</span></span> <span data-ttu-id="a1d80-114">Para obtener más información acerca de los requisitos previos conocimientos y para profesionales de TI y desarrolladores, consulte [Prerequisite conocimientos y](../core/prerequisite-skills-and-knowledge5.md).</span><span class="sxs-lookup"><span data-stu-id="a1d80-114">For more information about the prerequisite skills and knowledge for IT professionals and developers, see [Prerequisite Skills and Knowledge](../core/prerequisite-skills-and-knowledge5.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1d80-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a1d80-115">In This Section</span></span>  
  
-   [<span data-ttu-id="a1d80-116">Configuración del equipo del desarrollador para la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="a1d80-116">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)