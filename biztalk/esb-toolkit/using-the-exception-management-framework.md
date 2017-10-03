---
title: "Mediante el marco de trabajo de administración de excepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b69c9c01-e7e4-4788-8fe2-43d32075155d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47442604831a3a11bb9d00b65f9dc34961de2367
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-exception-management-framework"></a><span data-ttu-id="bd7d0-102">Mediante el marco de administración de excepciones</span><span class="sxs-lookup"><span data-stu-id="bd7d0-102">Using the Exception Management Framework</span></span>
<span data-ttu-id="bd7d0-103">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] usa las excepciones para comunicar errores (por ejemplo, un mapa no implementada o las reglas que no devuelven un nombre de asignación) para las transformaciones dinámicas y el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses exceptions to communicate failures (for example, a non-deployed map or rules that do not return a map name) for dynamic transformations and routing.</span></span> <span data-ttu-id="bd7d0-104">Cuando se produce un error en una transformación o un proceso de enrutamiento, ESB crea un mensaje de excepción y lo envía a través de un puerto de enlace directo a la base de datos de cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-104">When a transformation or routing process fails, the ESB creates an exception message and submits it through a direct-bound port to the Message Box database.</span></span> <span data-ttu-id="bd7d0-105">ESB también implementa un puerto de envío denominado todos. Excepciones que se suscribe a y recupera mensajes de excepción y los publica en el Portal de administración de ESB.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-105">The ESB also implements a send port named ALL.Exceptions that subscribes to and retrieves exception messages and publishes them to the ESB Management Portal.</span></span>  
  
 <span data-ttu-id="bd7d0-106">Además, todos los ejemplos de orquestación utilizan la orquestación de error ESB API de enrutamiento de excepción para controlar las excepciones.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-106">In addition, all orchestration samples use the ESB Failed Orchestration Exception Routing API to handle exceptions.</span></span> <span data-ttu-id="bd7d0-107">Puede utilizar esta API en cualquier proyecto de orquestación que implementa.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-107">You can use this API in any orchestration project you deploy.</span></span> <span data-ttu-id="bd7d0-108">La característica excepción enrutamiento de orquestación de error de ESB proporciona un método estándar para capturar y notificar todas las excepciones en un entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-108">The ESB Failed Orchestration Exception Routing feature provides a standard way to trap and report all exceptions in a BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="bd7d0-109">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene varios proyectos de ejemplo que muestran cómo usar el marco de trabajo de administración de excepciones de ESB.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains several sample projects that demonstrate how to use the ESB Exception Management Framework.</span></span> <span data-ttu-id="bd7d0-110">Los siguientes dos proyectos encapsulan la orquestación de error ESB API de enrutamiento de excepción:</span><span class="sxs-lookup"><span data-stu-id="bd7d0-110">The following two projects encapsulate the ESB Failed Orchestration Exception Routing API:</span></span>  
  
-   <span data-ttu-id="bd7d0-111">**ESB. ExceptionHandling**.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-111">**ESB.ExceptionHandling**.</span></span> <span data-ttu-id="bd7d0-112">Este proyecto contiene todos los métodos públicos para controlar el procesamiento de mensajes de error en las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-112">This project contains all the public methods for handling fault message processing in orchestrations.</span></span> <span data-ttu-id="bd7d0-113">Debe registrar el ensamblado de este proyecto en la caché global de ensamblados en el servidor local.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-113">You must register the assembly in this project in the global assembly cache on the local server.</span></span>  
  
-   <span data-ttu-id="bd7d0-114">**ESB. ExceptionHandling.Schemas.Faults**.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-114">**ESB.ExceptionHandling.Schemas.Faults**.</span></span> <span data-ttu-id="bd7d0-115">Este proyecto contiene el esquema de mensaje de error definido por el espacio de nombres **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling** y el esquema de propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-115">This project contains the fault message schema defined by the namespace **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling** and the system property schema.</span></span> <span data-ttu-id="bd7d0-116">Debe implementar este proyecto en el contenedor de la aplicación Microsoft.Practices.ESB.</span><span class="sxs-lookup"><span data-stu-id="bd7d0-116">You must deploy this project to the Microsoft.Practices.ESB application container.</span></span>  
  
 <span data-ttu-id="bd7d0-117">Todos los proyectos que utilizan la orquestación de error ESB API de enrutamiento excepción deben hacer referencia a los ensamblados básicos de:</span><span class="sxs-lookup"><span data-stu-id="bd7d0-117">All projects that use the ESB Failed Orchestration Exception Routing API must reference the core assemblies:</span></span>  
  
-   <span data-ttu-id="bd7d0-118">**Microsoft.Practices.ESB.ExceptionHandling.dll**</span><span class="sxs-lookup"><span data-stu-id="bd7d0-118">**Microsoft.Practices.ESB.ExceptionHandling.dll**</span></span>  
  
-   <span data-ttu-id="bd7d0-119">**Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**</span><span class="sxs-lookup"><span data-stu-id="bd7d0-119">**Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**</span></span>  
  
 <span data-ttu-id="bd7d0-120">En las secciones siguientes proporcionan más información acerca de cómo utilizar el marco de trabajo de administración de excepciones de ESB:</span><span class="sxs-lookup"><span data-stu-id="bd7d0-120">The following sections provide more information about using the ESB Exception Management Framework:</span></span>  
  
-   [<span data-ttu-id="bd7d0-121">Los miembros de la API de excepción de ESB</span><span class="sxs-lookup"><span data-stu-id="bd7d0-121">The ESB Exception API Members</span></span>](../esb-toolkit/the-esb-exception-api-members.md)  
  
-   [<span data-ttu-id="bd7d0-122">Creación y publicación de mensajes de error</span><span class="sxs-lookup"><span data-stu-id="bd7d0-122">Creating and Publishing Fault Messages</span></span>](../esb-toolkit/creating-and-publishing-fault-messages.md)  
  
-   [<span data-ttu-id="bd7d0-123">Suscribirse a y extraer los mensajes</span><span class="sxs-lookup"><span data-stu-id="bd7d0-123">Subscribing to and Extracting Messages</span></span>](../esb-toolkit/subscribing-to-and-extracting-messages.md)  
  
-   [<span data-ttu-id="bd7d0-124">Pasos de solución de escenario</span><span class="sxs-lookup"><span data-stu-id="bd7d0-124">Scenario Solution Steps</span></span>](../esb-toolkit/scenario-solution-steps.md)