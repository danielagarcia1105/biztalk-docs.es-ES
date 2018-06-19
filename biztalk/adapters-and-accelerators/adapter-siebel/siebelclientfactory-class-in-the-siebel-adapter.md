---
title: Clase SiebelClientFactory en el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelClientFactory
- Data Provider for Siebel, SiebelClientFactory
- SiebelClientFactory, supported properties and methods
ms.assetid: f3a807d3-a030-47d8-b145-e18075ec353c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50e47b22c1d5a2575b0da3fae432acd79886e2c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222068"
---
# <a name="siebelclientfactory-class-in-the-siebel-adapter"></a>Clase SiebelClientFactory en el adaptador de Siebel
Un cliente ADO.NET tiene acceso a la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] con interfaces y clases ADO.NET genéricas. Para habilitar esta característica, el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] hereda el **System.Data.Common.DbProviderFactory** clase. El programa cliente consume al cliente como sigue:  
  
```  
  
DbProviderFactory factory = DbProviderFactories.GetFactory("Microsoft.Data.SiebelClient");  
DbConnection connection = factory.CreateConnection();  
```  
  
 Un enfoque alternativo es como sigue:  
  
```  
SiebelClientFactory factory = SiebelClientFactory.Instance;  
DbConnection connection = factory.CreateConnection();  
```  
  
 SiebelClientFactory existe en el espacio de nombres Microsoft.Data.SiebelClient.  
  
## <a name="supported-members"></a>Miembros admitidos  
 **SiebelClientFactory** extiende **System.Data.CommonDbProviderFactory**.  En la tabla siguiente proporciona una descripción de los miembros que **SiebelClientFactory** invalida.  
  
|Nombre|Description|  
|----------|-----------------|  
|**Instancia**|Se trata de una variable de miembro.  Proporciona una instancia de singleton de SiebelClientFactory.|  
|**CreateCommand()**|Crea una instancia de SiebelCommand.|  
|**CreateConnection()**|Crea una instancia de SiebelConnection.|  
|**CreateConnectionStringBuilder()**|Crea una instancia de SiebelConnectionStringBuilder.|  
|**CreateParameter()**|Crea una instancia de SiebelParameter.|  
  
## <a name="see-also"></a>Vea también  
 [Extender Interfaces de ADO.NET con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)