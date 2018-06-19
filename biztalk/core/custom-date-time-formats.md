---
title: Formatos de fecha y hora personalizados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5efbec4-3138-44d7-bc76-f9c21547e1d5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1496f1f506df06a4d5569c065cba3bf4f8cbdad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238476"
---
# <a name="custom-date-time-formats"></a>Formatos de fecha y hora personalizados

## <a name="overview"></a>Información general
Debido a sus orígenes, los formatos de archivo sin formato para los que se crean esquemas de archivo sin formato deben usar formatos de fecha y hora que no se ajustan a los formatos ISO 8601. Por lo tanto, si va a crear un esquema de archivo sin formato y establecer el **tipo de datos** propiedad de un **elemento de campo** o **atributo de campo** nodo a uno de los (definición de esquemas XML Tipos de datos primitivos del lenguaje XSD), **xs: DateTime**, **xs: Time**, o **xs: Date**, puede usar el **formato de fecha y hora personalizado**propiedad para especificar un formato alternativo para los valores de fecha u hora.  
  
> [!NOTE]
>  Almacenamiento en el cuadro de mensaje trunca los valores de tiempo en **xs: DateTime** y **xs: Time** elementos por debajo del nivel de milisegundo. Se puede producir una pérdida similar de precisión al convertir los valores a tipos de datos de fecha y hora .NET.  
  
 Cuando este tipo de campo a su equivalente XML traduce el Desensamblador de archivos sin formato, el valor de la **formato de fecha y hora personalizado** propiedad se utilizará para permitir que el formato de fecha y hora de archivo sin formato se convierta en su compatible con ISO 8601 equivalente. Del mismo modo, cuando el ensamblador de archivo sin formato convierte un valor de fecha y hora compatible con ISO 8601 en su equivalente de archivo sin formato, la cadena de formato especificada en la **formato de fecha y hora personalizado** se usará la propiedad construir la fecha apropiada / formato de hora que se espera en el archivo sin formato.  
  
> [!NOTE]
>  De manera predeterminada, los valores correspondientes a los tipos de datos de fecha y hora XSD, de los que existen varios, deben ajustarse a los formatos ISO 8601. En resumen, las fechas se expresan como **aaaa-MM-DD** y horas se expresan como **hh** usando la notación de 24 horas. Cuando aparecen juntos, los valores de fecha y hora se separan mediante el carácter "T": **YYYY:MM:DDThh:mm:ss**.  
  
 Puede configurar la **formato de fecha y hora personalizado** propiedad con casi cualquier formato de fecha y hora, excepto fechas del calendario juliano. La lista desplegable proporciona varias opciones, pero también puede escribir otro formato que prefiera. Los formatos de fecha y hora utilizan Common Language Runtime (CLR) **DateTime** instalaciones. La única excepción es que se antepone automáticamente un signo de porcentaje (%) al carácter individual d, m o M para producir el elemento individual correspondiente del valor DateTime. Los separadores permitidos para los formatos personalizados de fecha y hora son: guión (-), barra diagonal (/) y punto (.). Para obtener más información acerca de **DateTime** formatos, busque "DateTimeFormatInfo" en la colección de documentos de Visual Studio.  
  
## <a name="see-also"></a>Vea también  
-  [Consideraciones de campo](../core/field-considerations.md)   
-  **Tipo de datos (propiedad de nodo de todos los esquemas)** y **formato de fecha y hora personalizado (propiedad de nodo de esquemas de archivo sin formato)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]