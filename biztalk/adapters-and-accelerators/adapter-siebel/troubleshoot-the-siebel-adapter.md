---
title: Solucionar problemas del adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: de11ffe3-3622-40df-b9c5-11c96f8460e0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e12b877eaabb629bb9e9e1da81cf5343e1780cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-siebel-adapter"></a><span data-ttu-id="5458e-102">Solucionar problemas del adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="5458e-102">Troubleshoot the Siebel adapter</span></span>
<span data-ttu-id="5458e-103">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] usa o depende de diferentes tecnologías de Microsoft incluidos pero no limitados a [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] / [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5458e-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several different Microsoft technologies including but not limited to [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]/[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="5458e-104">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] se crea en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], lo que a su vez requiere [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] y [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5458e-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] and [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="5458e-105">Los adaptadores pueden utilizarse o bien escribir aplicaciones mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o mediante la creación de aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5458e-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="5458e-106">Para problemas relacionados con cada uno de estos productos y tecnologías, consulte la documentación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5458e-106">For issues related to each of these technologies and products, refer to the respective documentation.</span></span>  
  
 <span data-ttu-id="5458e-107">Esta sección proporciona información acerca de cómo solucionar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], incluido:</span><span class="sxs-lookup"><span data-stu-id="5458e-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="5458e-108">La habilitación del seguimiento diagnosticar problemas con los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="5458e-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="5458e-109">Control de instalación y problemas operativos que pueden surgir al trabajar con los adaptadores, incluida la causa probable y una resolución.</span><span class="sxs-lookup"><span data-stu-id="5458e-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="5458e-110">Uso de contadores de rendimiento para medir el rendimiento del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5458e-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="5458e-111">Control de excepciones y errores, incluida la causa probable y una resolución.</span><span class="sxs-lookup"><span data-stu-id="5458e-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5458e-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5458e-112">In This Section</span></span>  
  
-   [<span data-ttu-id="5458e-113">Seguimiento de diagnóstico y registro de mensajes para el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="5458e-113">Diagnostic Tracing and Message Logging for the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="5458e-114">Solucionar problemas de instalación con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="5458e-114">Troubleshoot Installation Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-installation-issues-with-the-siebel-adapter.md) 
  
-   [<span data-ttu-id="5458e-115">Solucionar problemas de funcionamiento con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="5458e-115">Troubleshoot Operational Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-operational-issues-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="5458e-116">Solucionar problemas de rendimiento con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="5458e-116">Troubleshoot Performance Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-performance-issues-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="5458e-117">Solucionar problemas relacionados con el proveedor de datos para Siebel</span><span class="sxs-lookup"><span data-stu-id="5458e-117">Troubleshoot Issues with the Data Provider for Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-issues-with-the-data-provider-for-siebel.md) 
  
-   [<span data-ttu-id="5458e-118">Utilizar contadores de rendimiento con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="5458e-118">Use Performance Counters with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/use-performance-counters-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="5458e-119">Excepciones y control de errores con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="5458e-119">Exceptions and Error Handling with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)