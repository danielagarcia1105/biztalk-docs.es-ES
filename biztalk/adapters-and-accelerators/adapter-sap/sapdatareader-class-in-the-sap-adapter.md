---
title: Clase SAPDataReader en el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPDataReader, supported methods and classes
ms.assetid: bd0e55ea-7413-498f-851f-ed97bd8bacab
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70fe658058b6d00b4a22b333ef5683a285b9cab3
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sapdatareader-class-in-the-sap-adapter"></a>Clase SAPDataReader en el adaptador SAP
En la siguiente sección se enumera los métodos y propiedades para la **SAPDataReader** clase. Esto se deriva de **System.Data.Common.DbDataReader**.  
  
## <a name="supported-properties"></a>Propiedades admitidas  
  
|Nombre|Get/Set.|Description|  
|----------|--------------|-----------------|  
|**Profundidad**|Obtener|No compatible. Devuelve 0.|  
|**FieldCount**|Obtener|Número de campos en el conjunto de registros actual|  
|**IsClosed**|Obtener|Devuelve el estado del lector de datos|  
|**RecordsAffected**|Obtener|No compatible. Devuelve -1|  
  
## <a name="supported-methods"></a>Métodos admitidos  
  
|Nombre|Description|  
|----------|-----------------|  
|**Close()**|Cierra el DataReader|  
|**Get [métodos]** <sup>*</sup><br /><br /> donde [métodos] es el tipo de datos esperado. Por ejemplo: GetInt32(int)|Obtiene el valor de la columna en función del tipo de datos esperado|  
|**IsDBNull(int)**|No compatible. Devuelve false.|  
  
## <a name="see-also"></a>Vea también  
 [Extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)