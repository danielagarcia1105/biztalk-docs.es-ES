---
title: "Cómo capturar un volcado de memoria de un proceso que no responde | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ad53376-2fab-4dee-8a6a-a44d157390f2
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 520921010a8bbfd73de8c3b305a1270ca8363c46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive"></a><span data-ttu-id="79408-102">Cómo capturar un volcado de memoria de un proceso que no responde</span><span class="sxs-lookup"><span data-stu-id="79408-102">How to Capture a Memory Dump of a Process that is Non Responsive</span></span>
<span data-ttu-id="79408-103">El proceso de BizTalk BTSNTSvc.exe se define como **francesa** cuando el proceso parece que deja de responder.</span><span class="sxs-lookup"><span data-stu-id="79408-103">The BizTalk process BTSNTSvc.exe is defined as **hanging** when the process seems to stop responding.</span></span> <span data-ttu-id="79408-104">Los síntomas comunes de que un proceso no responde incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="79408-104">Common symptoms of a process hang include:</span></span>  
  
-   <span data-ttu-id="79408-105">Parece que las orquestaciones dejan de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="79408-105">Orchestrations appear to stop running.</span></span>  
  
-   <span data-ttu-id="79408-106">Los mensajes no se procesan.</span><span class="sxs-lookup"><span data-stu-id="79408-106">Messages aren’t being processed.</span></span>  
  
-   <span data-ttu-id="79408-107">Se producen problemas generales de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="79408-107">General timeout issues occur.</span></span>  
  
-   <span data-ttu-id="79408-108">El proceso de BizTalk BTSNTSvc.exe consume una cantidad inusualmente elevada de ciclos de CPU tal como se ve en el **procesos** ficha de **el Administrador de tareas**.</span><span class="sxs-lookup"><span data-stu-id="79408-108">The BizTalk process BTSNTSvc.exe consumes an unusually high amount of CPU cycles as viewed in the **Processes** tab of **Task Manager**.</span></span>  
  
 <span data-ttu-id="79408-109">Para capturar un volcado de memoria de un proceso BTSNTSvc.exe que no responde, siga los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="79408-109">To capture a memory dump of a hanging BTSNTSvc.exe process, follow these steps.</span></span>  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-hang-dump"></a><span data-ttu-id="79408-110">Para configurar la herramienta de diagnósticos de depuración y capturar un volcado que no responde</span><span class="sxs-lookup"><span data-stu-id="79408-110">To configure the Debug Diagnostics tool to capture a hang dump</span></span>  
  
1.  <span data-ttu-id="79408-111">Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **todos los programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span><span class="sxs-lookup"><span data-stu-id="79408-111">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="79408-112">Si el **Select Rule Type** se muestra el cuadro de diálogo del Asistente para la configuración de reglas, haga clic en el **cancelar** botón.</span><span class="sxs-lookup"><span data-stu-id="79408-112">If the **Select Rule Type** dialog of the Rules Configuration Wizard is displayed, click the **Cancel** button.</span></span>  
  
3.  <span data-ttu-id="79408-113">Haga clic en el **procesos** ficha de la herramienta de diagnóstico de depuración.</span><span class="sxs-lookup"><span data-stu-id="79408-113">Click the **Processes** tab of the Debug Diagnostic Tool.</span></span>  
  
4.  <span data-ttu-id="79408-114">Haga clic en el proceso BTSNTSvc.exe que no responde y seleccione **Create Full Userdump**.</span><span class="sxs-lookup"><span data-stu-id="79408-114">Right click the unresponsive BTSNTSvc.exe process and select **Create Full Userdump**.</span></span> <span data-ttu-id="79408-115">De forma predeterminada, un volcado de memoria del proceso se guardará en el directorio \Archivos de programa\IIS Resources\DebugDiag\Logs\Misc del equipo local.</span><span class="sxs-lookup"><span data-stu-id="79408-115">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\Misc directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79408-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="79408-116">See Also</span></span>  
 [<span data-ttu-id="79408-117">Cómo usar diagnósticos de depuración para analizar un volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="79408-117">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)