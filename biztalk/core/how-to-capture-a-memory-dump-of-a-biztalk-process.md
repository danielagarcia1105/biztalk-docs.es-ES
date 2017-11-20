---
title: "Cómo capturar un volcado de memoria de un proceso de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8053fcf3-b331-4245-b3c3-21290463e0c0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f87ad0f4a3eb3a49ea789d45a707bbc8b46cb4c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-capture-a-memory-dump-of-a-biztalk-process"></a><span data-ttu-id="7865a-102">Cómo capturar un volcado de memoria de un proceso de BizTalk</span><span class="sxs-lookup"><span data-stu-id="7865a-102">How to Capture a Memory Dump of a BizTalk Process</span></span>
<span data-ttu-id="7865a-103">Es posible que, en determinadas circunstancias, sea necesario capturar un volcado de memoria de un proceso que se está ejecutando en un servidor de BizTalk Server para realizar un análisis en profundidad del proceso.</span><span class="sxs-lookup"><span data-stu-id="7865a-103">Under certain circumstances it may be necessary to capture a memory dump of a process running on a BizTalk Server to perform an in depth analysis of the process.</span></span> <span data-ttu-id="7865a-104">A continuación se indican las situaciones que pueden requerir el análisis de un volcado de memoria:</span><span class="sxs-lookup"><span data-stu-id="7865a-104">Situations that may require analysis of a memory dump include the following:</span></span>  
  
-   <span data-ttu-id="7865a-105">Cuando no responde un proceso.</span><span class="sxs-lookup"><span data-stu-id="7865a-105">When a process is unresponsive.</span></span>  
  
-   <span data-ttu-id="7865a-106">Cuando un proceso está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="7865a-106">When a process is crashing.</span></span>  
  
-   <span data-ttu-id="7865a-107">Cuando un proceso pierde memoria.</span><span class="sxs-lookup"><span data-stu-id="7865a-107">When a process leaks memory.</span></span>  
  
 <span data-ttu-id="7865a-108">En esta sección se incluyen los pasos que se deberían seguir para capturar el tipo adecuado de volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="7865a-108">This section includes the steps that should be followed to capture the appropriate type of memory dump.</span></span>  
  
## <a name="installation-of-the-iis-diagnostics-toolkit"></a><span data-ttu-id="7865a-109">Instalación del Kit de herramientas de diagnóstico de IIS</span><span class="sxs-lookup"><span data-stu-id="7865a-109">Installation of the IIS Diagnostics Toolkit</span></span>  
 <span data-ttu-id="7865a-110">Cada uno de los temas de esta sección requiere el uso de la **Debug Diagnostics Tool** del Kit de herramientas de diagnóstico de IIS para capturar un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="7865a-110">Each of the topics in this section requires the use of the **Debug Diagnostics Tool** of the IIS Diagnostics Toolkit to capture a memory dump.</span></span> <span data-ttu-id="7865a-111">Para instalar el **Debug Diagnostics Tool** del Kit de herramientas de diagnóstico de IIS, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7865a-111">To install the **Debug Diagnostics Tool** of the IIS Diagnostics Toolkit follow these steps:</span></span>  
  
1.  <span data-ttu-id="7865a-112">Descargar el Kit de herramientas de diagnóstico IIS de [herramientas de diagnóstico de los servicios de Internet Information Server](http://go.microsoft.com/fwlink/?LinkId=64426).</span><span class="sxs-lookup"><span data-stu-id="7865a-112">Download the IIS Diagnostics Toolkit from [Internet Information Services Diagnostic Tools](http://go.microsoft.com/fwlink/?LinkId=64426).</span></span>  
  
2.  <span data-ttu-id="7865a-113">Haga doble clic en el **iisdiag.msi** paquete para iniciar el programa de instalación del Kit de herramientas de diagnóstico de IIS y elija la **personalizado** tipo de instalación.</span><span class="sxs-lookup"><span data-stu-id="7865a-113">Double-click the **iisdiag.msi** package to start the IIS Diagnostics Toolkit setup program and choose the **Custom** setup type.</span></span>  
  
3.  <span data-ttu-id="7865a-114">En el **personalizada** cuadro de diálogo, asegúrese de que la opción para la **Debug Diagnostics Tool 1.0** está habilitada y complete los pasos del programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="7865a-114">In the **Custom Setup** dialog, ensure that the option for the **Debug Diagnostics Tool 1.0** is enabled and complete the steps in the setup program.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7865a-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7865a-115">In This Section</span></span>  
  
-   [<span data-ttu-id="7865a-116">Cómo capturar un volcado de memoria de un proceso que no responde</span><span class="sxs-lookup"><span data-stu-id="7865a-116">How to Capture a Memory Dump of a Process that is Non Responsive</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive.md)  
  
-   [<span data-ttu-id="7865a-117">Cómo capturar un volcado de memoria de un proceso que está bloqueado</span><span class="sxs-lookup"><span data-stu-id="7865a-117">How to Capture a Memory Dump of a Process that is Crashing</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-crashing.md)  
  
-   [<span data-ttu-id="7865a-118">Cómo capturar un volcado de memoria de un proceso que pierde memoria</span><span class="sxs-lookup"><span data-stu-id="7865a-118">How to Capture a Memory Dump of a Process that is Leaking Memory</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory.md)  
  
-   [<span data-ttu-id="7865a-119">Cómo usar diagnósticos de depuración para analizar un volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="7865a-119">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)