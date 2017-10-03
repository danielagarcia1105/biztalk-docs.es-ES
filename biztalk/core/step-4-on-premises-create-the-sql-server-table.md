---
title: 'Paso 4 (de forma local): Crear la tabla de SQL Server | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7e253ac-8707-484f-8461-f098cc7ec7d8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6a6934a98ccd101003519486388b09504b5f0ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-on-premises-create-the-sql-server-table"></a><span data-ttu-id="14408-102">Paso 4 (de forma local): Crear la tabla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="14408-102">Step 4 (On Premises): Create the SQL Server Table</span></span>
<span data-ttu-id="14408-103">Como parte del escenario empresarial, por último, se debe insertar el mensaje X12 pedido enviado por Contoso a Northwind en un **SalesOrder** tabla, si la cantidad pedida es superior a 100.</span><span class="sxs-lookup"><span data-stu-id="14408-103">As part of the business scenario, the message X12 sales order message sent by Contoso to Northwind must finally be inserted in a **SalesOrder** table, if the quantity ordered is greater than 100.</span></span> <span data-ttu-id="14408-104">Este tema proporciona instrucciones sobre cómo crear el **SalesOrder** tabla dentro de una instancia de base de datos de SQL Server que está hospedada de forma local.</span><span class="sxs-lookup"><span data-stu-id="14408-104">This topic provides instructions on how to create the **SalesOrder** table within a SQL Server database instance that is housed on-premises.</span></span>  
  
### <a name="to-create-the-salesorder-table"></a><span data-ttu-id="14408-105">Para crear la tabla SalesOrder</span><span class="sxs-lookup"><span data-stu-id="14408-105">To create the SalesOrder table</span></span>  
  
1.  <span data-ttu-id="14408-106">Abra SQL Server Management Studio y ejecute la siguiente consulta en la base de datos en la que desea crear la tabla.</span><span class="sxs-lookup"><span data-stu-id="14408-106">Open SQL Server Management Studio and run the following query against the database where you want to create the table.</span></span>  
  
2.  <span data-ttu-id="14408-107">Ejecute la consulta siguiente para crear el **SalesOrder** tabla:</span><span class="sxs-lookup"><span data-stu-id="14408-107">Run the following query to create the **SalesOrder** table:</span></span>  
  
    ```  
    CREATE TABLE [dbo].[SalesOrder] (  
        [SalesOrderID] int IDENTITY(1,1) NOT NULL,  
        [PartNum] int  NOT NULL,  
        [DateRequested] datetime  NULL,  
        [CompanyCode] varchar(3)  NOT NULL,  
        [Qty] int  NOT NULL,  
        [UnitAskPrice] float  NULL,  
        [ShipDate] datetime  NOT NULL,  
        [SellToAddress] varchar(255)  NULL,  
        [BillToAddress] varchar(255)  NOT NULL,  
        [PartnerContact] varchar(128)  NULL,  
        [CustomerComments] varchar(500)  NULL,  
        [RFQStatuesId] smallint  NULL  
    );  
    GO  
    ```  
  
3.  <span data-ttu-id="14408-108">Compruebe que la tabla se ha creado en la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="14408-108">Verify that the table is created in the target database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14408-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="14408-109">See Also</span></span>  
 [<span data-ttu-id="14408-110">Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="14408-110">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)