---
title: Mensajes de archivo sin formato con registros posicionales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72c17c25-3847-458e-a43e-0dbdc42db749
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26c9e4551abcbd0fba32b21fb8e4205bece6e82f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-messages-with-positional-records"></a>Mensajes de archivo sin formato con registros posicionales
Los registros posicionales dentro de un mensaje de instancia de archivo sin formato contienen campos (elementos de datos) y cada uno de ellos tiene una longitud predefinida. Los campos se analizan según estas longitudes. Por ejemplo, considere el siguiente registro posicional de un mensaje de instancia de archivo sin formato que contiene una dirección de envío (la primera línea muestra el número de caracteres reservados para cada campo).  
  
```  
123456789012345678901234567890123456789012345678901234567890123456789012345  
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952  
```  
  
 Una definición razonable para este registro en un esquema de archivo sin formato se puede describir como un registro posicional llamado shipTo que contiene los campos siguientes:  
  
-   Un atributo denominado country/region, alineado a la izquierda, de 10 caracteres de longitud y con un desplazamiento de caracteres de cero.  
  
-   Un elemento denominado name, alineado a la izquierda, de 20 caracteres de longitud y con un desplazamiento de caracteres de cero.  
  
-   Un elemento denominado street, alineado a la izquierda, de 20 caracteres de longitud y con un desplazamiento de caracteres de cero.  
  
-   Un elemento denominado city, alineado a la izquierda, de 15 caracteres de longitud y con un desplazamiento de caracteres de cero.  
  
-   Un elemento denominado state, alineado a la izquierda, de 2 caracteres de longitud y con un desplazamiento de caracteres de cero.  
  
-   Un elemento denominado zip, alineado a la izquierda, de 5 caracteres de longitud y con un desplazamiento de caracteres de cero.  
  
 Según estas definiciones de registros y campos, el desensamblador de archivos sin formato creará el siguiente XML equivalente de este registro.  
  
```  
<shipTo country/region="US">  
    <name>Alice Smith</name>  
    <street>123 Maple Street</street>  
    <city>Mill Valley</city>  
    <state>CA</state>  
    <zip>90952</zip>  
</shipTo>  
  
```  
  
 Existen varias cuestiones que es necesario tener en cuenta en relación con los registros posicionales, y que afectan a la forma de analizar el registro cuando se recibe y a la forma de construirlo cuando se envía, entre ellas:  
  
-   El carácter utilizado para rellenar la parte no utilizada de cada campo, conocido como carácter controlador. Para obtener más información, consulte [relleno de los campos](../core/field-padding.md).  
  
-   Una etiqueta opcional dentro del registro para distinguir el registro de otros similares. Normalmente, las etiquetas se encuentran al comienzo del registro, aunque se pueden situar en cualquier parte del mismo. Para obtener más información, consulte [tratar las etiquetas en los registros posicionales](../core/tag-handling-in-positional-records.md). Los registros posicionales se pueden definir de modo que tengan o no tengan etiquetas, pero una vez definidos, deben contener o no etiquetas según la definición establecida.  
  
-   Modo de justificar los datos en un campo de longitud fija con respecto a los caracteres controladores existentes. Para obtener más información, consulte [justificación de los campos](../core/field-justification.md).  
  
-   Registros posicionales anidados dentro de otros registros posicionales o delimitados. Para obtener más información, consulte [registros posicionales anidados](../core/nested-positional-records.md).  
  
-   Registros posicionales con longitudes de campo especificadas como un número determinado de bytes en vez de como un número específico de caracteres. Para obtener más información, consulte [contar posiciones en Bytes](../core/position-counting-in-bytes.md).  
  
 Para ayudarle a comprender mejor cómo trabajar con archivos sin formato posicionales, vea los ejemplos disponibles en las carpetas FlatFileReceive y FlatFileSend que se encuentran en \Program [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]\SDK\Samples\Pipelines\AssemblerDisassembler\\.  
  
> [!NOTE]
>  Si el archivo sin formato contiene registros delimitados y posicionales, debe establecer el **estructura** propiedad del nodo raíz a **delimitado** y **estructura** propiedad de los subordinados a cualquiera de los nodos Registro **delimitado** o **posicional** según corresponda.  
  
> [!NOTE]
>  Los campos de los registros posicionales tienen una limitación de 50.000.000 caracteres.  
  
## <a name="see-also"></a>Vea también  
 [Estructura de un mensaje de archivo sin formato](../core/structure-of-a-flat-file-message.md)   
 [Cómo crear esquemas para mensajes de archivo sin formato](../core/how-to-create-schemas-for-flat-file-messages.md)