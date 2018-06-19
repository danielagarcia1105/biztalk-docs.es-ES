---
title: 'Paso 4 (de forma local): Crear la tabla de SQL Server | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e253ac-8707-484f-8461-f098cc7ec7d8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6a6934a98ccd101003519486388b09504b5f0ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277268"
---
# <a name="step-4-on-premises-create-the-sql-server-table"></a>Paso 4 (de forma local): Crear la tabla de SQL Server
Como parte del escenario empresarial, por último, se debe insertar el mensaje X12 pedido enviado por Contoso a Northwind en un **SalesOrder** tabla, si la cantidad pedida es superior a 100. Este tema proporciona instrucciones sobre cómo crear el **SalesOrder** tabla dentro de una instancia de base de datos de SQL Server que está hospedada de forma local.  
  
### <a name="to-create-the-salesorder-table"></a>Para crear la tabla SalesOrder  
  
1.  Abra SQL Server Management Studio y ejecute la siguiente consulta en la base de datos en la que desea crear la tabla.  
  
2.  Ejecute la consulta siguiente para crear el **SalesOrder** tabla:  
  
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
  
3.  Compruebe que la tabla se ha creado en la base de datos de destino.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)