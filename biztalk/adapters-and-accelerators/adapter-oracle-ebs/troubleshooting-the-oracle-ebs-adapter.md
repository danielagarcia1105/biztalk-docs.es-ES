---
title: Solucionar problemas del adaptador de Oracle EBS | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d78d5335-b860-47d9-9f3a-7f74d628d8ff
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7b36316612bda541d9bf608f7da22c399ade045
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-oracle-ebs-adapter"></a><span data-ttu-id="25a33-102">Solucionar problemas del adaptador de Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="25a33-102">Troubleshooting the Oracle EBS adapter</span></span>
## <a name="overview"></a><span data-ttu-id="25a33-103">Información general</span><span class="sxs-lookup"><span data-stu-id="25a33-103">Overview</span></span>
<span data-ttu-id="25a33-104">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] usa o depende de varias tecnologías de Microsoft, incluyendo pero sin limitarse a la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], y [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25a33-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="25a33-105">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] se crea en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], que también utiliza el [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25a33-105">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which also uses the [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="25a33-106">Los adaptadores pueden utilizarse o bien escribir aplicaciones mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o mediante la creación de aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="25a33-106">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> 
  
 <span data-ttu-id="25a33-107">Esta sección proporciona información sobre cómo solucionar problemas, incluyendo:</span><span class="sxs-lookup"><span data-stu-id="25a33-107">This section provides information about troubleshooting, including:</span></span>  
  
-   <span data-ttu-id="25a33-108">La habilitación del seguimiento diagnosticar problemas con los adaptadores</span><span class="sxs-lookup"><span data-stu-id="25a33-108">Enabling tracing to diagnose issues with the adapters</span></span>
  
-   <span data-ttu-id="25a33-109">Control de instalación y problemas operativos que pueden surgir al trabajar con los adaptadores, incluida la causa probable y una resolución</span><span class="sxs-lookup"><span data-stu-id="25a33-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause and a resolution</span></span>
  
-   <span data-ttu-id="25a33-110">Uso de contadores de rendimiento para revisar el rendimiento del adaptador</span><span class="sxs-lookup"><span data-stu-id="25a33-110">Using performance counters to review adapter performance</span></span>
  
-   <span data-ttu-id="25a33-111">Control de excepciones y errores, incluida la causa probable y una resolución</span><span class="sxs-lookup"><span data-stu-id="25a33-111">Handling exceptions and errors, including probable cause, and a resolution</span></span>
  
## <a name="lets-get-started"></a><span data-ttu-id="25a33-112">Comencemos</span><span class="sxs-lookup"><span data-stu-id="25a33-112">Let's get started</span></span>  
  
-   [<span data-ttu-id="25a33-113">Seguimiento de diagnóstico y el registro de mensajes en el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="25a33-113">Diagnostic Tracing and Message Logging in the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md) 
  
-   [<span data-ttu-id="25a33-114">Solucionar problemas de instalación con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="25a33-114">Troubleshoot Installation Issues with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter.md)  
  
-   [<span data-ttu-id="25a33-115">Solucionar problemas de funcionamiento con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="25a33-115">Troubleshoot Operational Issues with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter.md)
  
-   [<span data-ttu-id="25a33-116">Utilizar contadores de rendimiento con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="25a33-116">Use Performance Counters with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/use-performance-counters-with-the-oracle-e-business-suite-adapter.md)