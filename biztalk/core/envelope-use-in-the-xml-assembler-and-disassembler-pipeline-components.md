---
title: Usar sobres en el ensamblador XML y los componentes de canalización de desensamblador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.EnvelopeSpecNames property
- XML Disassembler [pipeline component], envelopes
- envelopes, nesting
- envelopes, XML Disassembler [pipeline component]
- envelopes, XML Assembler [pipeline component]
- XML Assembler [pipeline component], envelopes
- Envelope Specification Names property
ms.assetid: ccffd2f7-c7b1-4103-a914-ae9b4b19bee3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a435b0f87eb955bc3534c2892894a3a13afdc13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966461"
---
# <a name="envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components"></a>Usar sobres en el ensamblador XML y los componentes de canalización de desensamblador
Un mensaje XML puede incluir varios mensajes o ninguno. En el ejemplo siguiente se muestra un sobre (en negrita) que rodea a un documento XML.  
  
```  
<ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">  
   <message>Hello</message>  
</ns1:document>  
  
```  
  
 Los sobres tienen dos finalidades:  
  
- Pueden incluir valores de campo para utilizarlos para la promoción y degradación de propiedades.  
  
   El componente Desensamblador XML promociona propiedades y el componente Ensamblador XML las degrada. La promoción y degradación de propiedades también se pueden dar en los documentos XML.  
  
- Pueden combinar varios documentos XML en un único intercambio.  
  
   Un documento XML bien formado solo puede tener un elemento raíz, por lo que un sobre permite combinar varios documentos XML para compartir el elemento raíz.  
  
  Puede forzar la forma canónica si especifica el orden sobre mediante el uso de la **Editor de propiedades de colección de esquema** cuadro de diálogo que se tiene acceso haciendo clic en el botón de puntos suspensivos para la **esquemas de sobres** propiedad de tiempo de diseño en el ensamblador XML. También puede usar el **XMLNORM. EnvelopeSpecNames** propiedad de contexto del mensaje antes de ejecutar el ensamblador XML. El ensamblador XML crea un documento con doble cifrado en forma canónica.  
  
## <a name="nesting-envelopes"></a>Anidar sobres.  
 Puede anidar sobres para formar estructuras complejas de documentos donde varios documentos XML con doble cifrado se pueden combinar en un intercambio mayor. En el ejemplo siguiente se muestra un intercambio envuelto por dos sobres.  
  
```  
<envelope1>  
   <document1/>  
   <envelope2>  
      <document2/>  
      <document3/>  
   </envelope2>  
   <document4/>  
</envelope1>  
```  
  
 El ejemplo anterior muestra una forma flexible, lo que significa que un documento puede estar en el mismo nivel de jerarquía que un sobre. Después de desensamblar el documento con doble cifrado, se crean cuatro documentos separados (document1, document2, etc.).  
  
## <a name="see-also"></a>Vea también  
 [Componentes de canalización](../core/pipeline-components.md)