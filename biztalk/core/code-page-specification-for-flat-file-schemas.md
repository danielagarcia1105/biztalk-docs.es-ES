---
title: Especificación de la página para esquemas de archivo sin formato de código | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 825e75f1-893c-4c61-b566-f893d732a907
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64d5cfbc960346e702ed0d4a39ca74bbc4b3634c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232268"
---
# <a name="code-page-specification-for-flat-file-schemas"></a>Especificación de la página de código para esquemas de archivo sin formato

## <a name="overview"></a>Información general
El valor de la **página de códigos** propiedad se utiliza para crear un objeto de codificación que se utiliza durante el desensamblado y ensamblado de documentos de archivo sin formato. Este objeto de codificación permite al analizador de archivos sin formato convertir la codificación nativa de un documento de archivo sin formato entrante en la codificación UTF-8 normalizado que se usa internamente en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El objeto de codificación también permite al serializador de archivo sin formato volver a convertir la codificación interna UTF-8 en la codificación nativa del documento de archivo sin formato.  
  
 La configuración de la **página de códigos** propiedad desempeña un papel importante, pero no exclusivo, para determinar el esquema de codificación de caracteres utilizado por los documentos empresariales de archivo sin formato. Es necesario tener en cuenta cómo el desensamblador de archivos sin formato interpreta los mensajes de archivo sin formato de entrada y cómo el ensamblador de archivos sin formato codificará los caracteres cuando los mensajes de salida se traduzcan al formato de archivo sin formato.  

## <a name="character-encoding"></a>Codificación de caracteres  
 Hay varios factores que influyen en la determinación de cómo se trata la codificación de caracteres de un determinado mensaje de instancia, entre ellos:  
  
-   Al desensamblar un mensaje de instancia de archivo sin formato, se utiliza el algoritmo siguiente para determinar y mantener la información de codificación:  
  
    1.  Si el **Charset** en la parte del cuerpo del mensaje se establece, se utiliza su valor.  
  
    2.  En caso contrario, si el esquema de sobre (o documento) especifica una página de código mediante la **página de códigos** se utiliza su valor de la propiedad.  
  
    3.  O bien, si hay una marca de orden de bytes, se utiliza su valor.  
  
    4.  En caso contrario, considere usar UTF-8.  
  
-   Al ensamblar un mensaje de instancia de archivo sin formato, se utiliza el algoritmo siguiente para determinar el juego de caracteres que se debe usar para la descodificación:  
  
-   Si el **XMLNorm.TargetCharset** se establece la propiedad de contexto de mensaje, se utiliza su valor.  
  
-   De lo contrario, si la **TargetCharset** se establece la propiedad del ensamblador (tiempo de diseño), se utiliza su valor.  
  
-   En caso contrario, si el esquema de sobre (o documento) especifica una página de código mediante la **página de códigos** se utiliza su valor de la propiedad.  
  
    1.  De lo contrario, si la **SourceCharset** se establece la propiedad de contexto de mensaje, se utiliza su valor.  
  
    2.  En caso contrario, utilice UTF-8.  
  
## <a name="see-also"></a>Vea también  
 **Consideraciones al crear planos esquemas de mensaje de archivo** y **(propiedad de nodo de esquemas de archivo sin formato) de la página de códigos**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]