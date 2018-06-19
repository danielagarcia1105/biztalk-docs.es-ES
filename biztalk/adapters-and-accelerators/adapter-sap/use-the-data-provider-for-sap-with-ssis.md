---
title: Usar el proveedor de datos para SAP con SSIS | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, using with SSIS
- SSIS, Data Provider for SAP
ms.assetid: e8c50cc1-ac25-4993-9aee-7fd88268d65d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8459453e153626b6a79a5dc5f57ce041ba67d1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217348"
---
# <a name="use-the-data-provider-for-sap-with-ssis"></a><span data-ttu-id="d72ed-102">Usar el proveedor de datos para SAP con SSIS</span><span class="sxs-lookup"><span data-stu-id="d72ed-102">Use the Data Provider for SAP with SSIS</span></span>
<span data-ttu-id="d72ed-103">Puede usar el [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] junto con SQL Server Integration Service (SSIS) para importar datos desde un sistema SAP en tablas de base de datos de SQL Server, planos, archivos u otros tipos de destino compatible.</span><span class="sxs-lookup"><span data-stu-id="d72ed-103">You can use the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] along with SQL Server Integration Service (SSIS) to import data from an SAP system into SQL Server database tables, flat files, or other compatible destination types.</span></span> <span data-ttu-id="d72ed-104">Puede crear un paquete SSIS que se puede ejecutar para importar datos desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="d72ed-104">You can create an SSIS package that can be executed to import data from an SAP system.</span></span>  
  
 <span data-ttu-id="d72ed-105">Debe usar al Asistente de SQL Server Import y Export para importar datos en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d72ed-105">You must use the SQL Server Import and Export wizard to import data into the SQL Server database.</span></span> <span data-ttu-id="d72ed-106">Debe proporcionar una consulta para especificar los datos que desea importar.</span><span class="sxs-lookup"><span data-stu-id="d72ed-106">You must provide a query to specify data to be imported.</span></span> <span data-ttu-id="d72ed-107">Puede especificar una consulta con la instrucción SELECT o la instrucción EXECQUERY.</span><span class="sxs-lookup"><span data-stu-id="d72ed-107">You can specify a query using the SELECT statement or the EXECQUERY statement.</span></span> <span data-ttu-id="d72ed-108">Debe confirmar la consulta a la semántica de compatible con la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d72ed-108">The query must confirm to the semantics supported by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="d72ed-109">Para obtener más información sobre la gramática de una instrucción SELECT de consulta para la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [sintaxis para una instrucción SELECT en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="d72ed-109">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span> <span data-ttu-id="d72ed-110">Para obtener más información sobre la gramática de una instrucción EXECQUERY para la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [sintaxis de una instrucción EXECQUERY en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="d72ed-110">For more information about the grammar for an EXECQUERY statement for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for an EXECQUERY Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md).</span></span>  
  
 <span data-ttu-id="d72ed-111">Puede iniciar al Asistente para exportación de importación de SQL Server desde SQL Server Management Studio o desde un proyecto de servicio de integración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d72ed-111">You can start the SQL Server Import Export wizard either from the SQL Server Management Studio or from an Integration Service project in Visual Studio.</span></span> <span data-ttu-id="d72ed-112">Esta sección proporciona instrucciones sobre cómo ejecutar al Asistente de interfaces de Management Studio y Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d72ed-112">This section provides instructions on running the wizard from both the Management Studio and Visual Studio interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d72ed-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d72ed-113">In This Section</span></span>  
  
-   [<span data-ttu-id="d72ed-114">Importar datos SAP con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d72ed-114">Import SAP Data Using SQL Server Management Studio</span></span>](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="d72ed-115">Importar datos SAP mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d72ed-115">Import SAP Data Using Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-visual-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="d72ed-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d72ed-116">See Also</span></span>  
 [<span data-ttu-id="d72ed-117">Usar el proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="d72ed-117">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)