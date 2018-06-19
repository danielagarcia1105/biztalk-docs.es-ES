---
title: 'Escenario: Actualización de artefactos de la aplicación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, artifacts
- updating, artifacts
- artifacts, examples
- updating, examples
- examples, updating
- artifacts, updating
ms.assetid: 76833df3-2330-48af-84d8-731028b192ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e95e6a66fb0e6bccc1fcc2fb4a7664538e50d3e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269540"
---
# <a name="scenario-updating-application-artifacts"></a><span data-ttu-id="fdcb2-102">Escenario: Actualización de artefactos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="fdcb2-102">Scenario: Updating Application Artifacts</span></span>
<span data-ttu-id="fdcb2-103">Existen dos casos básicos para la actualización de artefactos de una aplicación implementada en un entorno de producción:</span><span class="sxs-lookup"><span data-stu-id="fdcb2-103">There are two basic scenarios for updating the artifacts in an application that has been deployed into a production environment:</span></span>  
  
-   <span data-ttu-id="fdcb2-104">La actualización de una orquestación con una versión nueva cuando la orquestación controla transacciones de larga ejecución o está esperando la respuesta de un puerto de petición-respuesta.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-104">Updating an orchestration with a new version when the orchestration handles long-running transactions or is waiting for a response from a solicit-response port.</span></span>  
  
-   <span data-ttu-id="fdcb2-105">El caso de actualización más común, cuando no le preocupa la finalización del procesamiento de mensajes, es la actualización de un esquema o de una asignación con una versión nueva.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-105">The more general update case, when you are not concerned with completing message processing, such as updating a schema or map with a new version.</span></span>  
  
 <span data-ttu-id="fdcb2-106">En el caso de actualización general, puede actualizar un artefacto con una versión nueva, por ejemplo para realizar un cambio en los requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-106">In the general update case, you may be updating an artifact with a new version, for example to address a change in business requirements.</span></span> <span data-ttu-id="fdcb2-107">Este caso es bastante sencillo: además, puede sobrescribir el artefacto original con el que está actualizado.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-107">This scenario is relatively straightforward, and you can overwrite the original artifact with the updated one.</span></span> <span data-ttu-id="fdcb2-108">Para obtener una lista de los pasos necesarios, consulte [lista de comprobación: actualizar los artefactos de una aplicación de BizTalk](../core/checklist-update-the-artifacts-in-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="fdcb2-108">For a list of the steps involved, see [Checklist: Update the Artifacts in a BizTalk Application](../core/checklist-update-the-artifacts-in-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="fdcb2-109">El segundo caso es más complejo.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-109">The second scenario is more complex.</span></span> <span data-ttu-id="fdcb2-110">En este caso, debe permitir que la orquestación existente finalice el procesamiento de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-110">In this case, you must allow the existing orchestration to finish processing the messages.</span></span> <span data-ttu-id="fdcb2-111">Al mismo tiempo, debe evitar que la orquestación existente procese cualquier mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-111">At the same time, you must prevent the existing orchestration from processing any new messages.</span></span> <span data-ttu-id="fdcb2-112">En cambio, la versión actualizada de la orquestación debe asumirlos.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-112">Instead, you want the updated version of the orchestration to take over.</span></span> <span data-ttu-id="fdcb2-113">Para ello, implemente el ensamblado que contiene la orquestación actualizada en la misma aplicación de BizTalk que la versión original y, a continuación, ejecute las dos orquestaciones de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-113">To accomplish this, you deploy the assembly containing the updated orchestration into the same BizTalk application as the original version, and then run both orchestrations simultaneously.</span></span> <span data-ttu-id="fdcb2-114">(El nuevo ensamblado debe tener un número de versión diferente que el ensamblado que contiene la orquestación original, de lo contrario, no podrá implementarlo en el mismo grupo de BizTalk.) A continuación, debe detener la orquestación original para que los mensajes nuevos no se enruten hacia ella e iniciar la versión actualizada, con lo que todos los mensajes nuevos se envían a esta última.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-114">(The new assembly must have a different version number than the assembly containing the original orchestration, or you will not be able to deploy it into the same BizTalk group.) You then stop the original orchestration, so that no new messages are routed to it, and start the updated version, so that all new messages are sent to it.</span></span> <span data-ttu-id="fdcb2-115">Una vez que la versión original haya finalizado de procesar todos los mensajes, puede anular la implementación.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-115">After the original version has finished processing all of its messages, you can then undeploy it.</span></span> <span data-ttu-id="fdcb2-116">Para obtener instrucciones acerca de cómo realizar estas tareas, consulte [cómo actualizar una orquestación](../core/how-to-upgrade-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="fdcb2-116">For instructions on performing these tasks, see [How to Upgrade an Orchestration](../core/how-to-upgrade-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="fdcb2-117">El siguiente diagrama muestra una implementación habitual de orquestación en paralelo.</span><span class="sxs-lookup"><span data-stu-id="fdcb2-117">The following diagram shows a typical side-by-side orchestration deployment.</span></span>  
  
 <span data-ttu-id="fdcb2-118">![Escenario de implementación en paralelo](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")</span><span class="sxs-lookup"><span data-stu-id="fdcb2-118">![Side by Side Deployment Scenario](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdcb2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdcb2-119">See Also</span></span>  
 <span data-ttu-id="fdcb2-120">[Escenarios de administración e implementación de aplicaciones](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="fdcb2-120">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 [<span data-ttu-id="fdcb2-121">Consideraciones importantes para actualizar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fdcb2-121">Important Considerations for Updating Applications</span></span>](../core/important-considerations-for-updating-applications.md)