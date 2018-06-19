---
title: Codificación de caracteres en el componente de canalización de ensamblador de archivo sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Flat File Assembler [pipeline component], character encoding
- IBaseMessagePart.Charset property
- pipeline components, Flat File Assembler
- Codepage property
- XMLNorm.SourceCharset property
- XMLNorm.TargetCharset property
- Target Charset property
ms.assetid: 0cf3c0fd-f036-4190-83ce-9064ef4e823c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af38855c81129cd4bafff50544f2aee15e6f3fab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232124"
---
# <a name="character-encoding-in-the-flat-file-assembler-pipeline-component"></a>Codificación de caracteres en el componente de canalización de ensamblador de archivo sin formato
El ensamblador de archivo sin formato puede crear mensajes con una codificación de caracteres especificada por el usuario. Puede especificar la codificación de caracteres en varios niveles:  
  
-   **Esquema.** Establecer el **codepage** propiedad en el esquema de archivo sin formato para el documento.  
  
-   **Componente.** Establecer el **juego de caracteres de destino** propiedad del componente en el Diseñador de canalizaciones.  
  
-   **Mensaje.** Establecer el **XMLNorm.TargetCharset** propiedad en el contexto del mensaje.  
  
 El valor de la propiedad establecida en un contexto del mensaje siempre reemplaza la establecida en el Diseñador de canalizaciones. Además, el valor establecido en el Diseñador de canalizaciones siempre sobrescribe el valor establecido como un **codepage** propiedad en un esquema de documento de archivo sin formato.  
  
 El ensamblador de archivo sin formato utiliza el siguiente algoritmo para determinar la codificación que se utilizará para un mensaje de salida:  
  
-   Si el **XMLNorm.TargetCharset** se establece la propiedad de contexto, su valor se utiliza para codificar.  
  
-   De lo contrario, si la **juego de caracteres de destino** se especifica la propiedad en el Diseñador de canalizaciones, se utiliza su valor.  
  
-   De lo contrario, si la **codepage** se especifica la propiedad en el esquema de archivo sin formato, se utiliza su valor.  
  
-   De lo contrario, si la **XMLNorm.SourceCharset** propiedad se especifica, se utiliza su valor.  
  
-   O bien, se utiliza "UTF-8". Observe que el componente de canalización de ensamblador de archivo sin formato no pone marca de orden de bytes en los mensajes salientes cuando se utiliza la codificación UTF-8.  
  
 El ensamblador de archivo sin formato guarda la información de codificación en la parte del cuerpo del objeto de mensaje de BizTalk en el **IBaseMessagePart.Charset** propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de ensamblador de archivo sin formato](../core/flat-file-assembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de ensamblador de archivo sin formato](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)   
 [Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)