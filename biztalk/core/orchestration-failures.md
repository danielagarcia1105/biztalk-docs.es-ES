---
title: Errores de orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Catch Exception block [Orchestration Designer], suspended orchestrations
- HAT, Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], HAT
- orchestrations, troubleshooting [HAT]
- orchestrations, errors
- HAT, Orchestration Debugger
- Orchestration Debugger
- errors, orchestrations
- HAT, troubleshooting orchestrations
- orchestrations, HAT
- HAT, orchestrations
ms.assetid: d0a799fb-7859-4774-b444-979f22f04215
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d95cab903ae9bf5faacdf385f667c33f9a2d5a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-failures"></a><span data-ttu-id="75cba-102">Errores de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="75cba-102">Orchestration Failures</span></span>
<span data-ttu-id="75cba-103">Las orquestaciones varían en complejidad; por ejemplo, una orquestación puede llamar a un objeto .NET o construir mensajes mediante la forma de transformación o de asignación.</span><span class="sxs-lookup"><span data-stu-id="75cba-103">Orchestrations vary in complexity; for example, an orchestration may call a .NET object or construct messages via transform and assignment shape.</span></span> <span data-ttu-id="75cba-104">En consecuencia, resulta imposible mostrar una lista de todos los errores debido a la variedad de su contenido y al nivel de personalización.</span><span class="sxs-lookup"><span data-stu-id="75cba-104">As a result, it is impossible to list out every possible failure, due to the variety of its content as well as level of customization.</span></span> <span data-ttu-id="75cba-105">Sin embargo, los errores que se producen en las orquestaciones aparecen como excepciones.</span><span class="sxs-lookup"><span data-stu-id="75cba-105">However, all failures encountered in orchestrations appear as exceptions.</span></span>  
  
 <span data-ttu-id="75cba-106">Si una orquestación no incluye ningún **CatchException** forma para una excepción, la excepción hace que la orquestación suspendida, pero no reanudable.</span><span class="sxs-lookup"><span data-stu-id="75cba-106">If an orchestration does not include any **CatchException** shape for an exception, the exception causes the orchestration to be Suspended, but not resumable.</span></span> <span data-ttu-id="75cba-107">Esto significa que el seguimiento de instancias de mensajes y servicios, o un script WMI, no puede recuperar la instancia.</span><span class="sxs-lookup"><span data-stu-id="75cba-107">This means that message and service instance tracking, or a WMI script, cannot recover the instance.</span></span> <span data-ttu-id="75cba-108">Sin embargo, se pueden guardar todos los mensajes asociados a la instancia Suspendido (no reanudable) mediante el seguimiento (o script WMI) para realizar un diagnóstico y reintentarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="75cba-108">However, you can save all messages associated with the Suspended (not Resumable) instance using tracking (or WMI script) for diagnostic and manual retry.</span></span>  
  
 <span data-ttu-id="75cba-109">Para diagnosticar el problema, use el depurador de orquestaciones para ver la última forma que se ejecutó antes de que se suspendiera la instancia.</span><span class="sxs-lookup"><span data-stu-id="75cba-109">To diagnose the problem, use the Orchestration Debugger to see the last shape executed before the instance is suspended.</span></span> <span data-ttu-id="75cba-110">Asimismo, se pueden visualizar los detalles de la excepción con el depurador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="75cba-110">You can also view exception details using the Orchestration Debugger.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75cba-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="75cba-111">See Also</span></span>  
 <span data-ttu-id="75cba-112">[Investigación de orquestación, puerto y errores de mensaje](../core/investigating-orchestration-port-and-message-failures.md) </span><span class="sxs-lookup"><span data-stu-id="75cba-112">[Investigating Orchestration, Port, and Message Failures](../core/investigating-orchestration-port-and-message-failures.md) </span></span>  
 [<span data-ttu-id="75cba-113">Depuración de una orquestación</span><span class="sxs-lookup"><span data-stu-id="75cba-113">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)