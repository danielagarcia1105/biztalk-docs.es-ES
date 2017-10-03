---
title: Clase SiebelParameter en el adaptador de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SiebelParameter
- Data Provider for Siebel, SiebelParameter
- SiebelParameter, supported properties and methods
ms.assetid: 1dcb72c7-a470-4609-8aba-a5c8ad5f3ac9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27df4b207b23cd04f7d29a2a18ec4ab032836e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="siebelparameter-class-in-the-siebel-adapter"></a>Clase SiebelParameter en el adaptador de Siebel
El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] proporciona un `DbParameter` implementación para permitir que un cliente ADO.NET especificar los parámetros de un comando concreto. Mediante una instancia de la `System.Data.Common.DbCommand` clase de la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], un programa cliente puede obtener una instancia de la `System.Data.Common.DbParameter` clase.  
  
```  
//In this example, command is an instance of DbCommand  
DbParameter param = command.CreateParameter();  
```  
  
 También se puede usar el siguiente método:  
  
```  
  
//Here command is an instance of SiebelCommand  
SiebelParameter param = (SiebelParameter) command.CreateParameter();                  
param.ParameterName = "@Time";  
```  
  
 El `SiebelParameter` clase hereda de `DbParameter`.  Se encuentra en el espacio de nombres `Microsoft.Data.SiebelClient`.  
  
## <a name="supported-properties"></a>Propiedades admitidas  
 El `SiebelParameter` clase admite las siguientes `DbParameter` *público* propiedades:  
  
|Nombre|Get/Set.|Description|  
|----------|--------------|-----------------|  
|**DbType**|Get y Set|Tipo de datos del parámetro. Vea [tipos de datos básicos de Siebel](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).|  
|**Dirección**|Get y Set|Se admiten los siguientes valores:<br /><br /> -                     `ParameterDirection.Input`<br /><br /> -                     `ParameterDirection.Output`<br /><br /> -                     `ParameterDirection.InputOutput`|  
|**IsNullable**|Get y Set|La propiedad no se admite e iniciará una excepción si se llama.|  
|**ParameterName**|Get y Set|El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] es compatible con esta propiedad para un cliente ADO.NET especificar el nombre del parámetro.|  
|**Valor**|Get y Set|El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] representa valores de parámetro como cadenas.|  
  
###  <a name="BKMK_Datatypes"></a>Tipos de datos admitidos  
 En la tabla siguiente se resume los más sencillos tipos de campo de Siebel que [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] admite. Para obtener cobertura más detallada, vea [tipos de datos básicos de Siebel](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).  
  
|Tipo de campo de Siebel|Tipo .NET|Tipo de esquema XML|  
|-----------------------|---------------|---------------------|  
|DTYPE_BOOL|Boolean|xsd:boolean|  
|DTYPE_CURRENCY|Decimal|xsd:decimal|  
|DTYPE_DATE|DateTime|xsd:dateTime|  
|DTYPE_DATETIME|DateTime|xsd:dateTime|  
|UTCDATETIME DTYPE_|DateTime|xsd:dateTime|  
|DTYPE_ID|String|xsd:cadena|  
|DTYPE_INTEGER|Integer|xsd:int|  
|DTYPE_NOTE|String|xsd:cadena|  
|DTYPE_NUMBER|Decimal|xsd:decimal|  
|DTYPE_PHONE|String|xsd:cadena|  
|DTYPE_TEXT|String|xsd:cadena|  
|DTYPE_TIME|DateTime|xsd:dateTime|  
  
## <a name="supported-methods"></a>Métodos admitidos  
 El `SiebelParameter` clase no invalida los métodos especiales en `DbParameter`.  
  
## <a name="see-also"></a>Vea también  
 [Extender Interfaces de ADO.NET con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)