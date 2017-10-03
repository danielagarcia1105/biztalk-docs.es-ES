---
title: "Codificación de caracteres en el componente de canalización de desensamblador XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], character encoding
- XMLNorm.SourceCharset property
ms.assetid: 37962bdc-cbcb-4559-9ae8-6c4be49b4822
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b0e307f2f608cde266e7a566fb3005bde048c31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="character-encoding-in-xml-disassembler-pipeline-component"></a>Codificación de caracteres en el componente de canalización de desensamblador XML
El desensamblador XML utiliza el siguiente algoritmo para determinar la codificación que se utilizará para procesar los mensajes entrantes:  
  
1.  Si en los datos existe una marca de orden de bytes, la información de codificación vendrá determinada por ésta.  
  
2.  De lo contrario, si la **IBaseMessagePart.Charset** propiedad está establecida, se utiliza la codificación especificada no existe.  
  
3.  En caso contrario, si la declaración XML está presente en el documento XML, se utiliza la codificación que se especifica en él, siempre que la declaración XML sea ANSI.  
  
4.  En caso contrario, se utiliza la codificación UTF-8.  
  
 Para los anteriores casos 2, 3 y 4, después de que el desensamblador XML determine la codificación, guarda en el contexto del mensaje en **XMLNorm.SourceCharset** propiedad. Los mensajes que produce el componente de canalización de desensamblador XML siempre utilizan la codificación UTF-8. En el caso 1, no se conserva la codificación que determinada la marca de orden de bytes.  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de desensamblador XML](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)