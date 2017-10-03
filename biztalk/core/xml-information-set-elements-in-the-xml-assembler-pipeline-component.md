---
title: "Elementos Set de información XML en el componente de canalización de ensamblador XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], processing instructions
- Add XML declaration property
- XMLNorm.AddXMLDeclaration property
- pipeline components, XML Assembler
- XML Assembler [pipeline component], XML information set
ms.assetid: 5a262763-838e-476b-8117-30c94bc1d64a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b194b85c88f63036cd74fcd9838aa99e73de6556
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xml-information-set-elements-in-the-xml-assembler-pipeline-component"></a>Elementos Set de información XML en el componente de canalización de ensamblador XML
El componente de ensamblador XML controla los elementos Set de información XML como se indica a continuación.  
  
|Elemento|Description|  
|-------------|-----------------|  
|comment|Se conservan los comentarios ubicados entre las etiquetas XML de apertura y de cierre del documento.|  
|CDATA|Se conserva CDATA ubicado entre las etiquetas XML de apertura y de cierre del documento. Los valores de CDATA no se utilizan para promoción de propiedades o campos distintivos.|  
|instrucciones de procesamiento|Antes de la etiqueta XML del documento se controlan las instrucciones de procesamiento en función de su valor (para obtener más información, consulte [instrucciones de procesamiento en el componente de canalización de ensamblador XML](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)). Se conservan las instrucciones de procesamiento ubicadas entre las etiquetas XML de apertura y de cierre del documento. Las instrucciones de procesamiento situadas después de la etiqueta de cierre se omiten, lo mismo que cualquier instrucción que esté ubicada antes, dentro de, o después del sobre.|  
|declaración XML|Cadena de la declaración XML, como `<?xml version='1.0'? encoding='UTF-8'>`, puede que se conserve el componente de canalización de ensamblador XML. Esto se controla mediante la **declaración XML agregar** propiedad, o su equivalente en el contexto del mensaje, **XMLNorm.AddXMLDeclaration**.<br /><br /> Si esta opción está establecida en **True** la declaración XML se agregarán al documento. Si la declaración XML ya existía, se sobrescribirá.<br /><br /> Si esta opción está establecida en **False**, no se agregará ninguna declaración XML y se quitará cualquier declaración XML existente. El valor de esta propiedad en el contexto del mensaje adquiere prioridad sobre el valor especificado en el Diseñador de canalizaciones.<br /><br /> Valor predeterminado: **True** (siempre se agrega la declaración XML)|  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de ensamblador XML](../core/xml-assembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)