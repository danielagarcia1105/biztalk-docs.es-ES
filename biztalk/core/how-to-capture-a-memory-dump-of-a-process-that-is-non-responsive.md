---
title: Cómo capturar un volcado de memoria de un proceso que no responde | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad53376-2fab-4dee-8a6a-a44d157390f2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f79cbc492611a6a1271e45b4198401b3d17452e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016191"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive"></a><span data-ttu-id="002d5-102">Cómo capturar un volcado de memoria de un proceso que no responde</span><span class="sxs-lookup"><span data-stu-id="002d5-102">How to Capture a Memory Dump of a Process that is Non Responsive</span></span>
<span data-ttu-id="002d5-103">El proceso de BizTalk BTSNTSvc.exe se define como **francesa** cuando el proceso parece dejar de responder.</span><span class="sxs-lookup"><span data-stu-id="002d5-103">The BizTalk process BTSNTSvc.exe is defined as **hanging** when the process seems to stop responding.</span></span> <span data-ttu-id="002d5-104">Los síntomas comunes de que un proceso no responde incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="002d5-104">Common symptoms of a process hang include:</span></span>  
  
- <span data-ttu-id="002d5-105">Parece que las orquestaciones dejan de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="002d5-105">Orchestrations appear to stop running.</span></span>  
  
- <span data-ttu-id="002d5-106">Los mensajes no se procesan.</span><span class="sxs-lookup"><span data-stu-id="002d5-106">Messages aren’t being processed.</span></span>  
  
- <span data-ttu-id="002d5-107">Se producen problemas generales de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="002d5-107">General timeout issues occur.</span></span>  
  
- <span data-ttu-id="002d5-108">El proceso de BizTalk BTSNTSvc.exe consume una cantidad inusualmente elevada de ciclos de CPU, tal como se ve en el **procesos** ficha de **el Administrador de tareas**.</span><span class="sxs-lookup"><span data-stu-id="002d5-108">The BizTalk process BTSNTSvc.exe consumes an unusually high amount of CPU cycles as viewed in the **Processes** tab of **Task Manager**.</span></span>  
  
  <span data-ttu-id="002d5-109">Para capturar un volcado de memoria de un proceso BTSNTSvc.exe que no responde, siga los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="002d5-109">To capture a memory dump of a hanging BTSNTSvc.exe process, follow these steps.</span></span>  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-hang-dump"></a><span data-ttu-id="002d5-110">Para configurar la herramienta de diagnósticos de depuración y capturar un volcado que no responde</span><span class="sxs-lookup"><span data-stu-id="002d5-110">To configure the Debug Diagnostics tool to capture a hang dump</span></span>  
  
1.  <span data-ttu-id="002d5-111">Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **todos los programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span><span class="sxs-lookup"><span data-stu-id="002d5-111">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="002d5-112">Si el **Select Rule Type** se muestra el cuadro de diálogo del Asistente para la configuración de reglas, haga clic en el **cancelar** botón.</span><span class="sxs-lookup"><span data-stu-id="002d5-112">If the **Select Rule Type** dialog of the Rules Configuration Wizard is displayed, click the **Cancel** button.</span></span>  
  
3.  <span data-ttu-id="002d5-113">Haga clic en el **procesos** pestaña de la herramienta Debug Diagnostic Tool.</span><span class="sxs-lookup"><span data-stu-id="002d5-113">Click the **Processes** tab of the Debug Diagnostic Tool.</span></span>  
  
4.  <span data-ttu-id="002d5-114">Haga clic en el proceso BTSNTSvc.exe que no responde y seleccione **Create Full Userdump**.</span><span class="sxs-lookup"><span data-stu-id="002d5-114">Right click the unresponsive BTSNTSvc.exe process and select **Create Full Userdump**.</span></span> <span data-ttu-id="002d5-115">De forma predeterminada, un volcado de memoria del proceso se guardará en el directorio \Archivos de programa\IIS Resources\DebugDiag\Logs\Misc del equipo local.</span><span class="sxs-lookup"><span data-stu-id="002d5-115">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\Misc directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002d5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="002d5-116">See Also</span></span>  
 [<span data-ttu-id="002d5-117">Cómo usar diagnósticos de depuración para analizar un volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="002d5-117">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)