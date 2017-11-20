---
title: "Implementar el servicio solución orientada a servicios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, service solution tutorial
- deploying, tutorials
- service solution tutorial, deploying
- service solution tutorial, background information
- tutorials, deploying
ms.assetid: 88d4d28d-9031-4fb8-ab62-04ee27949673
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7246635c4e0d55fd424fd0052eee91e118c8cb17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-the-service-oriented-solution"></a><span data-ttu-id="835cc-102">Implementar el servicio solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="835cc-102">Deploying the Service Oriented Solution</span></span>
<span data-ttu-id="835cc-103">La arquitectura orientada a servicios (SOA) es un enfoque para la generación de sistemas distribuidos.</span><span class="sxs-lookup"><span data-stu-id="835cc-103">Service Oriented Architecture (SOA) is an approach to building distributed systems.</span></span> <span data-ttu-id="835cc-104">La solución orientada a servicios demuestra cómo varios sistemas servidor con protocolos distintos se pueden integrar en un único servicio que pueden consumir los clientes.</span><span class="sxs-lookup"><span data-stu-id="835cc-104">The service oriented solution demonstrates how several back-end systems using different protocols can be aggregated into a single service that clients can consume.</span></span> <span data-ttu-id="835cc-105">Esta solución integra servicios con un enfoque que garantiza las características de entrega y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="835cc-105">This solution integrates services with an approach that guarantees delivery and performance characteristics.</span></span>  
  
 <span data-ttu-id="835cc-106">La solución orientada a servicios basa su modelo en un escenario de contrato de nivel de servicio en el que BizTalk Server y los servidores de la aplicación de la unidad de negocio conectados a éste disponen de tres segundos para responder a una solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="835cc-106">The service oriented solution is modeled after a service-level agreement scenario in which BizTalk Server and the Line of Business (LOB) application servers connected to it are given three seconds to respond with a service request.</span></span> <span data-ttu-id="835cc-107">Uno de estos tres segundos puede ser utilizado por el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="835cc-107">One of those three seconds may be taken up by the BizTalk Server.</span></span>  
  
 <span data-ttu-id="835cc-108">Los temas incluidos en esta sección explican cómo instalar y probar la solución orientada a servicios en un solo equipo y en varios servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="835cc-108">The topics in this section describe how to install and test the service oriented solution on a single computer and multiple production servers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="835cc-109">Hay tres versiones de la solución orientada a servicios: adaptador, en línea y el código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="835cc-109">There are three versions of the service oriented solution: adapter, inline, and stub.</span></span> <span data-ttu-id="835cc-110">Para obtener más información acerca de las diferencias entre las tres versiones de la solución orientada a servicios, vea [descripción de la solución orientada a servicios](../core/understanding-the-service-oriented-solution.md).</span><span class="sxs-lookup"><span data-stu-id="835cc-110">For more information about the differences between three versions of the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="835cc-111">**Instrucciones para el lector**</span><span class="sxs-lookup"><span data-stu-id="835cc-111">**Reader Guidance**</span></span>  
  
 <span data-ttu-id="835cc-112">En este documento se supone que el usuario ya conoce BizTalk Server, Windows Server y Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="835cc-112">This document assumes that you are familiar with BizTalk Server, Windows Server, and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="835cc-113">También supone que comprende conceptos básicos acerca de la integración de aplicaciones de negocio y servicios Web.</span><span class="sxs-lookup"><span data-stu-id="835cc-113">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span> <span data-ttu-id="835cc-114">Además, recomendamos que esté familiarizado con la generación de aplicaciones mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] así como con la creación de proyectos, establecimiento de referencias y utilización del modo de depuración para depurar y probar su solución.</span><span class="sxs-lookup"><span data-stu-id="835cc-114">Additionally, we recommend that you are familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and that you are familiar with creating projects, setting references, and using the debug mode to debug and test your solution.</span></span> <span data-ttu-id="835cc-115">Para obtener más información acerca de los requisitos previos conocimientos y para profesionales de TI y desarrolladores, consulte [Prerequisite conocimientos y](../core/prerequisite-skills-and-knowledge5.md).</span><span class="sxs-lookup"><span data-stu-id="835cc-115">For more information about the prerequisite skills and knowledge for IT professionals and developers, see [Prerequisite Skills and Knowledge](../core/prerequisite-skills-and-knowledge5.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="835cc-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="835cc-116">In This Section</span></span>  
  
-   [<span data-ttu-id="835cc-117">Solución orientada a servicios de configuración del equipo del desarrollador para el servicio</span><span class="sxs-lookup"><span data-stu-id="835cc-117">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)