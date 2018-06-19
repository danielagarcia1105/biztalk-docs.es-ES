---
title: Cómo capturar un volcado de memoria de un proceso que pierde memoria | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67404919-33a6-40ac-b1c4-09841db12fcf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e1e57a3c4d3c035069c550cdc540de1c88e8880
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969130"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a><span data-ttu-id="0b6b0-102">Cómo capturar un volcado de memoria de un proceso que pierde memoria</span><span class="sxs-lookup"><span data-stu-id="0b6b0-102">How to Capture a Memory Dump of a Process that is Leaking Memory</span></span>
<span data-ttu-id="0b6b0-103">Se dice que el proceso BTSNTSvc.exe de BizTalk pierde memoria cuando no puede liberar la memoria que ya no necesita, lo que reduce, por tanto, la cantidad de memoria disponible con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-103">The BizTalk process BTSNTSvc.exe is defined as having a memory leak when it fails to release memory that it no longer needs, thereby reducing the amount of available memory over time.</span></span> <span data-ttu-id="0b6b0-104">Se puede determinar el uso de memoria del proceso observando el valor en el **uso de memoria** columna de la **procesos** ficha disponible en **el Administrador de tareas**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-104">The memory usage of the process can be determined by viewing the value under the **Mem Usage** column of the **Processes** tab available in **Task Manager**.</span></span> <span data-ttu-id="0b6b0-105">Si el proceso sigue utilizando memoria con el tiempo sin liberarla, el rendimiento general del sistema se verá afectado negativamente.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-105">If the process continues to consume memory over time without releasing memory then overall system performance will be adversely impacted.</span></span>  
  
 <span data-ttu-id="0b6b0-106">Este tema contiene instrucciones para capturar un volcado de memoria de un proceso de BizTalk que parece que pierde memoria mediante una regla o de la captura de un volcado de memoria manual.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-106">This topic contains instructions for capturing a memory dump of a BizTalk process that is suspected of leaking memory by using a Rule or by manually capturing the memory dump.</span></span> <span data-ttu-id="0b6b0-107">Si la pérdida de memoria no es previsible, use el método manual.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-107">Use the manual method of capturing a memory dump if the occurrence of the memory leak is not predictable.</span></span>  
  
### <a name="to-capture-a-memory-dump-of-a-process-that-is-leaking-memory-by-using-a-rule"></a><span data-ttu-id="0b6b0-108">Para capturar un volcado de memoria de un proceso que pierde memoria mediante una regla</span><span class="sxs-lookup"><span data-stu-id="0b6b0-108">To capture a memory dump of a process that is leaking memory by using a rule</span></span>  
  
1.  <span data-ttu-id="0b6b0-109">Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **todos los programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-109">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="0b6b0-110">Si el **Select Rule Type** no se muestra el cuadro de diálogo del Asistente para agregar regla, haga clic en el **herramientas** menú, seleccione **acciones de regla**y haga clic en **Agregar regla**para mostrar el Asistente para agregar regla.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-110">If the **Select Rule Type** dialog of the Add Rule Wizard is not displayed, click the **Tools** menu, select **Rule Actions**, and click **Add Rule** to display the Add Rule Wizard.</span></span>  
  
3.  <span data-ttu-id="0b6b0-111">Seleccione el **Memory and Handle Leak** opción en el **Select Rule Type** cuadro de diálogo y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-111">Select the **Memory and Handle Leak** option in the **Select Rule Type** dialog and click **Next**.</span></span>  
  
4.  <span data-ttu-id="0b6b0-112">Seleccione el proceso BTSNTSvc.exe que parece que pierde memoria y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-112">Select the BTSNTSvc.exe process that is suspected of leaking memory and click **Next**.</span></span>  
  
5.  <span data-ttu-id="0b6b0-113">En el **Configure Tracking Duration** diálogo siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0b6b0-113">In the **Configure Tracking Duration** dialog follow these steps:</span></span>  
  
    1.  <span data-ttu-id="0b6b0-114">Si el aumento de memoria del proceso observado se produce inmediatamente, seleccione la opción **Iniciar seguimiento inmediatamente cuando se activa la regla de la memoria**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-114">If the observed process memory growth occurs immediately, check the option to **Start memory tracking immediately when rule is activated**.</span></span> <span data-ttu-id="0b6b0-115">Si el aumento de memoria del proceso observado no se produce inmediatamente, especifique un número adecuado de minutos en el **tiempo de preparación** cuadro de texto después del cual se iniciará el seguimiento de la memoria.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-115">If the observed process memory growth doesn't occur immediately, specify an appropriate number of minutes in the **Warm-up time** text box after which memory tracking will start.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0b6b0-116">El aumento de memoria del proceso observado puede no producirse inmediatamente si la pérdida de memoria ocurre al cargar un componente concreto en la memoria, por ejemplo, cuando una orquestación de BizTalk hace referencia a un componente externo.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-116">The observed process memory growth may not occur immediately if the memory leak is caused when loading a particular component into memory, for example when a BizTalk orchestration references an external component.</span></span>  
  
    2.  <span data-ttu-id="0b6b0-117">Especifique un número adecuado de minutos en el **seguimiento tiempo** cuadro de texto después del cual se detendrá el seguimiento de la memoria.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-117">Specify an appropriate number of minutes in the **Tracking time** text box after which memory tracking will stop.</span></span> <span data-ttu-id="0b6b0-118">Debe ser un número de minutos suficiente para reproducir la pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-118">This should be a number of minutes long enough to reproduce the memory leak.</span></span> <span data-ttu-id="0b6b0-119">Transcurrido este período, se capturará un volcado de memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-119">A memory dump of the process will be captured after this time period has elapsed.</span></span>  
  
    3.  <span data-ttu-id="0b6b0-120">Active la opción para **crear automáticamente un bloqueo de reglas para obtener userdump al salir del proceso inesperado**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-120">Check the option to **Auto-create a crash rule to get userdump on unexpected process exit**.</span></span>  
  
    4.  <span data-ttu-id="0b6b0-121">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-121">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="0b6b0-122">En el **seleccione Dump Location And Rule Name** diálogo haga clic en **siguiente** para aceptar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-122">In the **Select Dump Location And Rule Name** dialog click **Next** to accept the default values.</span></span>  
  
7.  <span data-ttu-id="0b6b0-123">En el **Rule Completed** diálogo haga clic en **finalizar** para aceptar el valor predeterminado de **activar la regla ahora**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-123">In the **Rule Completed** dialog click **Finish** to accept the default value of **Activate the rule now**.</span></span>  
  
8.  <span data-ttu-id="0b6b0-124">De forma predeterminada, se guardará un volcado de memoria del proceso para el \Program Files\IIS Resources\DebugDiag\Logs\\<*nombre de regla de bloqueo* \> directorio del equipo local después de los intervalos de tiempo se especifica en el **Configure Tracking Duration** ha transcurrido el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-124">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\\<*name of crash rule*\> directory of the local computer after the time intervals specified in the **Configure Tracking Duration** dialog has elapsed.</span></span>  
  
### <a name="to-manually-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a><span data-ttu-id="0b6b0-125">Para capturar manualmente un volcado de memoria de un proceso que pierde memoria</span><span class="sxs-lookup"><span data-stu-id="0b6b0-125">To manually capture a memory dump of a process that is leaking memory</span></span>  
  
1.  <span data-ttu-id="0b6b0-126">Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **todos los programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-126">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="0b6b0-127">Si el **Select Rule Type** se muestra el cuadro de diálogo del Asistente para agregar regla, haga clic en **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-127">If the **Select Rule Type** dialog of the Add Rule Wizard is displayed, click **Cancel**.</span></span>  
  
3.  <span data-ttu-id="0b6b0-128">Haga clic para seleccionar la **procesos** ficha de la herramienta de diagnóstico de depuración.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-128">Click to select the **Processes** tab of the Debug Diagnostic Tool.</span></span>  
  
4.  <span data-ttu-id="0b6b0-129">Haga clic en el proceso BTSNTSvc.exe que parece que pierde memoria y haga clic en **Monitor For Leaks**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-129">Right-click the BTSNTSvc.exe process that is suspected of leaking memory and click **Monitor For Leaks**.</span></span>  
  
5.  <span data-ttu-id="0b6b0-130">Supervisar el uso de memoria del proceso en **el Administrador de tareas** y cuando el uso de memoria del proceso aproxima 60-80% de la memoria disponible en el equipo de BizTalk, capture manualmente un volcado de memoria del proceso haciendo clic en el proceso y seleccionando la opción de **Create Full Userdump**.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-130">Monitor the memory usage of the process in **Task Manager** and when the memory usage of the process approaches 60-80% of the memory available on the BizTalk computer; manually capture a memory dump of the process by right-clicking the process and selecting the option to **Create Full Userdump**.</span></span>  
  
6.  <span data-ttu-id="0b6b0-131">De forma predeterminada, un volcado de memoria del proceso se guardará en el directorio \Archivos de programa\IIS Resources\DebugDiag\Logs\Misc\ del equipo local.</span><span class="sxs-lookup"><span data-stu-id="0b6b0-131">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\Misc\ directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6b0-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b6b0-132">See Also</span></span>  
 [<span data-ttu-id="0b6b0-133">Cómo usar diagnósticos de depuración para analizar un volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="0b6b0-133">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)