---
title: Sobre el proveedor de datos de .NET Framework para mySAP Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf6b8a1657f0731fc09c4ebc1ef1fa99e0e6ae4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-net-framework-data-provider-for-mysap-business-suite"></a>Sobre el proveedor de datos de .NET Framework para mySAP Business Suite
Esta sección proporciona información sobre la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) y sus características. Para obtener instrucciones sobre cómo usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [usar .NET Framework Data Provider para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).  
  
> [!NOTE]
>  Incluso si decide instalar la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] como parte de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación, su [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] todavía está incompleta hasta que instale una RFC personalizada en el sistema SAP. Para obtener instrucciones sobre cómo instalar la solicitud de cambio personalizada, consulte [instalar RFC personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).  
  
 Puede usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] de las maneras siguientes:  
  
-   Para escribir un cliente ADO.NET para conectarse al sistema SAP. La [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] expone ciertas clases que permiten interactuar con el proveedor.  
  
-   Para ejecutar una consulta SELECT en el sistema SAP. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] utiliza la solicitud de cambio personalizada para esta característica.  
  
-   Para ejecutar una operación de ejecución en el sistema SAP. Puede usar esta operación para realizar consultas en el sistema SAP.  
  
-   Para ejecutar una operación de EXECQUERY en el sistema SAP. Puede usar esta operación para ejecutar consultas que ya están definidas en el sistema SAP.  
  
-   Para, a su vez, use la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX complemento expuestas tablas y los módulos de función del sistema SAP. Los nombres de los objetos detectados desde el sistema SAP se escriben en un archivo de configuración, SAPDiscoveredObjects.xml.  
  
-   Para usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] con SQL Server Integration Services (SSIS).  
  
-   Para usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] con SQL Server Reporting Services (SSRS).  
  
 Para obtener más información acerca de cómo realizar estas tareas, consulte [usar .NET Framework Data Provider para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md). Para obtener más información acerca de la solicitud de cambio personalizada, el archivo de configuración de SAPDiscoveredObjects.xml y las limitaciones asociadas con la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], vea los siguientes vínculos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [RFC personalizadas utilizadas por el proveedor de SAP](../../adapters-and-accelerators/adapter-sap/custom-rfcs-used-by-the-provider-in-sap.md)  
  
-   [Acerca del archivo de SAPDiscoveredObjects.xml en SAP](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)  
  
-   [Limitaciones del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/limitations-of-the-net-framework-data-provider-for-mysap-business-suite.md)