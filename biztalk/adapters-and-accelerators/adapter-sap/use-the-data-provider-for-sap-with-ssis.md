---
title: Usar el proveedor de datos para SAP con SSIS | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, using with SSIS
- SSIS, Data Provider for SAP
ms.assetid: e8c50cc1-ac25-4993-9aee-7fd88268d65d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8459453e153626b6a79a5dc5f57ce041ba67d1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="use-the-data-provider-for-sap-with-ssis"></a>Usar el proveedor de datos para SAP con SSIS
Puede usar el [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] junto con SQL Server Integration Service (SSIS) para importar datos desde un sistema SAP en tablas de base de datos de SQL Server, planos, archivos u otros tipos de destino compatible. Puede crear un paquete SSIS que se puede ejecutar para importar datos desde un sistema SAP.  
  
 Debe usar al Asistente de SQL Server Import y Export para importar datos en la base de datos de SQL Server. Debe proporcionar una consulta para especificar los datos que desea importar. Puede especificar una consulta con la instrucción SELECT o la instrucción EXECQUERY. Debe confirmar la consulta a la semántica de compatible con la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]. Para obtener más información sobre la gramática de una instrucción SELECT de consulta para la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [sintaxis para una instrucción SELECT en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md). Para obtener más información sobre la gramática de una instrucción EXECQUERY para la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [sintaxis de una instrucción EXECQUERY en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md).  
  
 Puede iniciar al Asistente para exportación de importación de SQL Server desde SQL Server Management Studio o desde un proyecto de servicio de integración de Visual Studio. Esta sección proporciona instrucciones sobre cómo ejecutar al Asistente de interfaces de Management Studio y Visual Studio.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Importar datos SAP con SQL Server Management Studio](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-sql-server-management-studio.md)  
  
-   [Importar datos SAP mediante Visual Studio](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-visual-studio.md)  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)