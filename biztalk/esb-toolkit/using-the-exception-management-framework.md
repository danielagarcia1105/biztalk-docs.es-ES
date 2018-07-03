---
title: Mediante el marco de administración de excepciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b69c9c01-e7e4-4788-8fe2-43d32075155d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8146b3f2f9be6d076cfd7dddd651ee2c9bb4d3c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991533"
---
# <a name="using-the-exception-management-framework"></a><span data-ttu-id="76247-102">Mediante el marco de administración de excepciones</span><span class="sxs-lookup"><span data-stu-id="76247-102">Using the Exception Management Framework</span></span>
<span data-ttu-id="76247-103">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] usa las excepciones para comunicar los errores (por ejemplo, un mapa no implementada o reglas que no devuelven un nombre de asignación) para las transformaciones dinámicas y el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="76247-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses exceptions to communicate failures (for example, a non-deployed map or rules that do not return a map name) for dynamic transformations and routing.</span></span> <span data-ttu-id="76247-104">Cuando se produce un error en una transformación o un proceso de enrutamiento, ESB crea un mensaje de excepción y lo envía a través de un puerto de enlace directo a la base de datos de cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="76247-104">When a transformation or routing process fails, the ESB creates an exception message and submits it through a direct-bound port to the Message Box database.</span></span> <span data-ttu-id="76247-105">Lo ESB también implementa un puerto de envío denominado todos. Excepciones que se suscribe a y recupera mensajes de excepción y los publica en el Portal de administración de ESB.</span><span class="sxs-lookup"><span data-stu-id="76247-105">The ESB also implements a send port named ALL.Exceptions that subscribes to and retrieves exception messages and publishes them to the ESB Management Portal.</span></span>  

 <span data-ttu-id="76247-106">Además, todos los ejemplos de la orquestación utilizan la orquestación de error ESB API de enrutamiento de excepción para controlar las excepciones.</span><span class="sxs-lookup"><span data-stu-id="76247-106">In addition, all orchestration samples use the ESB Failed Orchestration Exception Routing API to handle exceptions.</span></span> <span data-ttu-id="76247-107">Puede utilizar esta API en cualquier proyecto de orquestación que implementa.</span><span class="sxs-lookup"><span data-stu-id="76247-107">You can use this API in any orchestration project you deploy.</span></span> <span data-ttu-id="76247-108">La característica de excepción enrutamiento de orquestación de error de ESB proporciona una manera estándar para capturar y notificar todas las excepciones en un entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="76247-108">The ESB Failed Orchestration Exception Routing feature provides a standard way to trap and report all exceptions in a BizTalk Server environment.</span></span>  

 <span data-ttu-id="76247-109">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene varios proyectos de ejemplo que muestran cómo usar el marco de administración de excepciones de ESB.</span><span class="sxs-lookup"><span data-stu-id="76247-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains several sample projects that demonstrate how to use the ESB Exception Management Framework.</span></span> <span data-ttu-id="76247-110">Los siguientes dos proyectos encapsulan la orquestación de error ESB API de enrutamiento de excepción:</span><span class="sxs-lookup"><span data-stu-id="76247-110">The following two projects encapsulate the ESB Failed Orchestration Exception Routing API:</span></span>  

- <span data-ttu-id="76247-111">**ESB. ExceptionHandling**.</span><span class="sxs-lookup"><span data-stu-id="76247-111">**ESB.ExceptionHandling**.</span></span> <span data-ttu-id="76247-112">Este proyecto contiene todos los métodos públicos para controlar el procesamiento de mensajes de error en las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="76247-112">This project contains all the public methods for handling fault message processing in orchestrations.</span></span> <span data-ttu-id="76247-113">Debe registrar el ensamblado de este proyecto en la caché global de ensamblados en el servidor local.</span><span class="sxs-lookup"><span data-stu-id="76247-113">You must register the assembly in this project in the global assembly cache on the local server.</span></span>  

- <span data-ttu-id="76247-114">**ESB. ExceptionHandling.Schemas.Faults**.</span><span class="sxs-lookup"><span data-stu-id="76247-114">**ESB.ExceptionHandling.Schemas.Faults**.</span></span> <span data-ttu-id="76247-115">Este proyecto contiene el esquema de mensaje de error definido por el espacio de nombres **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling** y el esquema de propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="76247-115">This project contains the fault message schema defined by the namespace **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling** and the system property schema.</span></span> <span data-ttu-id="76247-116">Debe implementar este proyecto en el contenedor de aplicación Microsoft.Practices.ESB.</span><span class="sxs-lookup"><span data-stu-id="76247-116">You must deploy this project to the Microsoft.Practices.ESB application container.</span></span>  

  <span data-ttu-id="76247-117">Todos los proyectos que usan la orquestación de error ESB API de enrutamiento de excepción deben hacer referencia a los ensamblados básicos:</span><span class="sxs-lookup"><span data-stu-id="76247-117">All projects that use the ESB Failed Orchestration Exception Routing API must reference the core assemblies:</span></span>  

- <span data-ttu-id="76247-118">**Microsoft.Practices.ESB.ExceptionHandling.dll**</span><span class="sxs-lookup"><span data-stu-id="76247-118">**Microsoft.Practices.ESB.ExceptionHandling.dll**</span></span>  

- <span data-ttu-id="76247-119">**Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**</span><span class="sxs-lookup"><span data-stu-id="76247-119">**Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**</span></span>  

  <span data-ttu-id="76247-120">Las secciones siguientes proporcionan más información sobre cómo usar el marco de administración de excepciones de ESB:</span><span class="sxs-lookup"><span data-stu-id="76247-120">The following sections provide more information about using the ESB Exception Management Framework:</span></span>  

- [<span data-ttu-id="76247-121">Los miembros de la API de excepciones de ESB</span><span class="sxs-lookup"><span data-stu-id="76247-121">The ESB Exception API Members</span></span>](../esb-toolkit/the-esb-exception-api-members.md)  

- [<span data-ttu-id="76247-122">Creación y publicación de mensajes de error</span><span class="sxs-lookup"><span data-stu-id="76247-122">Creating and Publishing Fault Messages</span></span>](../esb-toolkit/creating-and-publishing-fault-messages.md)  

- [<span data-ttu-id="76247-123">Suscripción y extracción de mensajes</span><span class="sxs-lookup"><span data-stu-id="76247-123">Subscribing to and Extracting Messages</span></span>](../esb-toolkit/subscribing-to-and-extracting-messages.md)  

- [<span data-ttu-id="76247-124">Pasos de solución de escenarios</span><span class="sxs-lookup"><span data-stu-id="76247-124">Scenario Solution Steps</span></span>](../esb-toolkit/scenario-solution-steps.md)
