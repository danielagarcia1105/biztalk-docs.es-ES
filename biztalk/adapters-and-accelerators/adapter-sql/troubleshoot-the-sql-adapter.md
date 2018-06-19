---
title: Solucionar problemas del adaptador SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1be376ba-ad4c-4fa7-b94b-82bfbc8f34cc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8b574a372ed365a22ff9d87d40bf4ab9af8ae4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222540"
---
# <a name="troubleshoot-the-sql-adapter"></a><span data-ttu-id="34d5e-102">Solucionar problemas del adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="34d5e-102">Troubleshoot the SQL adapter</span></span>
<span data-ttu-id="34d5e-103">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] usa o depende de varias tecnologías de Microsoft, incluyendo pero sin limitarse a la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)], y [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34d5e-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)], and [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="34d5e-104">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] se crea en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], lo que a su vez requiere el [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] o [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34d5e-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="34d5e-105">Los adaptadores pueden utilizarse o bien escribir las aplicaciones que usan el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o mediante la creación de aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="34d5e-105">The adapters can be consumed either by writing applications using the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="34d5e-106">Para problemas relacionados con cada uno de estos productos y tecnologías, consulte la documentación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="34d5e-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="34d5e-107">Esta sección proporciona información acerca de cómo solucionar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], incluido:</span><span class="sxs-lookup"><span data-stu-id="34d5e-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="34d5e-108">La habilitación del seguimiento diagnosticar problemas con los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="34d5e-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="34d5e-109">Control de instalación y problemas operativos que pueden surgir al trabajar con los adaptadores, incluida la causa probable y una resolución.</span><span class="sxs-lookup"><span data-stu-id="34d5e-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="34d5e-110">Uso de contadores de rendimiento para medir el rendimiento del adaptador.</span><span class="sxs-lookup"><span data-stu-id="34d5e-110">Using performance counters to gauge adapter performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="34d5e-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="34d5e-111">In This Section</span></span>  
  
-   [<span data-ttu-id="34d5e-112">Seguimiento de diagnóstico y el registro de mensajes en el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="34d5e-112">Diagnostic Tracing and Message Logging in the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)  
  
-   [<span data-ttu-id="34d5e-113">Solucionar problemas de instalación con el adaptador de SQl</span><span class="sxs-lookup"><span data-stu-id="34d5e-113">Troubleshoot Installation Issues with the SQl adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-installation-issues-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="34d5e-114">Solucionar problemas de funcionamiento con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="34d5e-114">Troubleshoot Operational Issues with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-operational-issues-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="34d5e-115">Utilice los contadores de rendimiento con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="34d5e-115">Use Performance Counters with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)