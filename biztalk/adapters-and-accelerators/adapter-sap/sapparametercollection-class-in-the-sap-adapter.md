---
title: Clase SAPParameterCollection en el adaptador SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPParameterCollection, supported methods and classes
ms.assetid: fd09355b-95f4-4d49-a643-b13058e63d74
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 924cb884c64f337cec0e628c804b5c5a8c6cf37b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sapparametercollection-class-in-the-sap-adapter"></a>Clase SAPParameterCollection en el adaptador SAP
En la siguiente sección se enumera los métodos y propiedades para la **SAPParameterCollection** clase. Esto se deriva de **System.Data.Common.DbParameterCollection**.  
  
## <a name="supported-properties"></a>Propiedades admitidas  
  
|Nombre|Get/Set.|Description|  
|----------|--------------|-----------------|  
|**Count**|Obtener|Número de parámetros de la colección.|  
|**IsFixedSize**|Obtener|No compatible. Devuelve false.|  
|**IsReadOnly**|Obtener|No compatible. Devuelve false.|  
|**IsSynchronized**|Obtener|No compatible. Devuelve false.|  
|**SyncRoot**|Obtener|Devuelve el objeto de bloqueo.|  
  
## <a name="supported-methods"></a>Métodos admitidos  
  
|Nombre|Description|  
|----------|-----------------|  
|**Add(SAPParameter)**|Parámetro no puede pertenecer a más de un ParameterCollection.|  
|**Add(Object)**|Objeto debe ser del tipo SAPParameter.|  
|**AddRange(System.Array)**|Agrega una matriz de instancias de SAPParameter.|  
|**Clear()**|Borra los parámetros de la colección.|  
|**Contains(Object)**|Comprobaciones en función de la instancia del parámetro.|  
|**Contains(String)**|Comprobación basada en nombre de parámetro.|  
|**CopyTo ([] SAPParameter, int)**|Lista de parámetros de copias en una matriz de tipos de SAPParameter.|  
|**CopyTo (System.Array, int)**|Lista de parámetros de copias en una matriz.|  
|**GetEnumerator()**|Obtiene un enumerador para los parámetros de la colección.|  
|**IndexOf(object)**|Índice del parámetro basado en la instancia de SAPParameter.|  
|**IndexOf(string)**|Índice del parámetro en función del nombre de SAPParameter.|  
|**Insert (int, object)**|Inserta un SAPParameter en la colección.|  
|**Remove(Object)**|Quita un SAPParameter en la colección basándose en la instancia.|  
|**RemoveAt(int)**|Quita un SAPParameter en la colección en un índice determinado.|  
|**RemoveAt(string)**|Quita un SAPParameter en la colección basándose en el nombre.|  
  
## <a name="see-also"></a>Vea también  
 [Extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)