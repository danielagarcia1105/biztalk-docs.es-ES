---
title: Sobre el proveedor de datos de .NET Framework para mySAP Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSIS
- EXEC query
- SELECT query
- SAPDiscoveredObjects.xml
- SQL Server Integration Services
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- custom RFC
- Visual Studio DDEX plug-in
ms.assetid: 4832f789-c1d8-4c5d-a49d-b1da6b7d4bd4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ee712f6b818b94ca731d94165cd345a3249a61d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978917"
---
# <a name="about-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="940a7-102">Sobre el proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="940a7-102">About the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="940a7-103">Esta sección proporciona información sobre la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) y sus características.</span><span class="sxs-lookup"><span data-stu-id="940a7-103">This section provides information about the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) and its features.</span></span> <span data-ttu-id="940a7-104">Para obtener instrucciones sobre cómo usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [usar el proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="940a7-104">For instructions about how to use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="940a7-105">Incluso si decide instalar la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] como parte de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación, su [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] todavía está incompleta hasta que instale una RFC personalizada en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="940a7-105">Even if you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, your [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] is still incomplete until you install a custom RFC in the SAP system.</span></span> <span data-ttu-id="940a7-106">Para obtener instrucciones sobre cómo instalar la RFC personalizada, consulte [instalar RFC personalizadas para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span><span class="sxs-lookup"><span data-stu-id="940a7-106">For instructions on how to install the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
 <span data-ttu-id="940a7-107">Puede usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="940a7-107">You can use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] in the following ways:</span></span>  
  
- <span data-ttu-id="940a7-108">Para escribir un cliente de ADO.NET para conectarse al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="940a7-108">To write an ADO.NET client to connect to the SAP system.</span></span> <span data-ttu-id="940a7-109">La [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] expone algunas clases que permiten interactuar con el proveedor.</span><span class="sxs-lookup"><span data-stu-id="940a7-109">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] exposes certain classes that enable you to interface with the provider.</span></span>  
  
- <span data-ttu-id="940a7-110">Para ejecutar una consulta SELECT en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="940a7-110">To execute a SELECT query on the SAP system.</span></span> <span data-ttu-id="940a7-111">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] usa la RFC personalizada para esta característica.</span><span class="sxs-lookup"><span data-stu-id="940a7-111">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses the custom RFC for this feature.</span></span>  
  
- <span data-ttu-id="940a7-112">Para ejecutar una operación de ejecución en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="940a7-112">To execute an EXEC operation on the SAP system.</span></span> <span data-ttu-id="940a7-113">Esta operación se puede usar para realizar consultas en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="940a7-113">You can use this operation to perform queries on the SAP system.</span></span>  
  
- <span data-ttu-id="940a7-114">Para ejecutar una operación de EXECQUERY en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="940a7-114">To execute an EXECQUERY operation on the SAP system.</span></span> <span data-ttu-id="940a7-115">Puede utilizar esta operación para ejecutar consultas que ya están definidas en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="940a7-115">You can use this operation to execute queries that are already defined in the SAP system.</span></span>  
  
- <span data-ttu-id="940a7-116">A su vez, utilice el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX complemento a las tablas de superficie y los módulos de función desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="940a7-116">To, in turn, use the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX plug-in to surface tables and function modules from the SAP system.</span></span> <span data-ttu-id="940a7-117">Los nombres de los objetos detectados desde el sistema SAP se escriben en un archivo de configuración SAPDiscoveredObjects.xml.</span><span class="sxs-lookup"><span data-stu-id="940a7-117">The names of the objects discovered from the SAP system are written to a configuration file, SAPDiscoveredObjects.xml.</span></span>  
  
- <span data-ttu-id="940a7-118">Para usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] con SQL Server Integration Services (SSIS).</span><span class="sxs-lookup"><span data-stu-id="940a7-118">To use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SQL Server Integration Services (SSIS).</span></span>  
  
- <span data-ttu-id="940a7-119">Para usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] con SQL Server Reporting Services (SSRS).</span><span class="sxs-lookup"><span data-stu-id="940a7-119">To use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SQL Server Reporting Services (SSRS).</span></span>  
  
  <span data-ttu-id="940a7-120">Para obtener más información acerca de cómo realizar estas tareas, consulte [usar el proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="940a7-120">For more information about performing these tasks, see [Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span> <span data-ttu-id="940a7-121">Para obtener más información acerca de la solicitud de cambio personalizada, el archivo de configuración SAPDiscoveredObjects.xml y las limitaciones asociadas con el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte los vínculos siguientes.</span><span class="sxs-lookup"><span data-stu-id="940a7-121">For more information about the custom RFC, the SAPDiscoveredObjects.xml configuration file, and the limitations associated with the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see the following links.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="940a7-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="940a7-122">In This Section</span></span>  
  
-   [<span data-ttu-id="940a7-123">RFC personalizadas usadas por el proveedor de SAP</span><span class="sxs-lookup"><span data-stu-id="940a7-123">Custom RFCs Used by the Provider in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/custom-rfcs-used-by-the-provider-in-sap.md)  
  
-   [<span data-ttu-id="940a7-124">Acerca del archivo SAPDiscoveredObjects.xml en SAP</span><span class="sxs-lookup"><span data-stu-id="940a7-124">About the SAPDiscoveredObjects.xml File in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)  
  
-   [<span data-ttu-id="940a7-125">Limitaciones del proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="940a7-125">Limitations of the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/limitations-of-the-net-framework-data-provider-for-mysap-business-suite.md)