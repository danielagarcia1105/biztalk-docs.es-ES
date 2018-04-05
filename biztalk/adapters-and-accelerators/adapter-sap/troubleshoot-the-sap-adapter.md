---
title: Solucionar problemas del adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 2c554a7b-18be-4c94-8bf2-f22ac080794c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1994f7c2d6d32dc394783a68edb91532118434aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-sap-adapter"></a><span data-ttu-id="07c15-102">Solucionar problemas del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="07c15-102">Troubleshoot the SAP adapter</span></span>
<span data-ttu-id="07c15-103">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] usa o depende de varias tecnologías de Microsoft, incluyendo pero sin limitarse a la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] o [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07c15-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="07c15-104">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] se crea en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], lo que a su vez requiere el [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] o [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07c15-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="07c15-105">Los adaptadores pueden utilizarse o bien escribir aplicaciones mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o mediante la creación de aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="07c15-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="07c15-106">Para problemas relacionados con cada uno de estos productos y tecnologías, consulte la documentación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="07c15-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="07c15-107">Esta sección proporciona información acerca de cómo solucionar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], incluido:</span><span class="sxs-lookup"><span data-stu-id="07c15-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="07c15-108">La habilitación del seguimiento diagnosticar problemas con los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="07c15-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="07c15-109">Control de instalación y problemas operativos que pueden surgir al trabajar con los adaptadores, incluida la causa probable y una resolución.</span><span class="sxs-lookup"><span data-stu-id="07c15-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="07c15-110">Uso de contadores de rendimiento para medir el rendimiento del adaptador.</span><span class="sxs-lookup"><span data-stu-id="07c15-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="07c15-111">Control de excepciones y errores, incluida la causa probable y una resolución.</span><span class="sxs-lookup"><span data-stu-id="07c15-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07c15-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="07c15-112">In This Section</span></span>  
  
-   [<span data-ttu-id="07c15-113">Seguimiento de diagnóstico y registro de mensajes para el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="07c15-113">Diagnostic Tracing and Message Logging for the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md)  
  
-   [<span data-ttu-id="07c15-114">Solucionar problemas de instalación con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="07c15-114">Troubleshoot Installation Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-installation-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="07c15-115">Solucionar problemas de funcionamiento con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="07c15-115">Troubleshoot Operational Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="07c15-116">Solucionar problemas de rendimiento con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="07c15-116">Troubleshoot Performance Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-performance-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="07c15-117">Solucionar problemas relacionados con el proveedor de datos para SAP</span><span class="sxs-lookup"><span data-stu-id="07c15-117">Troubleshoot Issues with the Data Provider for SAP</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-issues-with-the-data-provider-for-sap.md)  
  
-   [<span data-ttu-id="07c15-118">Utilizar contadores de rendimiento con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="07c15-118">Use Performance Counters with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="07c15-119">Excepciones y control de errores con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="07c15-119">Exceptions and Error Handling with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)