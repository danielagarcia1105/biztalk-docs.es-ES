---
title: Creación de controladores de excepción personalizada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 401aec8d-d9ca-4a88-9e5b-d3ab605dc0a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33d49fddb8a42c440f62acdd4ea337f43b876f6b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971525"
---
# <a name="creating-custom-exception-handlers"></a><span data-ttu-id="90a54-102">Creación de controladores de excepciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="90a54-102">Creating Custom Exception Handlers</span></span>
<span data-ttu-id="90a54-103">Para que una aplicación detectar y reaccionar ante las excepciones, los programadores deben proporcionar un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="90a54-103">For an application to detect and react to exceptions, developers must provide an exception handler.</span></span> <span data-ttu-id="90a54-104">Este controlador de excepciones puede suscribirse a un único tipo de mensaje de excepción o a los mensajes de excepción generados a partir de algunas o todas las partes de un sistema o una aplicación.</span><span class="sxs-lookup"><span data-stu-id="90a54-104">This exception handler can subscribe to a single type of exception message or to exception messages generated from some or all parts of a system or an application.</span></span> <span data-ttu-id="90a54-105">Por ejemplo, puede requerir solo un único controlador para todos los mensajes desde un sistema determinado (por ejemplo, las excepciones que se producen en el sistema de nóminas) o en su lugar puede requerir controladores de destino para los errores específicos (por ejemplo, para detectar si la comprobación del proceso de impresión se produce un error).</span><span class="sxs-lookup"><span data-stu-id="90a54-105">For example, you may require only a single handler for all messages from a particular system (such as any exceptions occurring in the payroll system), or you may instead require targeted handlers for specific failures (such as detecting if the check print process fails).</span></span>  
  
 <span data-ttu-id="90a54-106">Para suscribirse a un tipo de excepción específico, utilice una orquestación que tenga un filtro en la forma recepción de activación, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="90a54-106">To subscribe to a specific type of exception, use an orchestration that has a filter on the activating Receive shape, as shown in the following example.</span></span>  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.Schemas.Property.FaultCode == "1000";  
```  
  
 <span data-ttu-id="90a54-107">También puede tener una condición de filtro en un puerto de envío que envía un mensaje al sistema de archivos o a través de correo electrónico si el mensaje cumple una condición de filtro específico.</span><span class="sxs-lookup"><span data-stu-id="90a54-107">You may also have a filter condition on a send port that sends a message to the file system or via e-mail if the message meets a specific filter condition.</span></span>  
  
## <a name="sample-exception-handling-projects"></a><span data-ttu-id="90a54-108">Proyectos de ejemplo de control de excepciones</span><span class="sxs-lookup"><span data-stu-id="90a54-108">Sample Exception Handling Projects</span></span>  
 <span data-ttu-id="90a54-109">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye varias aplicaciones de BizTalk de ejemplo que muestran el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="90a54-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several sample BizTalk applications that demonstrate exception handling.</span></span> <span data-ttu-id="90a54-110">Estos ejemplos se pueden encontrar en la carpeta de control \Source\Samples\Exception.</span><span class="sxs-lookup"><span data-stu-id="90a54-110">These samples can be found in the \Source\Samples\Exception Handling folder.</span></span>  
  
 <span data-ttu-id="90a54-111">También hay cuatro proyectos de BizTalk, ubicados en la solución GlobalBank.ESB.Samples.ExceptionHandling, que muestran cómo usar el mecanismo de excepción enrutamiento de orquestación de error de ESB.</span><span class="sxs-lookup"><span data-stu-id="90a54-111">There are also four BizTalk projects, located in the GlobalBank.ESB.Samples.ExceptionHandling solution, that demonstrate how to use the ESB Failed Orchestration Exception Routing mechanism.</span></span> <span data-ttu-id="90a54-112">Estos proyectos están preconfigurados para implementar en la aplicación de GlobalBank.ESB BizTalk.</span><span class="sxs-lookup"><span data-stu-id="90a54-112">These projects are preconfigured to deploy into the GlobalBank.ESB BizTalk application.</span></span> <span data-ttu-id="90a54-113">Los proyectos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="90a54-113">The projects are the following:</span></span>  
  
- <span data-ttu-id="90a54-114">**ESB. ExceptionHandling.Schemas.**</span><span class="sxs-lookup"><span data-stu-id="90a54-114">**ESB.ExceptionHandling.Schemas.**</span></span> <span data-ttu-id="90a54-115">Este proyecto contiene los esquemas utilizados para las orquestaciones de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="90a54-115">This project contains the schemas used for the sample orchestrations.</span></span>  
  
- <span data-ttu-id="90a54-116">**ESB. ExceptionHandling.Pipelines.**</span><span class="sxs-lookup"><span data-stu-id="90a54-116">**ESB.ExceptionHandling.Pipelines.**</span></span> <span data-ttu-id="90a54-117">Este proyecto contiene la canalización de envío configurada con el procesador de excepción, utilizado en un puerto de envío se suscribe a todas las excepciones.</span><span class="sxs-lookup"><span data-stu-id="90a54-117">This project contains the send pipeline configured with the exception processor, used in a send port that subscribes to all exceptions.</span></span> <span data-ttu-id="90a54-118">Esto incluye las excepciones generadas por BizTalk y las excepciones generadas por el marco de administración de excepciones.</span><span class="sxs-lookup"><span data-stu-id="90a54-118">This includes exceptions generated by BizTalk and exceptions generated by the Exception Management Framework.</span></span>  
  
- <span data-ttu-id="90a54-119">**ESB. ExceptionHandling.Processes.**</span><span class="sxs-lookup"><span data-stu-id="90a54-119">**ESB.ExceptionHandling.Processes.**</span></span> <span data-ttu-id="90a54-120">Este proyecto contiene la orquestación EAIProcess.odx, que simula una excepción al intentar dividir por cero y llama a la **CreateFaultMessage** y **AddMessage** métodos para generar un adecuado mensaje de error, tal como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="90a54-120">This project contains the EAIProcess.odx orchestration, which simulates an exception by attempting to divide by zero and calls the **CreateFaultMessage** and **AddMessage** methods to generate a suitable fault message, as shown in Figure 1.</span></span>  
  
   <span data-ttu-id="90a54-121">![Orquestación procesa ejemplo](../esb-toolkit/media/ch4-orchestrationprocessessample.gif "Ch4-OrchestrationProcessesSample")</span><span class="sxs-lookup"><span data-stu-id="90a54-121">![Orchestration Processes Sample](../esb-toolkit/media/ch4-orchestrationprocessessample.gif "Ch4-OrchestrationProcessesSample")</span></span>  
  
   <span data-ttu-id="90a54-122">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="90a54-122">**Figure 1**</span></span>  
  
  <span data-ttu-id="90a54-123">**La orquestación EAIProcess.odx en el proyecto de ejemplo de procesos**</span><span class="sxs-lookup"><span data-stu-id="90a54-123">**The EAIProcess.odx orchestration in the Processes sample project**</span></span>  
  
- <span data-ttu-id="90a54-124">**ESB. ExceptionHandling.Handlers.**</span><span class="sxs-lookup"><span data-stu-id="90a54-124">**ESB.ExceptionHandling.Handlers.**</span></span> <span data-ttu-id="90a54-125">Este proyecto contiene la orquestación EAIGenericHandler.odx, que llama a la **GetMessages** método y recorre en iteración la **MessageCollection** utilizando el **MoveNext**método, como se muestra en la figura 2.</span><span class="sxs-lookup"><span data-stu-id="90a54-125">This project contains the EAIGenericHandler.odx orchestration, which calls the **GetMessages** method and iterates through the **MessageCollection** using the **MoveNext** method, as shown in Figure 2.</span></span>  
  
  <span data-ttu-id="90a54-126">![Ejemplo genérico de controladores de orquestación](../esb-toolkit/media/ch4-orchestrationhandlerssamplegeneric.gif "Ch4-OrchestrationHandlersSampleGeneric")</span><span class="sxs-lookup"><span data-stu-id="90a54-126">![Orchestration Handlers Sample Generic](../esb-toolkit/media/ch4-orchestrationhandlerssamplegeneric.gif "Ch4-OrchestrationHandlersSampleGeneric")</span></span>  
  
  <span data-ttu-id="90a54-127">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="90a54-127">**Figure 2**</span></span>  
  
  <span data-ttu-id="90a54-128">**La orquestación EAIGenericHandler.odx en el proyecto de ejemplo de controladores**</span><span class="sxs-lookup"><span data-stu-id="90a54-128">**The EAIGenericHandler.odx orchestration in the Handlers sample project**</span></span>  
  
  <span data-ttu-id="90a54-129">Lo ESB. ExceptionHandling.Handlers proyecto también contiene la orquestación EAIProcessHandler.odx, que llama a la **GetMessage** y **GetException** métodos, como se muestra en la figura 3.</span><span class="sxs-lookup"><span data-stu-id="90a54-129">The ESB.ExceptionHandling.Handlers project also contains the EAIProcessHandler.odx orchestration, which calls the **GetMessage** and **GetException** methods, as shown in Figure 3.</span></span>  
  
  <span data-ttu-id="90a54-130">![Proceso de ejemplo de controladores de orquestación](../esb-toolkit/media/ch4-orchestrationhandlerssampleprocess.gif "Ch4-OrchestrationHandlersSampleProcess")</span><span class="sxs-lookup"><span data-stu-id="90a54-130">![Orchestration Handlers Sample Process](../esb-toolkit/media/ch4-orchestrationhandlerssampleprocess.gif "Ch4-OrchestrationHandlersSampleProcess")</span></span>  
  
  <span data-ttu-id="90a54-131">**Figura 3**</span><span class="sxs-lookup"><span data-stu-id="90a54-131">**Figure 3**</span></span>  
  
  <span data-ttu-id="90a54-132">**La orquestación EAIProcessHandler.odx en el proyecto de ejemplo de controladores**</span><span class="sxs-lookup"><span data-stu-id="90a54-132">**The EAIProcessHandler.odx orchestration in the Handlers sample project**</span></span>