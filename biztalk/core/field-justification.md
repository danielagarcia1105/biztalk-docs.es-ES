---
title: "Campo de justificación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04380208-9bfd-43cf-a279-104daea2b978
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da9209040e64380b3a7a167dd013a15232543a75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="field-justification"></a>Justificación de los campos

## <a name="overview"></a>Información general
Por justificación de campo se entiende si los caracteres de datos de un campo aparecen antes (alineados a la izquierda) o después (alineados a la derecha) de cualquier carácter controlador que les acompañe.  
  
 En ocasiones, los caracteres de datos incluidos en un campo no necesitan todo el espacio dedicado a ese campo. Esto es cierto con mayor frecuencia en los registros posicionales, donde el número de bytes o caracteres dedicados a un campo es fijo, según lo determinado por la **longitud posicional** y **desplazamiento posicional** propiedades. Esto es habitual en situaciones en las que el elemento de datos es más pequeño que la longitud de campo, con la parte sin utilizar del campo rellenada con caracteres controladores.  
  
 Tal relleno también puede producirse en los registros delimitados cuando el valor de la **longitud mínima con carácter controlador** propiedad supera el espacio necesario para almacenar el elemento de datos relevante.  
  
 En ambos casos, el valor de la **justificación** propiedad (**izquierda** o **derecha**) de la correspondiente **elemento de campo** o **Atributo de campo** nodo determina si los caracteres controladores seguirá los caracteres de datos (alineados a la izquierda) o si los caracteres controladores estará precedido por los caracteres de datos (alineados a la derecha).  
  
 Cuando el Desensamblador de archivos sin formato convierte un mensaje de instancia de archivo sin formato en el mensaje de instancia XML equivalente, el **justificación** propiedad se utiliza al analizar el campo correspondiente. Cuando el ensamblador de archivo sin formato convierte un mensaje de instancia XML en un mensaje de instancia de archivo sin formato equivalente, el **justificación** propiedad se utiliza para determinar si los caracteres controladores asociados con un campo concreto, si los hay, se debe agregar al flujo de datos: ya sea antes o después de los caracteres de datos correspondiente.  
  
## <a name="see-also"></a>Vea también  
- [Consideraciones de campo](../core/field-considerations.md)   
- Obtener más información sobre las propiedades siguientes [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    - Justificación (propiedad de nodo de esquemas de archivo sin formato)  
    - Desplazamiento posicional (propiedad de nodo de esquemas de archivo sin formato)  
    - Longitud posicional (propiedad de nodo de esquemas de archivo sin formato)