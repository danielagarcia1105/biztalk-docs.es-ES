---
title: "Types2 básica | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, data types
- adapters [JD Edwards EnterpriseOne adapters], data types
- data types, JD Edwards EnterpriseOne adapters
ms.assetid: 96a70f0d-f7f8-4e3b-9511-59b330910ead
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7e5c47d8760e9743ec11a62598581d9d20b3e53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="basic-types"></a>Tipos básicos
Microsoft BizTalk Adapter para JD Edwards EnterpriseOne proporciona acceso únicamente a funciones de negocio de JD Edwards EnterpriseOne. Los metadatos de función de negocio se leen mediante una interfaz de funciones de negocio y se usa para buscar una lista de funciones de negocio y estructuras de datos asociadas. Los metadatos se establecen de forma inflexible en todos los casos para todos los métodos de la función de negocio.  
  
 Todos los métodos de la función de negocio tienen la misma convención de llamada: tres parámetros que se derivan del sistema y un puntero a una estructura de datos. La tabla siguiente muestra cómo se representan los tipos de datos de función de negocio.  
  
|Tipo de datos de JD Edwards EnterpriseOne|Description|Conversión de WDSL|  
|----------------------------------------|-----------------|---------------------|  
|char|Cadena de caracteres.|xsd:cadena de 1|  
|int|Entero corto.|xsd:short|  
|long|Entero largo.|xsd:short|  
|String|Vea [controlar los valores de cadena](../core/handling-string-values2.md).|xsd:cadena|  
|JDEDATE|Implementación especial de fechas.|xsd:fecha|  
|MATH_NUMERIC|Implementación especial de números de coma flotante, incluidos los valores de moneda.|xsd: String de 32|  
|Byte|Único carácter sin signo.|xsd:cadena de 1|  
|JDEUTIME|Incluye tanto el componente de fecha como el de hora.<br /><br /> El tipo de datos almacena todas las fechas y horas y realiza todos los cálculos de fecha y hora en la hora universal coordinada (UTC).|xsd:dateTime|  
  
## <a name="see-also"></a>Vea también  
 [Uso del tipo MATH_NUMERIC](../core/using-the-math-numeric-type1.md)   
 [Control de valores de cadena](../core/handling-string-values2.md)   
 [Apéndice B: tipos de datos](../core/appendix-b-data-types.md)