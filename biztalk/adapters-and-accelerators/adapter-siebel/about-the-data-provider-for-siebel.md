---
title: Acerca del proveedor de datos para Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, overview
ms.assetid: 461fe4d8-75f2-49d5-9fc2-3baab4ccf13f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81cac425bf1671166b4f40cecae3e1a3aca1c8e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-data-provider-for-siebel"></a><span data-ttu-id="908c4-102">Acerca del proveedor de datos para Siebel</span><span class="sxs-lookup"><span data-stu-id="908c4-102">About the Data Provider for Siebel</span></span>
## <a name="overview"></a><span data-ttu-id="908c4-103">Información general</span><span class="sxs-lookup"><span data-stu-id="908c4-103">Overview</span></span>
<span data-ttu-id="908c4-104">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] se basa en el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span><span class="sxs-lookup"><span data-stu-id="908c4-104">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is built on top of the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span> <span data-ttu-id="908c4-105">Puede usar el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] para:</span><span class="sxs-lookup"><span data-stu-id="908c4-105">You can use the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] to:</span></span>  
  
-   <span data-ttu-id="908c4-106">Escribir un cliente ADO.NET para conectarse al sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="908c4-106">Write an ADO.NET client to connect to the Siebel system.</span></span> <span data-ttu-id="908c4-107">La [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] expone ciertas clases que permiten interactuar con el proveedor.</span><span class="sxs-lookup"><span data-stu-id="908c4-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] exposes certain classes that enable you to interface with the provider.</span></span>  
  
-   <span data-ttu-id="908c4-108">Ejecute una consulta SELECT en un componente de negocio de Siebel</span><span class="sxs-lookup"><span data-stu-id="908c4-108">Run a SELECT query on a Siebel business component</span></span>
  
-   <span data-ttu-id="908c4-109">Ejecutar una consulta de ejecución en un servicio de negocios de Siebel</span><span class="sxs-lookup"><span data-stu-id="908c4-109">Run an EXEC query on a Siebel business service</span></span>
  
-   <span data-ttu-id="908c4-110">Use la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] con SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="908c4-110">Use the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SQL Server Integration Services (SSIS)</span></span>
  
<span data-ttu-id="908c4-111">[Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md) es un excelente recurso para obtener información sobre:</span><span class="sxs-lookup"><span data-stu-id="908c4-111">[Use  the .NET Framework Data Provider for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md) is a great resource for information on:</span></span>  
  
-   <span data-ttu-id="908c4-112">Las interfaces ADO.NET extendidos mediante el[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="908c4-112">The ADO.NET interfaces extended by the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]</span></span>  
  
-   <span data-ttu-id="908c4-113">La cadena de conexión para conectarse a un sistema Siebel</span><span class="sxs-lookup"><span data-stu-id="908c4-113">The connection string to connect to a Siebel system</span></span>  
  
-   <span data-ttu-id="908c4-114">Sintaxis de las instrucciones SELECT y EXEC</span><span class="sxs-lookup"><span data-stu-id="908c4-114">Syntax for the SELECT and EXEC statements</span></span>  
  
-   <span data-ttu-id="908c4-115">Con la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] con SSIS</span><span class="sxs-lookup"><span data-stu-id="908c4-115">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SSIS</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="908c4-116">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="908c4-116">Limitations</span></span>
<span data-ttu-id="908c4-117">Los siguientes se conocen las limitaciones de la [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="908c4-117">The following are known limitations of the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:</span></span>  
  
-   <span data-ttu-id="908c4-118">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] alias admite nombres para las tablas en la cláusula SELECT, pero no en la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="908c4-118">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports alias names for tables in the SELECT clause, but not in the WHERE clause.</span></span>  
  
-   <span data-ttu-id="908c4-119">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] no puede crear una tabla con nombres de columna que contiene el carácter especial, "]".</span><span class="sxs-lookup"><span data-stu-id="908c4-119">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] fails to create a table with column names that have the special character, "]".</span></span> <span data-ttu-id="908c4-120">Se puede omitir el carácter especial mediante la inclusión de otro corchete de cierre.</span><span class="sxs-lookup"><span data-stu-id="908c4-120">You can escape the special character by including another closing square bracket.</span></span> <span data-ttu-id="908c4-121">Por lo tanto, debe incluir"]]" en lugar de "]".</span><span class="sxs-lookup"><span data-stu-id="908c4-121">So, you should include"]]" instead of "]".</span></span>  
  
-   <span data-ttu-id="908c4-122">Debido a problemas con el control de tiempo de espera por el cliente de Siebel subyacente API, el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] no es compatible con el tiempo de espera de conexión y comando.</span><span class="sxs-lookup"><span data-stu-id="908c4-122">Due to issues with timeout handling by the underlying Siebel client API, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] does not support command and connection timeout.</span></span>  
  
-   <span data-ttu-id="908c4-123">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] no admite el comportamiento del comando asincrónico.</span><span class="sxs-lookup"><span data-stu-id="908c4-123">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] does not support asynchronous command behavior.</span></span>  
  
-   <span data-ttu-id="908c4-124">Cuando se usa con un proyecto de SQL Server Integration Services (SSIS), el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] se produce un error al recuperar datos para las columnas que contienen valores con más de 8.000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="908c4-124">When used with a SQL Server Integration Services (SSIS) project, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] fails to retrieve data for columns that contain values with more than 8000 characters.</span></span> <span data-ttu-id="908c4-125">Esto es debido a una restricción de SSIS según los cuales:</span><span class="sxs-lookup"><span data-stu-id="908c4-125">This is due to an SSIS restriction according to which:</span></span>  
  
    -   <span data-ttu-id="908c4-126">No se admiten valores superiores a 4.000 caracteres en la variable SSIS.</span><span class="sxs-lookup"><span data-stu-id="908c4-126">Values greater than 4000 characters in SSIS variable are not supported.</span></span>  
  
    -   <span data-ttu-id="908c4-127">No se admiten valores superiores a 4.000 caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="908c4-127">Values greater than 4000 wide characters are not supported.</span></span>  
  
    -   <span data-ttu-id="908c4-128">No se admiten valores mayores que 8000 caracteres de byte único.</span><span class="sxs-lookup"><span data-stu-id="908c4-128">Values greater than 8000 single-byte characters are not supported.</span></span>  
  
-   <span data-ttu-id="908c4-129">La operación de EXEC no será funcional al usar el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] con SQL Server Integration Services (SSIS).</span><span class="sxs-lookup"><span data-stu-id="908c4-129">The EXEC operation will not be functional while using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] with SQL Server Integration Services (SSIS).</span></span> <span data-ttu-id="908c4-130">Por lo tanto, por ejemplo, los clientes de adaptador no será capaz de ejecutar un servicio de negocio de Siebel (mediante [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) durante el uso de los proveedores de datos con SSIS.</span><span class="sxs-lookup"><span data-stu-id="908c4-130">So, for example, adapter clients will not be able to execute a business service in Siebel (using [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) while using the data providers with SSIS.</span></span> 

## <a name="see-also"></a><span data-ttu-id="908c4-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="908c4-131">See also</span></span>
[<span data-ttu-id="908c4-132">Limitaciones del adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="908c4-132">Limitations of the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[<span data-ttu-id="908c4-133">Solucionar problemas del adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="908c4-133">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)