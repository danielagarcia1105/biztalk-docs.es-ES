---
title: Clase SAPParameter en el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPParameter, supported methods, classes, and constructors
ms.assetid: 60053393-ad22-4c99-abae-e538d43c8e18
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ff43c344cc14adb3deef226c270adc3ca94f2a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218004"
---
# <a name="sapparameter-class-in-the-sap-adapter"></a>Clase SAPParameter en el adaptador SAP
En la siguiente sección se enumera los métodos y propiedades para la **SAPParameter** clase. Esto se deriva de **System.Data.Common.DbParameter**.  
  
## <a name="supported-properties"></a>Propiedades admitidas  
  
|Nombre|Get/Set.|Description|  
|----------|--------------|-----------------|  
|**DbType**|Obtener|DbType si el parámetro devuelto. No se puede establecer.|  
|**Dirección**|Get y Set|ParameterDirection.ReturnValue no compatible.|  
|**IsNullable**|-|No compatible.|  
|**ParameterName**|Get y Set|Nombre del parámetro.|  
|**Tamaño**|-|No compatible.|  
|**SourceColumn**|-|No compatible.|  
|**SourceColumnNullMapping**|-|No compatible.|  
|**SourceVersion**|-|No compatible.|  
|**Valor**|Get y Set|Valor del parámetro|  
  
## <a name="supported-methods"></a>Métodos admitidos  
  
|Nombre|Description|  
|----------|-----------------|  
|**ResetDbType()**|No compatible.|  
  
## <a name="supported-constructors"></a>Constructores  
  
|Nombre|Description|  
|----------|-----------------|  
|**SAPParameter()**|Instancia de parámetro SAP.|  
|**SAPParameter(string)**|Parámetro SAP con el nombre de parámetro SAP.|  
|**SAPParameter (string, DbType)**|Parámetro SAP con el nombre del parámetro SAP y DbType.|  
|**SAPParameter (string, object)**|Parámetro SAP con el nombre del parámetro SAP y el valor. Tipos complejos tienen el valor de tipo DataTable y cadena XML.|  
|**SAPParameter (string, ParameterDirection)**|Parámetro SAP con la dirección de parámetro y nombre del parámetro SAP.|  
  
## <a name="see-also"></a>Vea también  
 [Extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)