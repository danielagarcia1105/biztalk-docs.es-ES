---
title: Codificación de caracteres en el componente de canalización de ensamblador XML | Microsoft Docs
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
- pipeline components, XML Assembler
- XMLNorm.TargetCharset property
- Target Charset property
- XML Assembler [pipeline component], character encoding
ms.assetid: c031fbbf-f00f-41ba-8ac9-cec7d625cef6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5d06842eab0def7846ab31419ce2feb0aeb2cd1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000877"
---
# <a name="character-encoding-in-the-xml-assembler-pipeline-component"></a>Codificación de caracteres en el componente de canalización de ensamblador XML
El componente de canalización de ensamblador XML puede crear mensajes con codificación de caracteres que el usuario especifica de dos formas, como se muestra en la siguiente tabla.  
  
|Nivel de codificación|Método de codificación|  
|--------------------|---------------------|  
|Componente|Establecer el **destino charset** propiedad del componente en el Diseñador de canalizaciones.|  
|de mensaje|Establecer el **XMLNorm.TargetCharset** propiedad en el contexto del mensaje. **Nota:** mensajes de una propiedad de contexto siempre reemplaza cualquier propiedad de contexto establecido en el Diseñador de canalizaciones.|  
  
 El ensamblador XML utiliza el siguiente algoritmo para determinar la codificación del mensaje de salida:  
  
1. Si el **XMLNorm.TargetCharset** se establece la propiedad de contexto, se utiliza su valor.  
  
2. De lo contrario, si la **destino charset** propiedad se especifica en el Diseñador de canalizaciones, se utiliza su valor.  
  
3. De lo contrario, si la **XMLNorm.SourceCharset** propiedad se especifica, se utiliza su valor.  
  
4. Si no está configurada ninguna de las propiedades anteriores, se utiliza la codificación UTF-8.  
  
   El ensamblador XML guarda la información de codificación de un objeto de mensaje de BizTalk en el `IBaseMessagePart.Charset` propiedad. Al utilizar la codificación Unicode o UTF-8, el ensamblador XML siempre agrega la marca de orden de bytes (BOM) a los mensajes de salida.  
  
   Tenga en cuenta que cuando se usa el valor predeterminado XML enviar una canalización, que contiene el componente de ensamblador XML, los documentos se pueden codificar con el mismo juego de caracteres como cuando se hayan enviado al servidor, o pueden estar codificados con UTF-8 si se crearon documentos en el servidor y **XMLNorm.TargetCharset** no se ha especificado.  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de ensamblador XML](../core/xml-assembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines\AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)