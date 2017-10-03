---
title: "Tipos de Variable de propiedad de configuración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, properties
- binding files, properties
- binding files, data types
- adapters, data types
ms.assetid: 703219ce-e275-4a07-a2ad-28010d8363e6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05b861100fb7843a95b250c233084c13924c28dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-property-variable-types"></a>Tipos de variables de la propiedad Configuración
Las propiedades de configuración del adaptador en un nodo TransportTypeData\CustomProps de un archivo de enlace tienen en cuenta los tipos de datos disponibles en la enumeración VarEnum de .NET Framework. Los tipos de datos importantes se enumeran en la siguiente tabla:  
  
|Nombre de miembro|Description|Value|  
|-----------------|-----------------|-----------|  
|VT_EMPTY|Indica que no se ha especificado un valor.|0|  
|VT_NULL|Indica un valor nulo; similar a un valor nulo en SQL.|1|  
|VT_I2|Indica un entero corto.|2|  
|VT_I4|Indica un entero largo.|3|  
|VT_R4|Indica un valor de tipo Float.|4|  
|VT_R8|Indica un valor doble.|5|  
|VT_CY|Indica un valor de moneda.|6|  
|VT_DATE|Indica un valor DATE.|7|  
|VT_BSTR|Indica una cadena BSTR.|8|  
|VT_DISPATCH|Indica un puntero IDispatch.|9|  
|VT_ERROR|Indica un SCODE.|10|  
|VT_BOOL|Indica un valor booleano.|11|  
|VT_VARIANT|Indica un puntero lejano VARIANT.|12|  
|VT_UNKNOWN|Indica un puntero IUnknown.|13|  
|VT_DECIMAL|Indica un valor decimal.|14|  
|VT_I1|Indica un valor de carácter.|16|  
|VT_UI1|Indica un byte.|17|  
|VT_UI2|Indica un entero corto sin signo.|18|  
|VT_UI4|Indica un entero largo sin signo.|19|  
|VT_I8|Indica un entero de 64 bits.|20|  
|VT_UI8|Indica un entero de 64 bits sin signo.|21|  
|VT_CLSID|Indica un Id. de clase.|72|  
|VT_ARRAY|Indica un puntero SAFEARRAY.|8192|  
|VT_BYREF|Indica que un valor es una referencia.|16384|