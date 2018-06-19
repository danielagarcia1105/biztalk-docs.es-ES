---
title: Types1 básica | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, data types
- JD Edwards OneWorld adapters, business functions
- .NET Framework, mapping [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], data types
- adapters [JD Edwards OneWorld adapters], .NET Framework
- JD Edwards OneWorld adapters, .NET Framework
- adapters [JD Edwards OneWorld adapters], business functions
ms.assetid: d306ea1b-fb74-4fa3-9681-405252928df1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90cda6259567adf5236d0c28e576900d8b25271
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231860"
---
# <a name="basic-types"></a>Tipos básicos
El adaptador de Microsoft BizTalk para JD Edwards OneWorld únicamente proporciona acceso a las funciones de negocio JD Edwards OneWorld. Los metadatos de función de negocio se leen mediante una interfaz de funciones de negocio y se usa para buscar una lista de funciones de negocio y estructuras de datos asociadas. Los metadatos se establecen de forma inflexible en todos los casos para todos los métodos de la función de negocio.  
  
 Todos los métodos de la función de negocio tienen la misma convención de llamada: tres parámetros que se derivan del sistema y un puntero a una estructura de datos. La tabla siguiente muestra cómo se representan los tipos de datos de la función de negocio.  
  
 **Tipos de datos de función de negocio**  
  
|Tipo de datos de OneWorld JD Edwards|Description|Conversión de WDSL|  
|-----------------------------------|-----------------|---------------------|  
|char|Cadena de caracteres.|xsd:cadena de 1|  
|int|Entero corto.|xsd:short|  
|long|Entero largo.|xsd:short|  
|String|Vea [controlar los valores de cadena](../core/handling-string-values1.md).|xsd:cadena|  
|JDEDATE|Implementación especial de fechas.|xsd:fecha|  
|MATH_NUMERIC|Implementación especial de números de coma flotante, incluidos los valores de moneda.|xsd: String de 32|  
|Byte|Único carácter sin signo.|xsd:cadena de 1|  
  
 La tabla siguiente contiene la lista de tipos básicos en JD Edwards OneWorld y cómo se asignan a Microsoft .NET Framework.  
  
 **Tipos básicos y cómo se asignan a Microsoft .NET Framework**  
  
|JD Edwards OneWorld XE|.NET Framework|  
|----------------------------|--------------------|  
|char|String|  
|int|Short|  
|long|Short|  
|String|String|  
|JDEDATE|System.DateTime|  
|MATH_NUMERIC|String|  
|Byte|String|  
  
> [!NOTE]
>  Si solo hay un argumento, y el argumento de devolución es nulo, el marcador se reemplaza por la clase y la porción de salida se convierte en el valor de devolución. Por ejemplo:  
  
```  
org.apache.axis.holders.DateHolder becomes a java.util.Date.   
```  
  
 A continuación se muestra un ejemplo de firmas de método:  
  
```  
void testDate1(org.apache.axis.holders.DateHolder date1  
        org.apache.axis.holders.DateHolder date2);  
  
java.util.Date testDate2(java.util.Date date);  
```  
  
## <a name="character-limited-strings"></a>Cadenas con limitación de caracteres  
 En JD Edwards OneWorld, algunas cadenas tienen los caracteres limitados. Cualquier carácter adicional produce un error. Para ver el límite de caracteres de las cadenas, puede usarse el asistente para adaptadores de Microsoft.  
  
## <a name="see-also"></a>Vea también  
 [Uso del tipo MATH_NUMERIC](../core/using-the-math-numeric-type2.md)   
 [Control de valores de cadena](../core/handling-string-values1.md)   
 [Apéndice A: tipos de datos](../core/appendix-a-data-types.md)