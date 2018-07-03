---
title: Clase SiebelParameter del adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelParameter
- Data Provider for Siebel, SiebelParameter
- SiebelParameter, supported properties and methods
ms.assetid: 1dcb72c7-a470-4609-8aba-a5c8ad5f3ac9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cff2f0f5324dfacd118bc59dccfa524819acaa75
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021954"
---
# <a name="siebelparameter-class-in-the-siebel-adapter"></a>Clase SiebelParameter del adaptador de Siebel
El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] proporciona un `DbParameter` implementación para permitir que un cliente ADO.NET especificar los parámetros de un comando concreto. Mediante una instancia de la `System.Data.Common.DbCommand` clase de la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], un programa cliente puede obtener una instancia de la `System.Data.Common.DbParameter` clase.  

```  
//In this example, command is an instance of DbCommand  
DbParameter param = command.CreateParameter();  
```  

 Como alternativa, puede usarse el siguiente enfoque:  

```  

//Here command is an instance of SiebelCommand  
SiebelParameter param = (SiebelParameter) command.CreateParameter();                  
param.ParameterName = "@Time";  
```  

 El `SiebelParameter` clase hereda de `DbParameter`.  Existe en el espacio de nombres `Microsoft.Data.SiebelClient`.  

## <a name="supported-properties"></a>Propiedades admitidas  
 El `SiebelParameter` clase admite las siguientes `DbParameter` *pública* propiedades:  


|       Nombre        |   Get/Set.   |                                                                                                            Descripción                                                                                                            |
|-------------------|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    **DbType**     | Get y Set. |                                               Tipo de datos del parámetro. Consulte [los tipos de datos básicos de Siebel](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).                                               |
|   **Dirección**   | Get y Set. | Se admiten los siguientes valores:<br /><br /> -                     `ParameterDirection.Input`<br /><br /> -                     `ParameterDirection.Output`<br /><br /> -                     `ParameterDirection.InputOutput` |
|  **IsNullable**   | Get y Set. |                                                                               La propiedad no se admite y producirá una excepción si se llama.                                                                               |
| **ParameterName** | Get y Set. |                                  El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] compatible con esta propiedad para un cliente ADO.NET para especificar el nombre del parámetro.                                  |
|     **Value**     | Get y Set. |                                                    El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] representa valores de parámetro como cadenas.                                                    |

###  <a name="BKMK_Datatypes"></a> Tipos de datos admitidos  
 En la tabla siguiente se resume los más sencillos que los tipos de campo de Siebel [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] admite. Para obtener cobertura más detallada, consulte [tipos de datos básicos de Siebel](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).  

|Tipo de campo de Siebel|Tipo .NET|Tipo de esquema XML|  
|-----------------------|---------------|---------------------|  
|DTYPE_BOOL|Boolean|xsd:boolean|  
|DTYPE_CURRENCY|Decimal|xsd:decimal|  
|DTYPE_DATE|DateTime|xsd:dateTime|  
|DTYPE_DATETIME|DateTime|xsd:dateTime|  
|DTYPE_ UTCDATETIME|DateTime|xsd:dateTime|  
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
 [Ampliar Interfaces de ADO.NET con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)