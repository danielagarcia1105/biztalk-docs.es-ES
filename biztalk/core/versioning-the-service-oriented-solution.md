---
title: "Solución orientada a servicios de control de versiones del servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- versioning, service solutions
- service solution tutorial, versioning
ms.assetid: 0e09720f-53f2-4b38-aae3-a79ddfd35be5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af1c5d1475fc37322be9a8483963bbfd1432fbb4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="versioning-the-service-oriented-solution"></a><span data-ttu-id="c0c8c-102">Solución orientada a servicios de control de versiones del servicio</span><span class="sxs-lookup"><span data-stu-id="c0c8c-102">Versioning the Service Oriented Solution</span></span>
<span data-ttu-id="c0c8c-103">Las dos orquestaciones que actúan como servidores front-end a la solución, **CustomerServiceReceiveSend** y **CustomerServiceNativeRequestResponse**, llame a la central, la orquestación de trabajo,  **CustomerService**.</span><span class="sxs-lookup"><span data-stu-id="c0c8c-103">The two orchestrations that act as front ends to the solution, **CustomerServiceReceiveSend** and **CustomerServiceNativeRequestResponse**, call the central, working orchestration, **CustomerService**.</span></span> <span data-ttu-id="c0c8c-104">Las llamadas a la orquestación dependen del número de versión del ensamblado que contiene la orquestación.</span><span class="sxs-lookup"><span data-stu-id="c0c8c-104">Orchestration calls depend on the version number of the assembly containing the orchestration.</span></span> <span data-ttu-id="c0c8c-105">Dado que las tres orquestaciones están en el mismo ensamblado, no hay ningún problema de control de versiones.</span><span class="sxs-lookup"><span data-stu-id="c0c8c-105">Because all three orchestrations are in the same assembly, there are no versioning issues.</span></span>  
  
 <span data-ttu-id="c0c8c-106">Además, el proceso empresarial que implementan las orquestaciones es un proceso de solicitud-respuesta muy efímero que se ejecuta rápidamente.</span><span class="sxs-lookup"><span data-stu-id="c0c8c-106">In addition, the business process implemented by the orchestrations is a very short-lived request-response process that completes quickly.</span></span> <span data-ttu-id="c0c8c-107">Por lo tanto, la pregunta de versiones del proceso empresarial no se da en esta solución, no hay ninguna orquestación diferente en distintos ensamblados con distintas versiones.</span><span class="sxs-lookup"><span data-stu-id="c0c8c-107">Thus, the question of versioning the business process does not arise in this solution—there are no different orchestrations in different assemblies with different versions.</span></span>  
  
 <span data-ttu-id="c0c8c-108">Sin embargo, las orquestaciones utilizan los esquemas del ensamblado de esquema.</span><span class="sxs-lookup"><span data-stu-id="c0c8c-108">However, the orchestrations do use the schemas in the schema assembly.</span></span> <span data-ttu-id="c0c8c-109">Si los esquemas se revisan y compilan en una versión diferente, debe volver a compilar las orquestaciones con la versión más nueva del ensamblado de esquema.</span><span class="sxs-lookup"><span data-stu-id="c0c8c-109">If the schemas are revised and compiled into a different version, you must recompile the orchestrations with the newer version of the schema assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c8c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0c8c-110">See Also</span></span>  
 [<span data-ttu-id="c0c8c-111">Desarrollar un servicio en la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="c0c8c-111">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)