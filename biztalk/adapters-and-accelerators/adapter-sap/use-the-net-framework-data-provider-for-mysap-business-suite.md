---
title: Usar el proveedor de datos de .NET Framework para mySAP Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DDEX plug-in
- NET Framework Data Provider for mySAP Business Suite
- function module
- SSIS
- installation
- EXEC query
- SELECT query
- SAPDiscoveredObjects.xml
- SQL Server Integration Services
- Data Provider for SAP
- custom RFC
- installing
- configuration file
ms.assetid: 3abe9c34-b81b-4c0a-9bfd-bf05f89f29b8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa813fa6218d5afcb470406097d745ddf93522b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="use-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="1def6-102">Usar el proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="1def6-102">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="1def6-103">Esta sección proporciona instrucciones sobre cómo utilizar el [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1def6-103">This section provides instructions on using the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="1def6-104">Para obtener información acerca de la solicitud de cambio personalizado utilizado por [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] y vea las limitaciones del proveedor de [sobre el .NET Framework Data Provider para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="1def6-104">For information about the custom RFC used by [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] and the limitations of the provider see [About the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1def6-105">Incluso si decide instalar la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] como parte de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación, debe instalar algunas RFC personalizado en el sistema SAP para usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1def6-105">Even if you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, you must install some custom RFCs at the SAP system to use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="1def6-106">Para obtener instrucciones sobre cómo instalar las RFC personalizadas, consulte [instalar RFC personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span><span class="sxs-lookup"><span data-stu-id="1def6-106">For instructions on how to install the custom RFCs, see [Installing Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1def6-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1def6-107">In This Section</span></span>  
  
-   [<span data-ttu-id="1def6-108">Extender Interfaces de ADO.NET con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="1def6-108">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="1def6-109">Más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP</span><span class="sxs-lookup"><span data-stu-id="1def6-109">Read about Data Provider types for the SAP Connection String</span></span>](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)  
  
-   [<span data-ttu-id="1def6-110">Sintaxis de una instrucción SELECT en SAP</span><span class="sxs-lookup"><span data-stu-id="1def6-110">Syntax for a SELECT Statement in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)  
  
-   [<span data-ttu-id="1def6-111">Sintaxis para una instrucción EXEC en SAP</span><span class="sxs-lookup"><span data-stu-id="1def6-111">Syntax for an EXEC Statement in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)  
  
-   [<span data-ttu-id="1def6-112">Compatibilidad para ejecutar consultas SAP</span><span class="sxs-lookup"><span data-stu-id="1def6-112">Support for Executing SAP Queries</span></span>](https://msdn.microsoft.com/library/dd788118.aspx)  
  
-   [<span data-ttu-id="1def6-113">Invocar RFC y BAPI mediante el comando EXEC en SAP</span><span class="sxs-lookup"><span data-stu-id="1def6-113">Invoking RFCs and BAPIs by using the EXEC Command in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-and-bapis-using-the-exec-command-in-sap.md)  
  
-   [<span data-ttu-id="1def6-114">Realizar una consulta mediante el comando SELECT en SAP</span><span class="sxs-lookup"><span data-stu-id="1def6-114">Performing a Query by using the SELECT Command in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/run-a-query-using-the-select-command-in-sap.md)  
  
-   [<span data-ttu-id="1def6-115">Ejecutar una consulta SAP mediante el comando EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="1def6-115">Executing an SAP Query Using the EXECQUERY Command</span></span>](../../adapters-and-accelerators/adapter-sap/execute-an-sap-query-using-the-execquery-command.md)  
  
-   [<span data-ttu-id="1def6-116">Mediante el proveedor de datos para SAP con el complemento DDEX</span><span class="sxs-lookup"><span data-stu-id="1def6-116">Using the Data Provider for SAP with the DDEX Plug-in</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md)  
  
-   [<span data-ttu-id="1def6-117">Mediante el proveedor de datos para SAP con SSIS</span><span class="sxs-lookup"><span data-stu-id="1def6-117">Using the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)  
  
-   [<span data-ttu-id="1def6-118">Mediante el proveedor de datos para SAP con SSRS</span><span class="sxs-lookup"><span data-stu-id="1def6-118">Using the Data Provider for SAP with SSRS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)