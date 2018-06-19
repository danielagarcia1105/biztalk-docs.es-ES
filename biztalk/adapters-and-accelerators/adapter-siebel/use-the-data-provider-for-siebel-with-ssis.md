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
# <a name="use-the-data-provider-for-siebel-with-ssis"></a>Usar el proveedor de datos de Siebel con SSIS
Puede usar el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) junto con SQL Server Integration Services (SSIS) para importar datos desde un sistema Siebel en tablas de base de datos de SQL Server, planos, archivos u otros tipos de destino compatible. En concreto, puede crear un paquete SSIS que se puede ejecutar para importar estos datos.  
  
 Para importar datos en la base de datos de SQL Server, use el Asistente para exportación y SQL Server Import y proporcionar una consulta SELECT para especificar los datos que desea importar. Debe confirmar la consulta a la semántica de compatible con la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]. Para obtener más información sobre la gramática de una instrucción SELECT de consulta para la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], consulte [sintaxis de una instrucción SELECT de Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).  
  
> [!NOTE]
>  El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] no admite el uso de una instrucción EXEC con SSIS.  
  
 Puede iniciar al Asistente de SQL Server importación y exportación de SQL Server Management Studio o desde un proyecto de servicio de integración de Visual Studio. Esta sección proporciona instrucciones sobre cómo ejecutar al Asistente de las interfaces tanto el SQL Server Management Studio y Visual Studio.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Importar datos de Siebel utilizando SQL Server Management Studio](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-sql-server-management-studio.md)  
  
-   [Importar datos de Siebel con Visual Studio](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-visual-studio.md)  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)