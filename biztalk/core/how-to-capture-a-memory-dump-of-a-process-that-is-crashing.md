---
title: Cómo capturar un volcado de memoria de un proceso que está bloqueado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f436b72-2b6a-4519-acc3-e7ba978651fe
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e87664180b7ad4d5fdcd121542974a08b8634d55
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969570"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-crashing"></a><span data-ttu-id="891b5-102">Cómo capturar un volcado de memoria de un proceso que está bloqueado</span><span class="sxs-lookup"><span data-stu-id="891b5-102">How to Capture a Memory Dump of a Process that is Crashing</span></span>
<span data-ttu-id="891b5-103">El proceso de BizTalk BTSNTSvc.exe se define como **bloqueo** cuando finaliza el proceso de forma inesperada por Windows.</span><span class="sxs-lookup"><span data-stu-id="891b5-103">The BizTalk process BTSNTSvc.exe is defined as **crashing** when the process is unexpectedly terminated by Windows.</span></span> <span data-ttu-id="891b5-104">El bloqueo suele provocarlo una excepción no controlada en el proceso, como una infracción de acceso o un desbordamiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="891b5-104">A crash is typically caused by an unhandled exception in the process such as an access violation or a stack overflow.</span></span> <span data-ttu-id="891b5-105">En estas situaciones, las ventanas de forma predeterminada depurador, recuperación ante desastres. Watson (drwtsn32.exe) detecta la excepción y finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="891b5-105">In these situations, the Windows default debugger, Dr. Watson (drwtsn32.exe) catches the exception and terminates the process.</span></span>  
  
 <span data-ttu-id="891b5-106">Para capturar un volcado de memoria de un proceso que se está bloqueando, configure la herramienta de diagnósticos de depuración para capturar la excepción no controlada siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="891b5-106">To capture a memory dump of a process that is crashing, configure the Debug Diagnostics tool to catch the unhandled exception by following these steps:</span></span>  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-crash-dump"></a><span data-ttu-id="891b5-107">Para configurar la herramienta de diagnósticos de depuración y capturar un volcado</span><span class="sxs-lookup"><span data-stu-id="891b5-107">To configure the Debug Diagnostics tool to capture a crash dump</span></span>  
  
1.  <span data-ttu-id="891b5-108">Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **todos los programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span><span class="sxs-lookup"><span data-stu-id="891b5-108">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="891b5-109">Si el **Select Rule Type** no se muestra el cuadro de diálogo del Asistente para agregar regla, haga clic en el **herramientas** menú, seleccione **acciones de regla**y haga clic en **Agregar regla**para mostrar el Asistente para agregar regla.</span><span class="sxs-lookup"><span data-stu-id="891b5-109">If the **Select Rule Type** dialog of the Add Rule Wizard is not displayed, click the **Tools** menu, select **Rule Actions**, and click **Add Rule** to display the Add Rule Wizard.</span></span>  
  
3.  <span data-ttu-id="891b5-110">Seleccione el **bloqueo** opción en el **Select Rule Type** cuadro de diálogo y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="891b5-110">Select the **Crash** option in the **Select Rule Type** dialog and click **Next**.</span></span>  
  
4.  <span data-ttu-id="891b5-111">Seleccione **un proceso específico** en el **Select Target Type** cuadro de diálogo y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="891b5-111">Select **A specific process** in the **Select Target Type** dialog and click **Next**.</span></span>  
  
5.  <span data-ttu-id="891b5-112">Seleccione el proceso BTSNTSvc.exe que está bloqueando y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="891b5-112">Select the BTSNTSvc.exe process that is crashing and click **Next**.</span></span>  
  
6.  <span data-ttu-id="891b5-113">En el **configuración avanzada de** diálogo haga clic en **siguiente** para aceptar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="891b5-113">In the **Advanced Configuration** dialog click **Next** to accept the default values.</span></span>  
  
7.  <span data-ttu-id="891b5-114">En el **seleccione Dump Location And Rule Name** diálogo haga clic en **siguiente** para aceptar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="891b5-114">In the **Select Dump Location And Rule Name** dialog click **Next** to accept the default values.</span></span>  
  
8.  <span data-ttu-id="891b5-115">En el **Rule Completed** diálogo haga clic en **finalizar** para aceptar el valor predeterminado de **activar la regla ahora**.</span><span class="sxs-lookup"><span data-stu-id="891b5-115">In the **Rule Completed** dialog click **Finish** to accept the default value of **Activate the rule now**.</span></span>  
  
9. <span data-ttu-id="891b5-116">De forma predeterminada, se guardará un volcado de memoria del proceso para el \Program Files\IIS Resources\DebugDiag\Logs\\<*nombre de regla de bloqueo* \> directorio del equipo local la próxima vez que un se produce una excepción no controlada en el proceso.</span><span class="sxs-lookup"><span data-stu-id="891b5-116">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\\<*name of crash rule*\> directory of the local computer the next time that an unhandled exception occurs in the process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891b5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="891b5-117">See Also</span></span>  
 [<span data-ttu-id="891b5-118">Cómo usar diagnósticos de depuración para analizar un volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="891b5-118">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)