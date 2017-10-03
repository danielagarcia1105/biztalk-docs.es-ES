---
title: Caracteres de escape | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af800b9-d31b-487a-9a06-6eda47d1574e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e961a205b77a9944a497d6e6cbed0df71f63e03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="escape-characters"></a>Caracteres de escape

## <a name="overview"></a>Información general
Un carácter de escape es un carácter individual que suprime cualquier significado especial que tenga el carácter que le sigue. Por ejemplo, si define un registro de archivo sin formato con las siguientes características:  
  
-   Nombre = Record1  
  
-   Delimitado  
  
-   Delimitador secundario = coma (,)  
  
-   Orden secundario = prefijo  
  
-   Carácter de escape = barra diagonal inversa (\\)  
  
-   Etiqueta = RECORD1  
  
-   Dos campos denominados Field1 y Field2  
  
 Serán aplicables al registro los datos de archivo sin formato siguientes:  
  
```  
RECORD1,testfield1\,testfield1,testfield2  
                  ^^  
  
```  
  
 Los datos se desensamblarán en el siguiente fragmento de XML.  
  
```  
<Record1>  
    <Field1>testfield1,testfield1</Field1>  
    <Field2>testfield2</Field2>  
</Record1>  
  
```  
  
 Tenga en cuenta que el escape de la secuencia de caracteres `\,` indicado en la línea siguiente del registro de archivo sin formato, se ha convertido en un carácter de coma sin el carácter de escape en los datos de Field1 del registro XML equivalente. Además, el carácter de coma no se ha interpretado como un delimitador de campo como las otras dos comas.  
  
 Cuando el ensamblador de archivos sin formato realice la operación inversa (conversión de la versión XML del registro en el registro de archivo sin formato equivalente), el carácter de escape se insertará antes de la coma, a mitad de los datos de Field1, para indicar que se debe interpretar como datos en lugar de como un delimitador de campo.  
  
 Al crear un esquema de archivo sin formato mediante el Editor de BizTalk, puede definir un carácter de escape predeterminado para el esquema completo mediante el **carácter de Escape predeterminado** y **tipo de carácter de Escape predeterminado** propiedades de la **esquema** nodo. A continuación, puede configurar los registros individuales en el esquema para usar este carácter de escape predeterminado o un carácter de escape personalizado, específico del registro mediante el **carácter de Escape]** y **tipo de carácter de Escape**propiedades de la **registro** nodo.  
  
## <a name="see-also"></a>Vea también  
- [Formas de interpretar los caracteres especiales como parte de un valor de campo](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- Propiedades de carácter de escape [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    - Carácter de Escape predeterminado (propiedad de nodo de esquemas de archivo sin formato)
    - Tipo de carácter de Escape predeterminado (propiedad de nodo de esquemas de archivo sin formato)
    - Carácter de escape (propiedad de nodo de esquemas de archivo sin formato)  
    - Escape de carácter Type (propiedad de nodo de esquemas de archivo sin formato)