---
title: "Elementos Set de información XML en el componente de canalización de desensamblador XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], information set
- XML Disassembler [pipeline component], processing instructions
- pipeline components, XML Disassembler
ms.assetid: cc82344c-6c4b-4154-a662-0b7ae5caad30
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90b3140cbe23637160aafabdccb37104efd1d318
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xml-information-set-elements-in-the-xml-disassembler-pipeline-component"></a>Elementos Set de información XML en el componente de canalización de desensamblador XML
El desensamblador XML controla los elementos Set de información XML como se indica a continuación.  
  
|Elemento|Description|  
|-------------|-----------------|  
|comment|Se conservan los comentarios en el documento, sin embargo, no sucede igual con los comentarios de los sobres XML.|  
|CDATA|CDATA se conserva en el documento. Los elementos CDATA que aparecen fuera de un documento (por ejemplo, en un sobre) no se conservan.|  
|instrucciones de procesamiento|El desensamblador XML conserva las instrucciones de procesamiento que aparecen dentro o antes de un documento XML. Las instrucciones de procesamiento que aparecen después de un documento XML o antes o después de un sobre no se conservan.|  
|declaración XML|Se quita el elemento de declaración XML de cualquier mensaje entrante XML.|  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de desensamblador XML](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)