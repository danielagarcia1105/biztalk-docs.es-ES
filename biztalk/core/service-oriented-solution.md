---
title: Solución orientada a servicios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solutions
- tutorials, legacy applications
- business solutions, back-end systems
- service solution tutorial
- tutorials, services
- Web services, tutorials
- Web services, business solutions
- tutorials, applications
- applications, tutorials
- applications, services
- legacy applications, tutorials
- service solutions, business solutions
- tutorials, Web services
- tutorials, service solutions
- business solutions, totorials
- business solutions, legacy applications
- back-end systems
- tutorials, business solutions
- legacy applications, business solutions
- business solutions, Web services
- business solutions, service solutions
ms.assetid: ce7cdf8d-ecaf-4a6a-9536-a9cf5d7f874f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a1c69d537469cc1c2a4d9d93cde37014b31daa8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271372"
---
# <a name="service-oriented-solution"></a><span data-ttu-id="ab700-102">Solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="ab700-102">Service Oriented Solution</span></span>
<span data-ttu-id="ab700-103">La solución orientada a servicios muestra cómo presentar una aplicación de BizTalk como un servicio que esté disponible como un servicio Web y en formularios a los que puedan tener acceso aplicaciones heredadas.</span><span class="sxs-lookup"><span data-stu-id="ab700-103">The service oriented solution shows how to present a BizTalk application as a service that is available as a Web service and in forms accessible to legacy applications.</span></span> <span data-ttu-id="ab700-104">La solución también demuestra cómo comunicarse con procesos de servidor como servicios Web, además de cómo agregar respuestas de varios sistemas de servidor.</span><span class="sxs-lookup"><span data-stu-id="ab700-104">The solution also shows how to communicate with back-end processes as Web services, as well as how to aggregate responses from multiple back-end systems.</span></span>  
  
 <span data-ttu-id="ab700-105">Las secciones proporcionan información general sobre la solución, explicaciones detalladas de los patrones y opciones de diseño, e información sobre la generación y ejecución de la solución.</span><span class="sxs-lookup"><span data-stu-id="ab700-105">The sections provide an overview of the solution, detailed explanations of the patterns and design choices, and information about building and running the solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab700-106">Los patrones y las directrices que se documentan en esta sección pretenden ilustrar un enfoque hacia un tipo concreto de solución empresarial.</span><span class="sxs-lookup"><span data-stu-id="ab700-106">The patterns and guidance documented in these sections are intended to illustrate an approach to a particular kind of business solution.</span></span> <span data-ttu-id="ab700-107">Los patrones son mecanismos sencillos que se combinan unos con otros y cuya finalidad radica en aplicarse a un problema específico.</span><span class="sxs-lookup"><span data-stu-id="ab700-107">Patterns are simple mechanisms that are meant to be applied to a specific problem and are usually combined with other patterns.</span></span> <span data-ttu-id="ab700-108">No están diseñados para incluirse en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="ab700-108">They are not meant to be plugged into an application.</span></span> <span data-ttu-id="ab700-109">El código de ejemplo se proporciona tal cual y no está orientado a utilizarse en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="ab700-109">Example code is provided "as is" and is not intended for production use.</span></span> <span data-ttu-id="ab700-110">Tan sólo pretende ilustrar un patrón y, por tanto, no incluye ningún código adicional, como la validación, la seguridad, el registro y el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ab700-110">It is only intended to illustrate the pattern and therefore does not include extra code, such as exception handling, logging, security, and validation.</span></span> <span data-ttu-id="ab700-111">Microsoft no admite la implementación de códigos de ejemplo tal y como están expresados en las fases de producción.</span><span class="sxs-lookup"><span data-stu-id="ab700-111">Microsoft does not support deploying the example code "as is" to production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab700-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ab700-112">In This Section</span></span>  
  
-   [<span data-ttu-id="ab700-113">Descripción del servicio de solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="ab700-113">Understanding the Service Oriented Solution</span></span>](../core/understanding-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="ab700-114">Desarrollar un servicio en la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="ab700-114">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)  
  
-   [<span data-ttu-id="ab700-115">Implementar el servicio solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="ab700-115">Deploying the Service Oriented Solution</span></span>](../core/deploying-the-service-oriented-solution.md)