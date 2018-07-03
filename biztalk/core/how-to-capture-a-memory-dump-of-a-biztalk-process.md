---
title: Cómo capturar un volcado de memoria de un proceso de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8053fcf3-b331-4245-b3c3-21290463e0c0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3643dab17f8d1592f1e5fddce30aa12e537c817
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969141"
---
# <a name="how-to-capture-a-memory-dump-of-a-biztalk-process"></a><span data-ttu-id="430e1-102">Cómo capturar un volcado de memoria de un proceso de BizTalk</span><span class="sxs-lookup"><span data-stu-id="430e1-102">How to Capture a Memory Dump of a BizTalk Process</span></span>
<span data-ttu-id="430e1-103">Es posible que, en determinadas circunstancias, sea necesario capturar un volcado de memoria de un proceso que se está ejecutando en un servidor de BizTalk Server para realizar un análisis en profundidad del proceso.</span><span class="sxs-lookup"><span data-stu-id="430e1-103">Under certain circumstances it may be necessary to capture a memory dump of a process running on a BizTalk Server to perform an in depth analysis of the process.</span></span> <span data-ttu-id="430e1-104">A continuación se indican las situaciones que pueden requerir el análisis de un volcado de memoria:</span><span class="sxs-lookup"><span data-stu-id="430e1-104">Situations that may require analysis of a memory dump include the following:</span></span>  
  
- <span data-ttu-id="430e1-105">Cuando no responde un proceso.</span><span class="sxs-lookup"><span data-stu-id="430e1-105">When a process is unresponsive.</span></span>  
  
- <span data-ttu-id="430e1-106">Cuando un proceso está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="430e1-106">When a process is crashing.</span></span>  
  
- <span data-ttu-id="430e1-107">Cuando un proceso pierde memoria.</span><span class="sxs-lookup"><span data-stu-id="430e1-107">When a process leaks memory.</span></span>  
  
  <span data-ttu-id="430e1-108">En esta sección se incluyen los pasos que se deberían seguir para capturar el tipo adecuado de volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="430e1-108">This section includes the steps that should be followed to capture the appropriate type of memory dump.</span></span>  
  
## <a name="installation-of-the-iis-diagnostics-toolkit"></a><span data-ttu-id="430e1-109">Instalación del Kit de herramientas de diagnóstico de IIS</span><span class="sxs-lookup"><span data-stu-id="430e1-109">Installation of the IIS Diagnostics Toolkit</span></span>  
 <span data-ttu-id="430e1-110">Cada uno de los temas de esta sección requiere el uso de la **Debug Diagnostics Tool** del Kit de herramientas de diagnóstico de IIS para capturar un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="430e1-110">Each of the topics in this section requires the use of the **Debug Diagnostics Tool** of the IIS Diagnostics Toolkit to capture a memory dump.</span></span> <span data-ttu-id="430e1-111">Para instalar el **Debug Diagnostics Tool** del Kit de herramientas de diagnóstico de IIS, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="430e1-111">To install the **Debug Diagnostics Tool** of the IIS Diagnostics Toolkit follow these steps:</span></span>  
  
1.  <span data-ttu-id="430e1-112">Descargue el Kit de herramientas de diagnóstico IIS desde [herramientas de diagnóstico de Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=64426).</span><span class="sxs-lookup"><span data-stu-id="430e1-112">Download the IIS Diagnostics Toolkit from [Internet Information Services Diagnostic Tools](http://go.microsoft.com/fwlink/?LinkId=64426).</span></span>  
  
2.  <span data-ttu-id="430e1-113">Haga doble clic en el **iisdiag.msi** paquete para iniciar el programa de instalación del Kit de herramientas de diagnóstico de IIS y elija el **personalizado** tipo de instalación.</span><span class="sxs-lookup"><span data-stu-id="430e1-113">Double-click the **iisdiag.msi** package to start the IIS Diagnostics Toolkit setup program and choose the **Custom** setup type.</span></span>  
  
3.  <span data-ttu-id="430e1-114">En el **instalación personalizada** cuadro de diálogo, asegúrese de que la opción para la **Debug Diagnostics Tool 1.0** está habilitada y complete los pasos del programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="430e1-114">In the **Custom Setup** dialog, ensure that the option for the **Debug Diagnostics Tool 1.0** is enabled and complete the steps in the setup program.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="430e1-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="430e1-115">In This Section</span></span>  
  
-   [<span data-ttu-id="430e1-116">Cómo capturar un volcado de memoria de un proceso que no responde</span><span class="sxs-lookup"><span data-stu-id="430e1-116">How to Capture a Memory Dump of a Process that is Non Responsive</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive.md)  
  
-   [<span data-ttu-id="430e1-117">Cómo capturar un volcado de memoria de un proceso que está bloqueado</span><span class="sxs-lookup"><span data-stu-id="430e1-117">How to Capture a Memory Dump of a Process that is Crashing</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-crashing.md)  
  
-   [<span data-ttu-id="430e1-118">Cómo capturar un volcado de memoria de un proceso que pierde memoria</span><span class="sxs-lookup"><span data-stu-id="430e1-118">How to Capture a Memory Dump of a Process that is Leaking Memory</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory.md)  
  
-   [<span data-ttu-id="430e1-119">Cómo usar diagnósticos de depuración para analizar un volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="430e1-119">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)