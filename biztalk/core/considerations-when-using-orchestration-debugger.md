---
title: Consideraciones al usar el depurador de orquestaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, modified orchestrations
- Orchestration Debugger, planning
- atomic scopes
- planning, Orchestration Debugger
- Orchestration Debugger, atomic scopes
- Orchestration Debugger, simple types
- orchestrations, modifying
ms.assetid: 55bfef48-08bd-48bb-abd5-7264e683da46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e3e244691d61ef27c55f606414dd08857d58f14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998157"
---
# <a name="considerations-when-using-orchestration-debugger"></a><span data-ttu-id="09c66-102">Consideraciones acerca del uso del Depurador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="09c66-102">Considerations when Using Orchestration Debugger</span></span>
<span data-ttu-id="09c66-103">A continuación se describen algunas consideraciones que debe tener en cuenta cuando trabaje con el Depurador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="09c66-103">Following are some things to consider when you work with the Orchestration Debugger.</span></span>  
  
## <a name="tracking-atomic-scopes"></a><span data-ttu-id="09c66-104">Realizar un seguimiento de ámbitos atómicos</span><span class="sxs-lookup"><span data-stu-id="09c66-104">Tracking atomic scopes</span></span>  
 <span data-ttu-id="09c66-105">Una orquestación puede contener ámbitos atómicos para incluir llamadas al motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="09c66-105">An orchestration can contain atomic scopes to include calls to the Rule Engine.</span></span> <span data-ttu-id="09c66-106">Cuando se adjunta a una instancia en el depurador de orquestaciones, todos los ámbitos atómicos en la instancia de orquestación crearán espacios en aparecen en la lista de eventos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="09c66-106">When you attach to an instance in the orchestration debugger, any atomic scopes in the orchestration instance will cause gaps to appear in the tracked events list.</span></span> <span data-ttu-id="09c66-107">Esto ocurre por dos motivos:</span><span class="sxs-lookup"><span data-stu-id="09c66-107">This happens for two reasons:</span></span>  
  
- <span data-ttu-id="09c66-108">Porque los eventos de las formas de las transacciones atómicas no se guardan hasta que se confirma el ámbito.</span><span class="sxs-lookup"><span data-stu-id="09c66-108">Because events for the shapes inside atomic transactions do not get persisted until the scope commits</span></span>  
  
- <span data-ttu-id="09c66-109">El depurador vuelve a cargar los eventos al final de la lista, por lo que todos los espacios en blanco se quedan sin rellenar durante la sesión activa.</span><span class="sxs-lookup"><span data-stu-id="09c66-109">The debugger reloads events onto the end of the list, so any gaps remain unfilled during the live session.</span></span>  
  
  <span data-ttu-id="09c66-110">Puede eliminar los espacios en blanco si actualiza la vista.</span><span class="sxs-lookup"><span data-stu-id="09c66-110">You can eliminate the gaps if you refresh the view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09c66-111">No puede establecer un punto de interrupción en formas de un ámbito atómico.</span><span class="sxs-lookup"><span data-stu-id="09c66-111">You cannot set a breakpoint on shapes inside an atomic scope.</span></span>  
  
## <a name="setting-breakpoints-in-the-exception-handler-scope"></a><span data-ttu-id="09c66-112">Establecer puntos de interrupción en el ámbito del controlador de excepción</span><span class="sxs-lookup"><span data-stu-id="09c66-112">Setting breakpoints in the exception handler scope</span></span>  
 <span data-ttu-id="09c66-113">Si el punto de interrupción se define en el controlador de detección de excepción, los tipos de excepción deben marcarse como serializables o el depurador de orquestaciones no se detendrá en los puntos de interrupción establecidos.</span><span class="sxs-lookup"><span data-stu-id="09c66-113">If the breakpoint is set at the exception catch handler, the exception types must be marked as serializable, or the orchestration debugger will not stop at the breakpoints you set.</span></span> <span data-ttu-id="09c66-114">Ello se debe a que el depurador de orquestaciones realiza la persistencia en el punto de interrupción. Por lo tanto, cuando hay un objeto no serializable en el estado de la instancia de orquestación, se producirá una excepción de persistencia y, en este caso, también recibirá una excepción DebugBreakPointFailedException.</span><span class="sxs-lookup"><span data-stu-id="09c66-114">This is because of that the orchestration debugger does persistence at the breakpoint, therefore, when there is a non-serializable object in the orchestration instance state, a persistence exception will be thrown, and in this case, you will also receive a DebugBreakPointFailedException exception.</span></span>  
  
## <a name="tracking-a-modified-orchestration"></a><span data-ttu-id="09c66-115">Realizar un seguimiento de una orquestación modificada</span><span class="sxs-lookup"><span data-stu-id="09c66-115">Tracking a modified orchestration</span></span>  
 <span data-ttu-id="09c66-116">Si realiza el seguimiento de una orquestación modificada sin cambiar el número de versión, debe reiniciar todas las instancias de host para las que dio de alta la orquestación.</span><span class="sxs-lookup"><span data-stu-id="09c66-116">If you track an orchestration modified without changing the version number, you must restart all the host instances to which the orchestration is enlisted.</span></span> <span data-ttu-id="09c66-117">Esto garantiza que cualquier cambio de la forma en la versión implementada recientemente se muestra correctamente, al ir avanzando por el depurador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="09c66-117">This insures that any shape change in the newly deployed version displays correctly, as you step through the Orchestration Debugger.</span></span>  
  
## <a name="tracking-simple-types"></a><span data-ttu-id="09c66-118">Realizar el seguimiento de tipos simples</span><span class="sxs-lookup"><span data-stu-id="09c66-118">Tracking simple types</span></span>  
 <span data-ttu-id="09c66-119">El Depurador de orquestaciones solo admite tipos simples.</span><span class="sxs-lookup"><span data-stu-id="09c66-119">The Orchestration Debugger only supports simple types.</span></span> <span data-ttu-id="09c66-120">Por ejemplo, si realiza el seguimiento de un mensaje de varias partes que contiene un objeto .NET, puede ver las propiedades de todas las partes del mensaje, excepto las propiedades del objeto .NET.</span><span class="sxs-lookup"><span data-stu-id="09c66-120">For example, if you track a multipart message that contains a .NET object you can view the properties of all message parts, with the exception of the .NET object properties.</span></span>  
  
 <span data-ttu-id="09c66-121">Cuando una orquestación aparece en estado En punto de interrupción y se inicia el Depurador de orquestaciones, puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="09c66-121">When an orchestration appears in the In Breakpoint state and the Orchestration Debugger starts, you can perform the following actions:</span></span>  
  
-   <span data-ttu-id="09c66-122">Use la **adjuntar** opción de servicio.</span><span class="sxs-lookup"><span data-stu-id="09c66-122">Use the **Attach** service option.</span></span>  
  
-   <span data-ttu-id="09c66-123">Revise los pasos que ya se han completado.</span><span class="sxs-lookup"><span data-stu-id="09c66-123">Review the steps that have already completed.</span></span>  
  
-   <span data-ttu-id="09c66-124">Consulte el estado de variables y mensajes.</span><span class="sxs-lookup"><span data-stu-id="09c66-124">View the state of variables and messages.</span></span>  
  
-   <span data-ttu-id="09c66-125">Establezca puntos de interrupción adicionales.</span><span class="sxs-lookup"><span data-stu-id="09c66-125">Set additional breakpoints.</span></span>  
  
-   <span data-ttu-id="09c66-126">Seleccione el **continuar servicio** opción.</span><span class="sxs-lookup"><span data-stu-id="09c66-126">Select the **Continue Service** option.</span></span>  
  
-   <span data-ttu-id="09c66-127">Repita los pasos tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="09c66-127">Repeat any steps as required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c66-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="09c66-128">See Also</span></span>  
 <span data-ttu-id="09c66-129">[Modo interactivo en el depurador de orquestaciones](../core/interactive-mode-in-orchestration-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="09c66-129">[Interactive Mode in Orchestration Debugger](../core/interactive-mode-in-orchestration-debugger.md) </span></span>  
 [<span data-ttu-id="09c66-130">Depuración de una orquestación</span><span class="sxs-lookup"><span data-stu-id="09c66-130">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)