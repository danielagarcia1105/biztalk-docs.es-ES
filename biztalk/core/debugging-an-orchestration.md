---
title: "Depuración de una orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging, Orchestration Debugger
- debugging, orchestrations
- Orchestration Debugger, about Orchestration Debugger
- Orchestrations Debugger
- orchestrations, debugging
- debugging, HAT
- HAT, debugging
ms.assetid: aae99cfd-d3dd-41c8-ae7a-b2733352cd69
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c231513ad75520fcadd88e5dd7d88104ddeeced5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="debugging-an-orchestration"></a><span data-ttu-id="d2cad-102">Depuración de una orquestación</span><span class="sxs-lookup"><span data-stu-id="d2cad-102">Debugging an Orchestration</span></span>
<span data-ttu-id="d2cad-103">El Depurador de orquestaciones le permite realizar el seguimiento de la actividad de una actividad de una instancia de orquestación única forma a forma.</span><span class="sxs-lookup"><span data-stu-id="d2cad-103">The Orchestration Debugger enables you to track the activity of a single orchestration instance on a shape-by-shape basis.</span></span> <span data-ttu-id="d2cad-104">Muestra una vista procesada de la orquestación creada en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="d2cad-104">It displays a rendered view of the orchestration created in the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="d2cad-105">Se obtiene acceso al Depurador de orquestaciones en la página de información general de grupo de la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d2cad-105">You access the Orchestration Debugger in the Group Overview Page in the BizTalk Server Administration Console.</span></span>  <span data-ttu-id="d2cad-106">Para ello, en los resultados de una consulta de seguimiento, haga clic con el botón secundario en cualquier instancia de servicio o mensaje asociada a un tipo de orquestación para abrir el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="d2cad-106">This is done from the output of a tracking query through a shortcut menu by right-clicking any service or message instance associated with an orchestration type.</span></span> <span data-ttu-id="d2cad-107">Cuando se encuentre en esta página, puede cambiar entre la vista Depurador de orquestaciones y Flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d2cad-107">Once you're in i this page, you can switch back and forth between the Orchestration Debugger and the Message Flow view.</span></span>  
  
 <span data-ttu-id="d2cad-108">El Depurador de orquestaciones proporciona la funcionalidad siguiente:</span><span class="sxs-lookup"><span data-stu-id="d2cad-108">The Orchestration Debugger provides the following functionality:</span></span>  
  
-   <span data-ttu-id="d2cad-109">Muestra una vista procesada de la orquestación en la que puede reproducir todos los pasos de procesamiento para esa orquestación en particular.</span><span class="sxs-lookup"><span data-stu-id="d2cad-109">Displays a rendered view of the orchestration in which you can replay each processing step for that particular orchestration.</span></span>  
  
-   <span data-ttu-id="d2cad-110">Le permite establecer puntos de interrupción antes de cualquier forma de orquestación y continuar con la ejecución.</span><span class="sxs-lookup"><span data-stu-id="d2cad-110">Enables you to set breakpoints before any orchestration shape and continue execution.</span></span>  
  
-   <span data-ttu-id="d2cad-111">Le permite analizar variables y datos de mensaje específicos.</span><span class="sxs-lookup"><span data-stu-id="d2cad-111">Enables you to look at specific variables and message data.</span></span>  
  
-   <span data-ttu-id="d2cad-112">Habilita automáticamente todas las opciones de seguimiento de una instancia de orquestación determinada cuando ésta se abre en el Depurador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="d2cad-112">Automatically enables all of the tracking options for a particular orchestration instance when that instance opens in the Orchestration Debugger.</span></span>  
  
-   <span data-ttu-id="d2cad-113">Le ofrece la posibilidad de continuar, reanudar en el modo de depuración y finalizar la instancia de orquestación determinada.</span><span class="sxs-lookup"><span data-stu-id="d2cad-113">It gives you the ability to continue, resume in debug, and terminate the particular orchestration instance.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d2cad-114">Si anula la implementación de un ensamblado, la base de datos mantiene las opciones de seguimiento y la información del punto de interrupción de dicho ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d2cad-114">When you undeploy an assembly, the database maintains the tracking options and breakpoint information for the undeployed assembly.</span></span> <span data-ttu-id="d2cad-115">Si a continuación vuelve a implantar el mismo ensamblado, se restauran las opciones y la información de punto de interrupción para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d2cad-115">If you subsequently deploy the same assembly, the options and breakpoint information for that assembly are restored.</span></span>  
  
 <span data-ttu-id="d2cad-116">Los dos modos de utilización del Depurador de orquestaciones son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d2cad-116">The two modes for using the Orchestration Debugger are:</span></span>  
  
-   [<span data-ttu-id="d2cad-117">Modo de informe en el depurador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="d2cad-117">Reporting Mode in Orchestration Debugger</span></span>](../core/reporting-mode-in-orchestration-debugger.md)  
  
-   [<span data-ttu-id="d2cad-118">Modo interactivo en el depurador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="d2cad-118">Interactive Mode in Orchestration Debugger</span></span>](../core/interactive-mode-in-orchestration-debugger.md)  
  
 <span data-ttu-id="d2cad-119">Las funciones varían en función del estado del servicio.</span><span class="sxs-lookup"><span data-stu-id="d2cad-119">The capabilities differ depending on the state of the service.</span></span> <span data-ttu-id="d2cad-120">Puede realizar una depuración interactiva al invocar cualquier instancia de servicio que se encuentre en estado En punto de interrupción desde cualquier vista.</span><span class="sxs-lookup"><span data-stu-id="d2cad-120">You can perform interactive debugging by invoking any service instance currently in the In Breakpoint state, from any view.</span></span> <span data-ttu-id="d2cad-121">Para obtener información sobre la depuración de una orquestación, consulte [cómo invocar el depurador de orquestaciones y las vistas de flujo de mensajes](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md).</span><span class="sxs-lookup"><span data-stu-id="d2cad-121">For information about debugging an orchestration, see [How to Invoke the Orchestration Debugger and the Message Flow Views](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d2cad-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d2cad-122">In This Section</span></span>  
  
-   [<span data-ttu-id="d2cad-123">Interfaz de usuario del depurador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="d2cad-123">Orchestration Debugger User Interface</span></span>](../core/orchestration-debugger-user-interface.md)  
  
-   [<span data-ttu-id="d2cad-124">Consideraciones al utilizar el depurador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="d2cad-124">Considerations when Using Orchestration Debugger</span></span>](../core/considerations-when-using-orchestration-debugger.md)  
  
-   [<span data-ttu-id="d2cad-125">Trabajar con la vista depurador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="d2cad-125">Working with the Orchestration Debugger View</span></span>](../core/working-with-the-orchestration-debugger-view.md)