---
title: Instrucciones de procesamiento en el componente de canalización de ensamblador XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.ProcessingInstructionOption property
- envelopes, processing instructions
- XML Assembler [pipeline component], processing instructions
- Processing instruction scope property
- XMLNorm.ProcessingInstruction property
- envelopes, XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: d8ea453e-3b20-417d-bf25-9d424b0150fd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85ac6045084c0aea672b0c1e9d6dfb1b4a742d55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265156"
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a>Instrucciones de procesamiento en el componente de canalización de ensamblador XML
Las instrucciones de procesamiento proporcionan información a la aplicación que procesa un documento XML. Dicha información puede incluir instrucciones sobre cómo procesar el documento, cómo mostrarlo, etc.  
  
 Las instrucciones de procesamiento se agregan a un documento XML mediante el **agregar instrucciones de procesamiento** propiedad (o el equivalente **XMLNorm.ProcessingInstructionOption** propiedad en el contexto del mensaje). Texto de la instrucción de procesamiento se especifica con el **agregar texto de instrucciones de procesamiento** propiedad (o el equivalente **XMLNorm.ProcessingInstruction** propiedad en el contexto del mensaje).  
  
 El **agregar instrucciones de procesamiento** propiedad (o **XMLNorm.ProcessingInstructionOption** propiedad) tiene tres valores posibles, que se describen en la tabla siguiente.  
  
|Valor|Valor|Description|  
|-----------|-----------|-----------------|  
|Anexar|0|Las nuevas instrucciones de procesamiento del ensamblador XML se agregan a las ya existentes al principio del documento.|  
|Crear nuevo|1|Las nuevas instrucciones de procesamiento del ensamblador XML sobrescriben las ya existentes al principio del documento.|  
|Omitir|2|Se quitan las instrucciones de procesamiento que se encuentran al principio del documento.|  
  
 Las dos instrucciones de procesamiento (o propiedades de contexto de mensaje) especificadas en el contexto de un mensaje adquieren prioridad sobre las dos propiedades especificadas en el Diseñador de canalizaciones. Por ejemplo, si **XMLNorm.ProcessingInstructionOption** se especifica como **crear nuevo** (1) y **XMLNorm.ProcessingInstruction** no se especifica un procesamiento vacío instrucción reemplazará una instrucción de procesamiento existente.  
  
 Como otro ejemplo, si **XMLNorm.ProcessingInstruction** se especifica pero **XMLNorm.ProcessingInstructionOption** no lo es, se utiliza ninguna de las propiedades del contexto del mensaje. En este caso, se utilizan las instrucciones de procesamiento del Diseñador de canalizaciones.  
  
 De forma predeterminada, **agregar instrucciones de procesamiento** está establecido en **anexado**, y **agregar texto de instrucciones de procesamiento** está vacía.  
  
## <a name="processing-properties-and-envelopes"></a>Propiedades de procesamiento y sobres  
 Las instrucciones de procesamiento no se mantienen para los sobres por lo que la siguiente combinación de valores de ensamblador de archivo sin formato hace que solo el sobre más externo tenga la instrucción de procesamiento:  
  
-   **Ámbito de instrucción de procesamiento** propiedad establecida en "Envelope".  
  
-   **Agregar instrucciones de procesamiento** propiedad establecida en "Agregar".  
  
 El sobre utilizará la instrucción de procesamiento especificada en el ensamblador **texto de instrucciones de procesamiento de agregar** propiedad.  
  
 Las instrucciones de procesamiento que existen en los sobres externos o internos no estarán presentes en los mensajes de salida, tal como se especificó en el mensaje de entrada.  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de ensamblador XML](../core/xml-assembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)