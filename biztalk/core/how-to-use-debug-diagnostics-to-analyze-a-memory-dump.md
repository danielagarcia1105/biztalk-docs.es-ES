---
title: "Cómo usar diagnósticos de depuración para analizar un volcado de memoria | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 986a91a7-feab-4014-bbd5-e8b966b8b841
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccc0faf72c9123ab7a501af8520f273e8c528b8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-debug-diagnostics-to-analyze-a-memory-dump"></a><span data-ttu-id="605a7-102">Cómo usar diagnósticos de depuración para analizar un volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="605a7-102">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>
<span data-ttu-id="605a7-103">El diagnóstico de IIS **Debug Diagnostics Tool** incluye una característica que puede proporcionar un análisis básico de un archivo de volcado de memoria capturado.</span><span class="sxs-lookup"><span data-stu-id="605a7-103">The IIS Diagnostics **Debug Diagnostics Tool** includes a feature that can provide a basic analysis of a captured memory dump file.</span></span> <span data-ttu-id="605a7-104">Para realizar un análisis de un archivo de volcado de la memoria, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="605a7-104">To perform an analysis of a memory dump file follow these steps.</span></span>  
  
### <a name="to-analyze-the-dump-file"></a><span data-ttu-id="605a7-105">Para analizar el archivo de volcado</span><span class="sxs-lookup"><span data-stu-id="605a7-105">To analyze the dump file</span></span>  
  
1.  <span data-ttu-id="605a7-106">Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**,  **Herramienta de diagnóstico 1.0 de depuración**.</span><span class="sxs-lookup"><span data-stu-id="605a7-106">Launch the Debug Diagnostics tool from **Start**, **Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="605a7-107">Haga clic en el **análisis avanzado** ficha.</span><span class="sxs-lookup"><span data-stu-id="605a7-107">Click the **Advanced Analysis** tab.</span></span>  
  
3.  <span data-ttu-id="605a7-108">En **secuencias de comandos de análisis disponibles** haga clic para seleccionar **analizadores de bloqueo/bloqueo** para analizar un volcado de bloqueo o dejar de responder o haga clic para seleccionar **análisis de presión de memoria** para analizar un objeto de memoria volcado de memoria de un proceso parece que pierde memoria.</span><span class="sxs-lookup"><span data-stu-id="605a7-108">Under **Available Analysis Scripts** click to select **Crash/Hang Analyzers** to analyze a crash/hang dump or click to select **Memory Pressure Analysis** to analyze a memory dump of a process suspected of leaking memory.</span></span>  
  
4.  <span data-ttu-id="605a7-109">Haga clic en el **agregar archivos de datos** botón para buscar el archivo de volcado de memoria generado y haga clic en el **abiertos** botón para agregar el archivo de volcado de memoria a la lista de posibles de archivos de datos que se va a analizar.</span><span class="sxs-lookup"><span data-stu-id="605a7-109">Click the **Add Data Files** button to browse to the generated dump file and click the **Open** button to add the dump file to the possible list of data files to be analyzed.</span></span>  
  
5.  <span data-ttu-id="605a7-110">Haga clic para seleccionar el archivo de volcado que se ha agregado.</span><span class="sxs-lookup"><span data-stu-id="605a7-110">Click to select the dump file that was added.</span></span>  
  
6.  <span data-ttu-id="605a7-111">Haga clic en el **iniciar análisis** botón.</span><span class="sxs-lookup"><span data-stu-id="605a7-111">Click the **Start Analysis** button.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="605a7-112">El analizador intentará localizar y descargar los archivos de símbolos adecuados de Internet si no están instalados en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="605a7-112">The analyzer attempts to locate and download the appropriate symbol files from the internet if the symbol files are not installed on the local computer.</span></span> <span data-ttu-id="605a7-113">Si se ejecuta código personalizado en el proceso BTSNTSvc.exe, actualice el **símbolo Buscar ruta de acceso para la depuración** opción disponible en la **rutas de búsqueda y de carpeta** pestaña de la **opciones & Configuración de** cuadro de diálogo para incluir los archivos de símbolos adecuados.</span><span class="sxs-lookup"><span data-stu-id="605a7-113">If custom code is being executed in the BTSNTSvc.exe process, update the **Symbol Search Path For Debugging** option available in the **Folder And Search Paths** tab of the **Options & Settings** dialog to include the appropriate symbol files.</span></span> <span data-ttu-id="605a7-114">Haga clic en el **herramientas** menú y seleccione **opciones y configuración** para mostrar la **opciones y configuración** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="605a7-114">Click the **Tools** menu and select **Options And Settings** to display the **Options & Settings** dialog.</span></span>  
  
7.  <span data-ttu-id="605a7-115">Una vez completado el análisis, se genera un informe en formato de archivo .mht y se muestra en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="605a7-115">Once the analysis is complete a report is generated in .mht file format and displayed in Internet Explorer.</span></span> <span data-ttu-id="605a7-116">De forma predeterminada, este informe se guardará en el directorio \Archivos de programa\IIS Resources\DebugDiag\Reports del equipo local.</span><span class="sxs-lookup"><span data-stu-id="605a7-116">By default this report is saved to the \Program Files\IIS Resources\DebugDiag\Reports directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="605a7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="605a7-117">See Also</span></span>  
 [<span data-ttu-id="605a7-118">Cómo capturar un volcado de memoria de un proceso de BizTalk</span><span class="sxs-lookup"><span data-stu-id="605a7-118">How to Capture a Memory Dump of a BizTalk Process</span></span>](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)