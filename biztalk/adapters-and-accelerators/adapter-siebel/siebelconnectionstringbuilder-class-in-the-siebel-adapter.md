---
title: Clase SiebelConnectionStringBuilder en el adaptador de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SiebelConnectionStringBuilder, supported properties and methods
- Data Provider for Siebel, SiebelConnectionStringBuilder
- SiebelConnectionStringBuilder
ms.assetid: 4995fce8-7e62-4af9-a731-47b16438067c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 088748c63983e76e64d32f54b3e999fadd88d23a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="siebelconnectionstringbuilder-class-in-the-siebel-adapter"></a>Clase SiebelConnectionStringBuilder en el adaptador de Siebel
El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] proporciona un `DbConnectionStringBuilder` entornos para obtener las propiedades de conexión de herramientas de implementación para habilitar el Explorador de SQL Server Integration Services (SSIS) y Visual Studio la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] y mostrarlos en forma de una interfaz gráfica de usuario controlada por el PropertyGrid.  
  
 Para crear un SiebelConnectionStringBuilder, emplee el siguiente método:  
  
```  
  
//In this example, factory is an instance of SiebelClientFactory  
SiebelConnectionStringBuilder bldr = (SiebelConnectionStringBuilder)factory.CreateConnectionStringBuilder();  
bldr.ConnectionString = connstr;  
```  
  
 O bien, simplemente:  
  
```  
  
SiebelConnectionStringBuilder bldr = new SiebelConnectionStringBuilder();  
```  
  
 Para ver las claves y valores que se admiten como parte de la `DbConnectionStringBuilder`, consulte [propiedades del proveedor de datos de la cadena de conexión de Siebel](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).  
  
## <a name="see-also"></a>Vea también  
 [Extender Interfaces de ADO.NET con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)