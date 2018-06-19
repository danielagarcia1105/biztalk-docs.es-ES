---
title: Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ADO.NET programming, performing operations
- Data Provider for Siebel, overview
ms.assetid: 97fe4f95-c9ae-42f1-a159-1b0e98607b31
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5acb8f96add3dcde48456751d82dc2a8e00ffe43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222244"
---
# <a name="use-the-net-framework-data-provider-for-siebel-ebusiness-applications"></a><span data-ttu-id="4b690-102">Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness</span><span class="sxs-lookup"><span data-stu-id="4b690-102">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>
<span data-ttu-id="4b690-103">Esta sección proporciona instrucciones sobre cómo utilizar el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="4b690-103">This section provides instructions on using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span> <span data-ttu-id="4b690-104">Esta sección proporciona información acerca de:</span><span class="sxs-lookup"><span data-stu-id="4b690-104">This section provides information about:</span></span>  
  
-   <span data-ttu-id="4b690-105">La cadena de conexión para conectarse a un sistema de Siebel mediante un cliente ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="4b690-105">The connection string to connect to a Siebel system using an ADO.NET client.</span></span>  
  
-   <span data-ttu-id="4b690-106">La sintaxis de instrucciones SELECT y EXEC.</span><span class="sxs-lookup"><span data-stu-id="4b690-106">The syntax for SELECT and EXEC statements.</span></span>  
  
-   <span data-ttu-id="4b690-107">Con la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] con SSIS.</span><span class="sxs-lookup"><span data-stu-id="4b690-107">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SSIS.</span></span>  
  
-   <span data-ttu-id="4b690-108">Interfaces de ADO.NET que la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] extiende.</span><span class="sxs-lookup"><span data-stu-id="4b690-108">The ADO.NET interfaces that the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] extends.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b690-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4b690-109">In This Section</span></span>  
  
-   [<span data-ttu-id="4b690-110">Extender Interfaces de ADO.NET con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="4b690-110">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="4b690-111">Propiedades de proveedor de datos de la cadena de conexión de Siebel</span><span class="sxs-lookup"><span data-stu-id="4b690-111">Data Provider properties for the Siebel Connection String</span></span>](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)  
  
-   [<span data-ttu-id="4b690-112">Sintaxis de una instrucción SELECT de Siebel</span><span class="sxs-lookup"><span data-stu-id="4b690-112">Syntax for a SELECT Statement in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)  
  
-   [<span data-ttu-id="4b690-113">Sintaxis para una instrucción EXEC en Siebel</span><span class="sxs-lookup"><span data-stu-id="4b690-113">Syntax for an EXEC Statement in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/syntax-for-an-exec-statement-in-siebel.md)  
  
-   [<span data-ttu-id="4b690-114">Ejecute una consulta SELECT en componentes empresariales con Siebel</span><span class="sxs-lookup"><span data-stu-id="4b690-114">Run a SELECT Query on Business Components with Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/run-a-select-query-on-business-components-with-siebel.md)  
  
-   [<span data-ttu-id="4b690-115">Ejecutar una operación de ejecución en los servicios de negocios con Siebel</span><span class="sxs-lookup"><span data-stu-id="4b690-115">Run an EXECUTE Operation on Business Services with Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/run-an-execute-operation-on-business-services-with-siebel.md)  
  
-   [<span data-ttu-id="4b690-116">Usar el proveedor de datos de Siebel con SSIS</span><span class="sxs-lookup"><span data-stu-id="4b690-116">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)