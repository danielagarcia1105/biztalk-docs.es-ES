---
title: Usar el proveedor de datos de Siebel con SSIS | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSIS
- SQL Server Integration Services
- Data Provider for Siebel, using with SSIS
ms.assetid: e72cecf2-6c05-4df7-8e6e-aff3a9df8b79
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c46c1437d7eeedd56ee37b054f9f6eb6b72ada
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222212"
---
# <a name="use-the-data-provider-for-siebel-with-ssis"></a><span data-ttu-id="ac865-102">Usar el proveedor de datos de Siebel con SSIS</span><span class="sxs-lookup"><span data-stu-id="ac865-102">Use the Data Provider for Siebel with SSIS</span></span>
<span data-ttu-id="ac865-103">Puede usar el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) junto con SQL Server Integration Services (SSIS) para importar datos desde un sistema Siebel en tablas de base de datos de SQL Server, planos, archivos u otros tipos de destino compatible.</span><span class="sxs-lookup"><span data-stu-id="ac865-103">You can use the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) along with SQL Server Integration Services (SSIS) to import data from a Siebel system into SQL Server database tables, flat files, or other compatible destination types.</span></span> <span data-ttu-id="ac865-104">En concreto, puede crear un paquete SSIS que se puede ejecutar para importar estos datos.</span><span class="sxs-lookup"><span data-stu-id="ac865-104">Specifically, you can create an SSIS package that can be executed to import this data.</span></span>  
  
 <span data-ttu-id="ac865-105">Para importar datos en la base de datos de SQL Server, use el Asistente para exportación y SQL Server Import y proporcionar una consulta SELECT para especificar los datos que desea importar.</span><span class="sxs-lookup"><span data-stu-id="ac865-105">To import data into the SQL Server database, use the SQL Server Import and Export Wizard, and provide a SELECT query to specify the data to be imported.</span></span> <span data-ttu-id="ac865-106">Debe confirmar la consulta a la semántica de compatible con la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac865-106">The query must confirm to the semantics supported by the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span> <span data-ttu-id="ac865-107">Para obtener más información sobre la gramática de una instrucción SELECT de consulta para la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], consulte [sintaxis de una instrucción SELECT de Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span><span class="sxs-lookup"><span data-stu-id="ac865-107">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac865-108">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] no admite el uso de una instrucción EXEC con SSIS.</span><span class="sxs-lookup"><span data-stu-id="ac865-108">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] does not support using an EXEC statement with SSIS.</span></span>  
  
 <span data-ttu-id="ac865-109">Puede iniciar al Asistente de SQL Server importación y exportación de SQL Server Management Studio o desde un proyecto de servicio de integración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ac865-109">You can start the SQL Server Import and Export wizard either from the SQL Server Management Studio or from an Integration Service project in Visual Studio.</span></span> <span data-ttu-id="ac865-110">Esta sección proporciona instrucciones sobre cómo ejecutar al Asistente de las interfaces tanto el SQL Server Management Studio y Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ac865-110">This section provides instructions on running the wizard from both the SQL Server Management Studio and Visual Studio interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac865-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ac865-111">In This Section</span></span>  
  
-   [<span data-ttu-id="ac865-112">Importar datos de Siebel utilizando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ac865-112">Import Siebel Data Using SQL Server Management Studio</span></span>](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ac865-113">Importar datos de Siebel con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ac865-113">Import Siebel Data Using Visual Studio</span></span>](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-visual-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="ac865-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac865-114">See Also</span></span>  
 [<span data-ttu-id="ac865-115">Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness</span><span class="sxs-lookup"><span data-stu-id="ac865-115">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)