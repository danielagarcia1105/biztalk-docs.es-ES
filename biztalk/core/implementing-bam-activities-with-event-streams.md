---
title: Implementar actividades BAM con secuencias de eventos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], about activities
- activities [BAM]
- BAM, activities
ms.assetid: 94e6d9dd-93c3-4ab0-9de7-a860dd1e3406
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63594b956affc0f5b94f26ccdcb10d904ef171cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-bam-activities-with-event-streams"></a><span data-ttu-id="7a7a1-102">Implementar actividades de BAM con secuencias de eventos</span><span class="sxs-lookup"><span data-stu-id="7a7a1-102">Implementing BAM Activities with Event Streams</span></span>
<span data-ttu-id="7a7a1-103">Una actividad de BAM representa una unidad de trabajo en el negocio, como un pedido o una aplicación de préstamo.</span><span class="sxs-lookup"><span data-stu-id="7a7a1-103">A BAM activity represents a unit of work in the business, such as purchase order or loan application.</span></span> <span data-ttu-id="7a7a1-104">La actividad muestra el historial (hitos) y los datos sobre esta unidad de trabajo a los usuarios finales empresariales o al trabajador de la información.</span><span class="sxs-lookup"><span data-stu-id="7a7a1-104">The activity shows the history (milestones) and data about this unit of work to the business end user, or information worker.</span></span> <span data-ttu-id="7a7a1-105">Por ejemplo, una actividad de aplicaciones de préstamo podría contener hitos como "Préstamo aprobado" y datos como" Nombre del candidato" e "Importe del préstamo".</span><span class="sxs-lookup"><span data-stu-id="7a7a1-105">For example, a loan application activity might contain milestones such as “Loan approved” and data such as “Applicant name” and “Loan amount.”</span></span> <span data-ttu-id="7a7a1-106">Las actividades de BAM a menudo se asignan directamente a un proceso empresarial, aunque como una abstracción de alto nivel, una actividad es independiente de la implementación actual de la infraestructura de TI.</span><span class="sxs-lookup"><span data-stu-id="7a7a1-106">BAM activities often map directly to a business process, although as a high-level abstraction an activity is independent of the actual implementation of your IT infrastructure.</span></span>  
  
 <span data-ttu-id="7a7a1-107">Su trabajo como programador consiste en mantener esta abstracción exponiendo los hitos relevantes y los datos de la implementación en el contexto de una actividad específica.</span><span class="sxs-lookup"><span data-stu-id="7a7a1-107">Your job as a developer is to maintain this abstraction by exposing only the relevant milestones and data from the implementation in the context of a specific activity.</span></span> <span data-ttu-id="7a7a1-108">Para obtener un ejemplo de código que muestra el uso de una actividad, consulte [API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7a7a1-108">For a code sample that demonstrates the use of an activity, see [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a7a1-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7a7a1-109">In This Section</span></span>  
  
-   [<span data-ttu-id="7a7a1-110">¿Por qué escribir código para BAM?</span><span class="sxs-lookup"><span data-stu-id="7a7a1-110">Why Write Code For BAM?</span></span>](../core/why-write-code-for-bam.md)  
  
-   [<span data-ttu-id="7a7a1-111">Conceptos de BAM para el desarrollador</span><span class="sxs-lookup"><span data-stu-id="7a7a1-111">BAM Concepts for the Developer</span></span>](../core/bam-concepts-for-the-developer.md)  
  
-   [<span data-ttu-id="7a7a1-112">Información general sobre el proceso de desarrollo de BAM</span><span class="sxs-lookup"><span data-stu-id="7a7a1-112">Overview of the BAM Development Process</span></span>](../core/overview-of-the-bam-development-process.md)  
  
-   [<span data-ttu-id="7a7a1-113">Clases EventStream</span><span class="sxs-lookup"><span data-stu-id="7a7a1-113">EventStream Classes</span></span>](../core/eventstream-classes.md)  
  
-   [<span data-ttu-id="7a7a1-114">Uso de una actividad</span><span class="sxs-lookup"><span data-stu-id="7a7a1-114">Using an Activity</span></span>](../core/using-an-activity.md)  
  
-   [<span data-ttu-id="7a7a1-115">Relaciones de actividad</span><span class="sxs-lookup"><span data-stu-id="7a7a1-115">Activity Relationships</span></span>](../core/activity-relationships.md)  
  
-   [<span data-ttu-id="7a7a1-116">Continuación de actividad</span><span class="sxs-lookup"><span data-stu-id="7a7a1-116">Activity Continuation</span></span>](../core/activity-continuation.md)  
  
-   [<span data-ttu-id="7a7a1-117">Las actividades en bucle</span><span class="sxs-lookup"><span data-stu-id="7a7a1-117">Looping Activities</span></span>](../core/looping-activities.md)  
  
-   [<span data-ttu-id="7a7a1-118">Instrumentar una solución: uso de la API de paso a paso</span><span class="sxs-lookup"><span data-stu-id="7a7a1-118">Instrumenting a Solution: Step-by-Step API Usage</span></span>](../core/instrumenting-a-solution-step-by-step-api-usage.md)