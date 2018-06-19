---
title: Clase SAPClientFactory en el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPClientFactory, supported methods and classes
ms.assetid: e64de5e4-e53f-4708-ab02-9e12774e94cd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c82e4bea6a16085608ebf1f8fe10ea95b4db394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217636"
---
# <a name="sapclientfactory-class-in-the-sap-adapter"></a>Clase SAPClientFactory en el adaptador SAP
En la siguiente sección se enumera los métodos y propiedades para la **SAPClientFactory** clase. Esto se deriva de **System.Data.Common.DbProviderFactory**.  
  
## <a name="supported-properties"></a>Propiedades admitidas  
  
|Nombre|Get/Set.|Description|  
|----------|--------------|-----------------|  
|**Instancia**|-|Instancia de singleton de SAPClientFactory|  
  
## <a name="supported-methods"></a>Métodos admitidos  
  
|Nombre|Description|  
|----------|-----------------|  
|**CreateCommand()**|Crea una instancia de SAPCommand|  
|**CreateConnection()**|Crea una instancia de SAPConnection|  
|**CreateConnectionStringBuilder()**|Crea una instancia de SAPConnectionStringBuilder|  
|**CreateParameter()**|Crea una instancia de SAPParameter|  
  
## <a name="see-also"></a>Vea también  
 [Extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)