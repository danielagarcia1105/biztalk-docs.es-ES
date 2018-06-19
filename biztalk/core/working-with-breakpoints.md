---
title: Trabajar con puntos de interrupción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, breakpoints
- Orchestration Debugger, suspended orchestrations
- Orchestration Debugger, Message Flow view
- Orchestration Debugger, service options
- Message Flow view [Orchestration Debugger]
ms.assetid: aad1a2b0-d705-49cd-85f7-b0ab2e473bcc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60e9cee77f105b132438e621651ee90c0090c1be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289212"
---
# <a name="working-with-breakpoints"></a><span data-ttu-id="e4f4e-102">Trabajar con puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="e4f4e-102">Working with Breakpoints</span></span>
<span data-ttu-id="e4f4e-103">Puede establecer puntos de interrupción si se conecta a una orquestación suspendida o establece un punto de interrupción en una clase.</span><span class="sxs-lookup"><span data-stu-id="e4f4e-103">You can set breakpoints by attaching to a suspended orchestration, or by setting a breakpoint on a class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4f4e-104">Si anula la implementación de un ensamblado, la base de datos mantiene la información del punto de interrupción y las opciones de seguimiento de ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e4f4e-104">When you undeploy an assembly, the database maintains the tracking options and breakpoint information for that assembly.</span></span> <span data-ttu-id="e4f4e-105">Si a continuación vuelve a implantar el mismo ensamblado, se restauran la información del punto de interrupción y las opciones de ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e4f4e-105">If you subsequently deploy the same assembly again, the options and breakpoint information for that assembly are restored.</span></span>  
  
### <a name="to-attach-to-a-suspended-orchestration"></a><span data-ttu-id="e4f4e-106">Para conectarse a una orquestación suspendida</span><span class="sxs-lookup"><span data-stu-id="e4f4e-106">To attach to a suspended orchestration</span></span>  
  
1.  <span data-ttu-id="e4f4e-107">Seleccione una orquestación suspendida automáticamente mediante una forma de suspensión y luego continúe en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="e4f4e-107">Select an automatically suspended orchestration using a suspend shape, and then go to Step 3.</span></span>  
  
2.  <span data-ttu-id="e4f4e-108">Actualice la vista para comprobar que la instancia aparece en estado de suspensión.</span><span class="sxs-lookup"><span data-stu-id="e4f4e-108">Refresh the view to check that the instance now appears in a Suspended state.</span></span>  
  
3.  <span data-ttu-id="e4f4e-109">Haga clic en **reanudar en depuración**.</span><span class="sxs-lookup"><span data-stu-id="e4f4e-109">Click **Resume in Debug**.</span></span>  
  
     <span data-ttu-id="e4f4e-110">La orquestación se reanuda en un estado En punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e4f4e-110">The orchestration resumes in an In Breakpoint state.</span></span> <span data-ttu-id="e4f4e-111">Ahora puede depurar interactivamente.</span><span class="sxs-lookup"><span data-stu-id="e4f4e-111">You can now debug interactively.</span></span>  
  
### <a name="to-switch-to-the-message-flow-view"></a><span data-ttu-id="e4f4e-112">Para pasar a la vista Flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="e4f4e-112">To switch to the Message Flow view</span></span>  
  
-   <span data-ttu-id="e4f4e-113">Haga clic en una celda de la lista de resultados y seleccione **flujo de mensajes** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="e4f4e-113">Right-click a cell in the Results list and select **Message Flow** from the shortcut menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f4e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4f4e-114">See Also</span></span>  
 [<span data-ttu-id="e4f4e-115">Trabajar con la vista depurador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="e4f4e-115">Working with the Orchestration Debugger View</span></span>](../core/working-with-the-orchestration-debugger-view.md)