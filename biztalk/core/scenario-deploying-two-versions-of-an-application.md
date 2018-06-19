---
title: 'Escenario: Implementar dos versiones de una aplicación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, multiple assemblies
- assemblies, multiple assemblies
- receive locations, examples
- assemblies, deploying
- assemblies, examples
ms.assetid: 3e79a7df-bf77-4a0b-86ec-359fcf3489b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1bb4f04e8b00dd171de89bbed6f01d2a2d1e2e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268940"
---
# <a name="scenario-deploying-two-versions-of-an-application"></a><span data-ttu-id="b83b7-102">Escenario: Implementar dos versiones de una aplicación</span><span class="sxs-lookup"><span data-stu-id="b83b7-102">Scenario: Deploying Two Versions of an Application</span></span>
<span data-ttu-id="b83b7-103">En este tema se describe el escenario de implementación de dos versiones de una aplicación en un grupo de BizTalk, de modo que se puedan ejecutar de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="b83b7-103">This topic describes the scenario of deploying two versions of an application within a BizTalk group, so that they can both run simultaneously.</span></span> <span data-ttu-id="b83b7-104">En este escenario, deberá implementar una versión principal nueva de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b83b7-104">In this scenario, you need to deploy a major new version of the application.</span></span> <span data-ttu-id="b83b7-105">Necesita socios comerciales para cambiar su interacción con el sistema debido a su cambio de esquema o de protocolo, básicamente una aplicación nueva.</span><span class="sxs-lookup"><span data-stu-id="b83b7-105">It requires partners to change their interaction with the system due to either schema or protocol change - essentially a new application.</span></span> <span data-ttu-id="b83b7-106">El cambio a este sistema se ha probado aunque no bajo la escala de un sistema de producción completo.</span><span class="sxs-lookup"><span data-stu-id="b83b7-106">The changeover to this system has been tested but not under the scale of a full production system.</span></span> <span data-ttu-id="b83b7-107">Desea poner a prueba el sistema nuevo con el 20 por ciento de los socios comerciales para ir aumentando gradualmente ese porcentaje hasta que todos los socios comerciales lo usen.</span><span class="sxs-lookup"><span data-stu-id="b83b7-107">You want to pilot the new system with 20 percent of the partners, and gradually increase that percentage until all the partners are using it.</span></span>  
  
 <span data-ttu-id="b83b7-108">Debido a que las dos aplicaciones reciben mensajes en dos ubicaciones de recepción diferentes, debe pedir a los socios que usen la versión nueva de la aplicación para enviar mensajes a la nueva dirección URL de modo que la versión nueva procesará los mensajes.</span><span class="sxs-lookup"><span data-stu-id="b83b7-108">Because the two applications receive messages on two different receive locations, you must ask those partners that should use the new version of the application to send messages to the new URL, so that they will be processed by the new version.</span></span>  
  
 <span data-ttu-id="b83b7-109">El siguiente diagrama muestra una implementación habitual de aplicaciones en paralelo.</span><span class="sxs-lookup"><span data-stu-id="b83b7-109">The following diagram shows a typical side-by-side application deployment.</span></span>  
  
 <span data-ttu-id="b83b7-110">![Dos versiones de ensamblado implementadas conjuntamente](../core/media/sidebysideassemblyversions.gif "SideBySideAssemblyVersions")</span><span class="sxs-lookup"><span data-stu-id="b83b7-110">![Two Assembly Versions Deployed Together](../core/media/sidebysideassemblyversions.gif "SideBySideAssemblyVersions")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b83b7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b83b7-111">See Also</span></span>  
 [<span data-ttu-id="b83b7-112">Escenarios de administración e implementación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b83b7-112">Application Deployment and Management Scenarios</span></span>](../core/application-deployment-and-management-scenarios.md)