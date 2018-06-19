---
title: Solucionar problemas del adaptador de base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 2a3da42b-413b-479a-90d2-02f262abff41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3cf2e8c5f9a3f0baa743f86eaf6527ed9847019
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215132"
---
# <a name="troubleshoot-the-oracle-database-adapter"></a><span data-ttu-id="1165c-102">Solucionar problemas del adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="1165c-102">Troubleshoot the Oracle Database adapter</span></span>
<span data-ttu-id="1165c-103">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] usa o depende de varias tecnologías de Microsoft, incluyendo pero sin limitarse a la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1165c-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="1165c-104">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] se crea en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], lo que a su vez requiere el [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1165c-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="1165c-105">Los adaptadores pueden utilizarse o bien escribir aplicaciones mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o mediante la creación de aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="1165c-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="1165c-106">Para problemas relacionados con cada uno de estos productos y tecnologías, consulte la documentación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1165c-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="1165c-107">Esta sección proporciona información acerca de cómo solucionar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], incluido:</span><span class="sxs-lookup"><span data-stu-id="1165c-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="1165c-108">La habilitación del seguimiento diagnosticar problemas con los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="1165c-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="1165c-109">Control de instalación y problemas operativos que pueden surgir al trabajar con los adaptadores, incluida la causa probable y una resolución.</span><span class="sxs-lookup"><span data-stu-id="1165c-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="1165c-110">Uso de contadores de rendimiento para medir el rendimiento del adaptador.</span><span class="sxs-lookup"><span data-stu-id="1165c-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="1165c-111">Control de excepciones y errores, incluida la causa probable y una resolución.</span><span class="sxs-lookup"><span data-stu-id="1165c-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1165c-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1165c-112">In This Section</span></span>  
  
-   [<span data-ttu-id="1165c-113">Seguimiento de diagnóstico y registro de mensajes para el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="1165c-113">Diagnostic tracing and message logging for the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="1165c-114">Solucionar problemas de instalación con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="1165c-114">Troubleshoot installation issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="1165c-115">Solucionar problemas de funcionamiento con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="1165c-115">Troubleshoot operational issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="1165c-116">Solucionar problemas de rendimiento con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="1165c-116">Troubleshoot performance issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-performance-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="1165c-117">Utilizar contadores de rendimiento con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="1165c-117">Use performance counters with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/use-performance-counters-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="1165c-118">Excepciones y control de errores con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="1165c-118">Exceptions and error handling with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)