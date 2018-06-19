---
title: Codificación de caracteres en el componente de canalización de desensamblador de archivos sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, Flat File Disassembler
- Flat File Disassembler [pipeline component], character encoding
ms.assetid: 0dbe24fb-c431-4edf-8aa9-4c040d6a7b32
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 839a3377f27417757e394c946fe96acc83752355
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231644"
---
# <a name="character-encoding-in-the-flat-file-disassembler-pipeline-component"></a>Codificación de caracteres en el componente de canalización de desensamblador de archivos sin formato
El componente de desensamblador de archivo sin formato utiliza el siguiente algoritmo para determinar la codificación que se utilizará para procesar un mensaje entrante.  
  
1.  Si en los datos existe una marca de orden de bytes, la información de codificación vendrá determinada por ésta. Esta información de codificación no se conserva el Desensamblador (es decir, no se guarda en el **XMLNorm.SourceCharset** propiedad).  
  
2.  De lo contrario, si la **IBaseMessagePart.Charset** propiedad está establecida, se utiliza la codificación especificada no existe.  
  
3.  En caso contrario, si el encabezado o el esquema de documento contienen información de página de códigos, se utiliza ésta.  
  
4.  En caso contrario, se utiliza la codificación UTF-8.  
  
 Para los anteriores casos 2, 3 y 4, el Desensamblador guarda la información de codificación en el contexto del mensaje en el **XMLNorm.SourceCharset** propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de desensamblador de archivos sin formato](../core/flat-file-disassembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de desensamblador de archivos sin formato](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
 [Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)