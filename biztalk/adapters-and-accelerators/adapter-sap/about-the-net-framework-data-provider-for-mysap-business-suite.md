---
title: Sobre el proveedor de datos de .NET Framework para mySAP Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ee712f6b818b94ca731d94165cd345a3249a61d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978917"
---
# <a name="about-the-net-framework-data-provider-for-mysap-business-suite"></a>Sobre el proveedor de datos de .NET Framework para mySAP Business Suite
Esta sección proporciona información sobre la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) y sus características. Para obtener instrucciones sobre cómo usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [usar el proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).  
  
> [!NOTE]
>  Incluso si decide instalar la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] como parte de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación, su [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] todavía está incompleta hasta que instale una RFC personalizada en el sistema SAP. Para obtener instrucciones sobre cómo instalar la RFC personalizada, consulte [instalar RFC personalizadas para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).  
  
 Puede usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] de las maneras siguientes:  
  
- Para escribir un cliente de ADO.NET para conectarse al sistema SAP. La [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] expone algunas clases que permiten interactuar con el proveedor.  
  
- Para ejecutar una consulta SELECT en el sistema SAP. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] usa la RFC personalizada para esta característica.  
  
- Para ejecutar una operación de ejecución en el sistema SAP. Esta operación se puede usar para realizar consultas en el sistema SAP.  
  
- Para ejecutar una operación de EXECQUERY en el sistema SAP. Puede utilizar esta operación para ejecutar consultas que ya están definidas en el sistema SAP.  
  
- A su vez, utilice el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX complemento a las tablas de superficie y los módulos de función desde el sistema SAP. Los nombres de los objetos detectados desde el sistema SAP se escriben en un archivo de configuración SAPDiscoveredObjects.xml.  
  
- Para usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] con SQL Server Integration Services (SSIS).  
  
- Para usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] con SQL Server Reporting Services (SSRS).  
  
  Para obtener más información acerca de cómo realizar estas tareas, consulte [usar el proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md). Para obtener más información acerca de la solicitud de cambio personalizada, el archivo de configuración SAPDiscoveredObjects.xml y las limitaciones asociadas con el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte los vínculos siguientes.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [RFC personalizadas usadas por el proveedor de SAP](../../adapters-and-accelerators/adapter-sap/custom-rfcs-used-by-the-provider-in-sap.md)  
  
-   [Acerca del archivo SAPDiscoveredObjects.xml en SAP](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)  
  
-   [Limitaciones del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/limitations-of-the-net-framework-data-provider-for-mysap-business-suite.md)