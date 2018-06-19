---
title: Mensajes de archivo sin formato con registros delimitados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ad7119b-4e39-43df-9dba-a04382eb6db2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5dc9eb0253e2bfe8824f6395e1c619c23f0e551
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "22246716"
---
# <a name="flat-file-messages-with-delimited-records"></a>Mensajes de archivo sin formato con registros delimitados
Los registros delimitados de un mensaje de instancia de archivo sin formato contienen registros o campos individuales (elementos de datos) anidados, separados con un carácter o un conjunto de caracteres predefinido. Los campos se analizan según estos delimitadores de separación. Por ejemplo, considere los siguientes registros delimitados de un mensaje de instancia de archivo sin formato con dos elementos de línea de un pedido hipotético:  
  
```  
  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Electric-120vac,ITEM926-AA|Baby Monitor|1|39.98|Electric-4AA|2004-01-21  
  
```  
  
 Una definición aceptable de este registro de esquema de archivo sin formato sería la que se describe a continuación:  
  
-   Un registro delimitado denominado "items" con el delimitador secundario (,), el prefijo de orden secundario y la etiqueta ITEMS.  
  
    -   A delimitados, repitiendo registro con el nombre de elemento con el delimitador secundario &#124;, infijo de orden secundario y la etiqueta de elemento.  
  
    -   Un atributo denominado "partNum".  
  
    -   Un elemento denominado "productName".  
  
    -   Un elemento denominado "quantity".  
  
    -   Un elemento denominado "USPrice".  
  
    -   Un elemento denominado "powerSource".  
  
-   Un elemento opcional denominado "shipDate".  
  
 Según estas definiciones de registros y campos, el desensamblador de archivos sin formato crea los siguientes equivalentes XML de los registros.  
  
```  
  
<items>  
    <item partNum="872-AA">  
        <productName>Lawnmower</productName>  
        <quantity>1</quantity>  
        <USPrice>148.95</USPrice>  
        <powerSource>Electric-120vac</powerSource>  
    </item>  
    <item partNum="926-AA">  
        <productName>Baby Monitor</productName>  
        <quantity>1</quantity>  
        <USPrice>39.98</USPrice>  
        <powerSource>Electric-4AA</powerSource>  
        <shipDate>2004-01-21</shipDate>  
    </item>  
</items>  
  
```  
  
 Existen varias cuestiones que es necesario tener en cuenta con relación a los registros delimitados y que afectan a cómo se analiza el registro cuando se recibe y cómo se crea cuando se envía, entre ellas:  
  
-   El carácter o los caracteres utilizados para que se invalide su interpretación como delimitadores de modo que se consideren parte de los datos. Para obtener más información, consulte [formas de interpretar los caracteres especiales como parte de un valor de campo](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md).  
  
-   Una etiqueta opcional al principio del registro para distinguir el registro de otros similares. Para obtener más información, consulte [tratamiento de las etiquetas en los registros delimitados](../core/tag-handling-in-delimited-records.md).  
  
-   Cómo se justifican los datos en los campos con una longitud mínima con respecto a los caracteres controladores existentes. Para obtener más información, consulte [relleno de los campos](../core/field-padding.md), [justificación de los campos](../core/field-justification.md), y [mínimo campo longitudes de los registros delimitados](../core/minimum-field-lengths-within-delimited-records.md).  
  
-   Registros posicionales anidados dentro de otros registros delimitados. Para obtener más información, consulte [registros delimitados y posicionales anidados](../core/nested-positional-and-delimited-records.md).  
  
-   Cómo se justifican los datos en un campos de longitud fija con respecto a los caracteres controladores existentes. Para obtener más información, consulte [justificación de los campos](../core/field-justification.md).  
  
-   Consideraciones acerca de la posición de los delimitadores respecto a los datos que delimitan. Para obtener más información, consulte [consideraciones acerca del orden secundario](../core/child-order-considerations.md).  
  
-   Conservar y suprimir los delimitadores cuando se reciben y envían mensajes de archivo sin formato. Para obtener más información, consulte [conservar y suprimir delimitadores](../core/delimiter-preservation-and-suppression.md).  
  
 Para ayudarle a comprender mejor cómo trabajar con archivos sin formato delimitados, vea los ejemplos disponibles en las carpetas FlatFileReceive y FlatFileSend que se encuentran en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\.  
  
> [!NOTE]
>  Si el archivo sin formato contiene registros delimitados y posicionales, debe establecer el **estructura** propiedad del nodo raíz a **delimitado** y **estructura** propiedad de los subordinados a cualquiera de los nodos Registro **delimitado** o **posicional** según corresponda.  
  
> [!NOTE]
>  Los campos delimitados de los archivos sin formato tienen un límite de 50.000.000 caracteres.  
  
## <a name="see-also"></a>Vea también  
 [Estructura de un mensaje de archivo sin formato](../core/structure-of-a-flat-file-message.md)   
 [Cómo crear esquemas para mensajes de archivo sin formato](../core/how-to-create-schemas-for-flat-file-messages.md)   
 [Migración de registros de archivo sin formato](../core/migrating-flat-file-records.md)