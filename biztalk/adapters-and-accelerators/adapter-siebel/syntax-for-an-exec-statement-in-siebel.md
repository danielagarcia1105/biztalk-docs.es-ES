---
title: "Sintaxis para una instrucción EXEC en Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
- Data Provider for Siebel, EXEC statement
ms.assetid: c5534102-bf37-4b39-83ab-e09483744c4d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d18481b206b1be7e0062762c1844305fc36e10f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="syntax-for-an-exec-statement-in-siebel"></a>Sintaxis para una instrucción EXEC en Siebel
Mediante el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], los clientes ADO.NET también pueden realizar una operación de EXEC en la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. La sintaxis de la instrucción EXEC es:  
  
```  
EXEC  
<Business Service name>.<Business Service method>  
\<value 1..n>,  
@parameter 1..n [OUTPUT],  
@parameter 1..n = <value>  
  
```  
  
 En la sintaxis anterior, `\<value 1..n>` representa un conjunto de parámetros sin nombre. Éstos son valores codificados de forma rígida. Normalmente representan en parámetros.  También pueden representar parámetros INOUT. Sin embargo, si se usa un valor codificado de forma rígida para un parámetro de entrada, el valor de salida asociado a ese parámetro no se puede recuperar después de ejecuta la instrucción EXEC.  
  
 El `@parameter 1..n` sintaxis representa un conjunto de parámetros con nombre, que pueden ser IN, INOUT, o los parámetros de salida. Los parámetros de salida deben ir seguidos por el **salida** palabra clave.  
  
> [!NOTE]
>  El **salida** palabra clave solo debe utilizarse con los parámetros de salida y no con parámetros INOUT.  
  
 Para especificar valores de parámetro en línea, use la `@parameter 1..n = <value>` sintaxis.  
  
 Todos los parámetros deben ser separados por comas.  
  
 Los siguientes son ejemplos de instrucciones EXEC:  
  
```  
EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo 'InputValue', @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo @InOut, @Out OUTPUT, @In='InputValue'  
  
EXEC ExtractDataService.Echo 'InputValue', @Out OUTPUT, @InOut='InputValue'  
  
```  
  
> [!NOTE]
>  Cada nombre de parámetro (como `@In` en el ejemplo anterior) debe coincidir con el nombre del argumento correspondiente en el método de servicio empresarial de Siebel.  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)