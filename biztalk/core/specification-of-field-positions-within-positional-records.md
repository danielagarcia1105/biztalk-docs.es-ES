---
title: Especificación de posiciones de campo en los registros posicionales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33c2eee3-ec30-46c5-a143-a3d2e2f265a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91a253c76e8f3394897514716978e1902cf2e3d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279348"
---
# <a name="specification-of-field-positions-within-positional-records"></a>Especificación de posiciones de campo en los registros posicionales
Para definir un registro posicional, debe proporcionar información acerca de las posiciones y longitudes de los campos de ese registro. Si el registro contiene un subregistro, las posiciones y longitudes de los campos del subregistro se acumulan a la información del registro que lo contiene.  
  
 La suma de los valores especificados para la **desplazamiento posicional** y **longitud posicional** propiedades para un determinado **elemento de campo** o **atributo de campo**  nodo determina el número de caracteres dedicados al campo correspondiente. El conjunto de estas sumas para todos los campos del registro y cualquier subregistro determina los límites de los campos en los registros.  
  
> [!NOTE]
>  Cuando el **contar posiciones en Bytes** propiedad de la **esquema** nodo se establece en **Sí**, **longitud posicional** y  **Posición de desplazamiento** propiedades especifican bytes en lugar de caracteres.  

Ver más detalles acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="positional-offset-property"></a>Propiedad Desplazamiento posicional  
 Cuando el Desensamblador de archivos sin formato convierte un mensaje de instancia de archivo sin formato en el mensaje de instancia XML equivalente, el valor especificado para la **desplazamiento posicional** propiedad define el número de caracteres (o bytes) que se pasan por alto y omitidas sobre en esa posición en el mensaje de instancia. En otras palabras, cualquier información que aparece en esa posición de inicio y la longitud (el último según lo especificado por el **desplazamiento posicional** propiedad) en la instancia de archivo sin formato mensaje no se copiará en la versión XML del mensaje.  
  
 Cuando el ensamblador de archivo sin formato convierte un mensaje de instancia XML en un mensaje de instancia de archivo sin formato equivalente, el valor especificado para la **desplazamiento posicional** propiedad define el número de caracteres (o bytes) que se rellenan con caracteres de espacio en esa posición inicial dentro del mensaje de instancia de archivo sin formato que se está creando. El carácter de espacio siempre se utiliza para rellenar posiciones de desplazamiento; el carácter utilizado no se puede configurar.  
  
 El **desplazamiento posicional** propiedad proporciona flexibilidad para interpretar el contenido de los registros posicionales. Básicamente, esta propiedad permite omitir cualquier dato de longitud fija que esté situado antes de un campo con un valor distinto de cero para esa propiedad. Los datos de longitud fija pueden ser uno o más campos completos de datos o algún tipo de datos constantes, como una etiqueta asociada al campo, que no es necesario que se incluyan en el equivalente XML del mensaje de instancia de archivo sin formato. Para obtener más información, consulte el ejemplo siguiente.  
  
## <a name="positional-length-property"></a>Propiedad Longitud posicional  
 Cuando el Desensamblador de archivos sin formato convierte un mensaje de instancia de archivo sin formato en el mensaje de instancia XML equivalente, el valor especificado para la **longitud posicional** propiedad define el número de caracteres (o bytes) que están asociado con el campo en esa posición en el mensaje de instancia. La información que aparece en el que la posición de inicio y longitud en el mensaje de instancia de archivo sin formato constituye los datos en el campo, sujetas a la información adicional proporcionada por el asociado **justificación** y  **Carácter controlador:** propiedades. Para obtener más información sobre la justificación y relleno de los campos, consulte [justificación de los campos](../core/field-justification.md) y [relleno de los campos](../core/field-padding.md).  
  
 Cuando el ensamblador de archivo sin formato convierte un mensaje de instancia XML en un mensaje de instancia de archivo sin formato equivalente, el valor especificado para la **longitud posicional** propiedad define el número de caracteres (o bytes) disponible para escribir los datos asociados a ese campo. Si el número de caracteres de datos es inferior a lo que especifica la longitud del campo, se utiliza el carácter controlador relevante para rellenar la diferencia. Si no hay más caracteres de datos que la longitud del campo especificada, al principio o al final de los datos se trunca según la configuración de la **justificación** propiedad y no se incluye en el mensaje de instancia de archivo sin formato que se está construir.  
  
> [!NOTE]
>  La parte final de los datos alineados a la izquierda se trunca y se descarta. La parte inicial de los datos alineados a la derecha se trunca y se descarta.  
  
## <a name="example"></a>Ejemplo  
 Considere las siguientes definiciones de campos de un registro.  
  
|Nombre de nodo de campo|Offset|Longitud|Carácter controlador|Justificación|  
|---------------------|------------|------------|-------------------|-------------------|  
|Field1|0|6|Valor predeterminado (espacio)|Izquierda|  
|Field2|0|4|*|Derecha|  
|Field3|2|6|*|Izquierda|  
|Field4|4|6|Valor predeterminado (espacio)|Derecha|  
  
 Además, considere que la siguiente secuencia de caracteres se encuentra en el punto de inicio de un registro con estas definiciones de campos (la primera línea sirve para contar las posiciones de carácter).  
  
```  
123456789012345678901234567890123456789012345678901234567890  
abc   **12345678**skip  here  
```  
  
 Cuando se aplican estas definiciones de campos a estos datos de registro de ejemplo, el desensamblador de archivos sin formato crea el siguiente XML equivalente (datos mostrados en negrita).  
  
```  
<Field1>abc</Field1>  
<Field2>12</Field2>  
<Field3>5678</Field3>  
<Field4>here</Field4>  
```  
  
 Las observaciones siguientes están relacionadas con cómo se analizan estos datos:  
  
-   Los caracteres asociados con Field1 (longitud 6 y sin desplazamiento) son "`abc` ", pero no se incluyen los espacios en el XML porque el carácter de espacio es el carácter controlador (predeterminado) de Field1 y Field1 está definido como alineado a la izquierda.  
  
-   Los caracteres asociados con Field2 (longitud 4 y sin desplazamiento) son "`**12`", pero los asteriscos no se incluyen en el XML porque el carácter de asterisco es el carácter controlador establecido para Field2 y Field2 está definido como alineado a la derecha.  
  
-   Los caracteres asociados con Field3 (longitud 6 y un desplazamiento de 2) es "`345678**`", pero el 3 y 4 no se incluyen en el archivo XML debido al desplazamiento. Los asteriscos tampoco se incluyen en el XML porque el carácter de asterisco es el carácter controlador establecido para Field2, y Field2 está definido como alineado a la izquierda.  
  
-   Los caracteres asociados con Field4 (longitud 6 y un desplazamiento de 4) es "`skip  here`", pero la secuencia de caracteres "`skip`" no se incluye en el archivo XML debido al desplazamiento. Los dos caracteres de espacio tampoco se incluyen en el XML porque el carácter de espacio es el carácter controlador (predeterminado) de Field4, y Field4 está definido como alineado a la derecha.  
  
 Si el XML generado por el Desensamblador de archivos sin formato en este ejemplo se pasa para el ensamblador de archivo sin formato con las mismas definiciones de campo, se generan los mismos datos de archivo plano, con dos excepciones: el desplazamiento descartado secuencias 34 y omitidas se rellenan con caracteres de espacio (indicado con el `^` carácter en la línea siguiente a los datos).  
  
```  
123456789012345678901234567890123456789012345678901234567890  
abc   **12  5678**      here  
          ^^      ^^^^  
  
```  
  
## <a name="see-also"></a>Vea también  
-  [Consideraciones de campo](../core/field-considerations.md)    
-  [Justificación de los campos](../core/field-justification.md)   
-  [Relleno de los campos](../core/field-padding.md)   
- Obtener más información sobre las propiedades siguientes [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    - Contar posiciones en Bytes (propiedad de nodo de esquemas de archivo sin formato)  
    - Justificación (propiedad de nodo de esquemas de archivo sin formato)  
    - Carácter controlador (propiedad de nodo de esquemas de archivo sin formato) 
    - Desplazamiento posicional (propiedad de nodo de esquemas de archivo sin formato)
    - Longitud posicional (propiedad de nodo de esquemas de archivo sin formato)