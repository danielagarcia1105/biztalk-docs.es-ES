---
title: Utilización de sobres en el ensamblador de XML y los componentes de canalización de desensamblador | Documentos de Microsoft
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
ms.openlocfilehash: a0ae57a65bad84f3d46ceb27e9b5415dc3d1bc31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240396"
---
# <a name="envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components"></a><span data-ttu-id="3466e-102">Utilización de sobres en el ensamblador de XML y los componentes de canalización de desensamblador</span><span class="sxs-lookup"><span data-stu-id="3466e-102">Envelope Use in the XML Assembler and Disassembler Pipeline Components</span></span>
<span data-ttu-id="3466e-103">Un mensaje XML puede incluir varios mensajes o ninguno.</span><span class="sxs-lookup"><span data-stu-id="3466e-103">An XML message can include zero or more envelopes.</span></span> <span data-ttu-id="3466e-104">En el ejemplo siguiente se muestra un sobre (en negrita) que rodea a un documento XML.</span><span class="sxs-lookup"><span data-stu-id="3466e-104">The following example shows an envelope (in bold) wrapping an XML document.</span></span>  
  
```  
<ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">  
   <message>Hello</message>  
</ns1:document>  
  
```  
  
 <span data-ttu-id="3466e-105">Los sobres tienen dos finalidades:</span><span class="sxs-lookup"><span data-stu-id="3466e-105">Envelopes serve two purposes:</span></span>  
  
-   <span data-ttu-id="3466e-106">Pueden incluir valores de campo para utilizarlos para la promoción y degradación de propiedades.</span><span class="sxs-lookup"><span data-stu-id="3466e-106">They can include field values to use for property promotion and demotion.</span></span>  
  
     <span data-ttu-id="3466e-107">El componente Desensamblador XML promociona propiedades y el componente Ensamblador XML las degrada.</span><span class="sxs-lookup"><span data-stu-id="3466e-107">The XML Disassembler component promotes properties, and the XML Assembler component demotes properties.</span></span> <span data-ttu-id="3466e-108">La promoción y degradación de propiedades también se pueden dar en los documentos XML.</span><span class="sxs-lookup"><span data-stu-id="3466e-108">Property promotion and demotion can also occur in XML documents.</span></span>  
  
-   <span data-ttu-id="3466e-109">Pueden combinar varios documentos XML en un único intercambio.</span><span class="sxs-lookup"><span data-stu-id="3466e-109">They can combine several XML documents into a single interchange.</span></span>  
  
     <span data-ttu-id="3466e-110">Un documento XML bien formado solo puede tener un elemento raíz, por lo que un sobre permite combinar varios documentos XML para compartir el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="3466e-110">Because a well-formed XML document can have only one root element, an envelope enables you to combine multiple XML documents to share one root element.</span></span>  
  
 <span data-ttu-id="3466e-111">Para imponer la forma canónica, puede especificar el orden sobre mediante la **Editor de propiedades de colección de esquema** cuadro de diálogo que se tiene acceso haciendo clic en el botón de puntos suspensivos para la **esquemas de sobres** propiedad de tiempo de diseño en el ensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="3466e-111">You can enforce the canonical form by specifying the envelope order by using the **Schema Collection Property Editor** dialog which is accessed by clicking the ellipses for the **Envelope schemas** design-time property in the XML Assembler.</span></span> <span data-ttu-id="3466e-112">También puede usar el **XMLNORM. EnvelopeSpecNames** propiedad de contexto del mensaje antes de ejecutar el ensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="3466e-112">You can also use the **XMLNORM.EnvelopeSpecNames** message context property before the XML Assembler is run.</span></span> <span data-ttu-id="3466e-113">El ensamblador XML crea un documento con doble cifrado en forma canónica.</span><span class="sxs-lookup"><span data-stu-id="3466e-113">The XML Assembler produces an enveloped document in canonical form.</span></span>  
  
## <a name="nesting-envelopes"></a><span data-ttu-id="3466e-114">Anidar sobres.</span><span class="sxs-lookup"><span data-stu-id="3466e-114">Nesting envelopes</span></span>  
 <span data-ttu-id="3466e-115">Puede anidar sobres para formar estructuras complejas de documentos donde varios documentos XML con doble cifrado se pueden combinar en un intercambio mayor.</span><span class="sxs-lookup"><span data-stu-id="3466e-115">You can nest envelopes to form complex document structures where several enveloped XML documents can be combined into a larger interchange.</span></span> <span data-ttu-id="3466e-116">En el ejemplo siguiente se muestra un intercambio envuelto por dos sobres.</span><span class="sxs-lookup"><span data-stu-id="3466e-116">The following example shows an interchange wrapped by two envelopes.</span></span>  
  
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
  
 <span data-ttu-id="3466e-117">El ejemplo anterior muestra una forma flexible, lo que significa que un documento puede estar en el mismo nivel de jerarquía que un sobre.</span><span class="sxs-lookup"><span data-stu-id="3466e-117">The preceding example illustrates a flexible form, which means that a document can be on the same hierarchy level as an envelope.</span></span> <span data-ttu-id="3466e-118">Después de desensamblar el documento con doble cifrado, se crean cuatro documentos separados (document1, document2, etc.).</span><span class="sxs-lookup"><span data-stu-id="3466e-118">After disassembling the enveloped document, four separate documents are created (document1, document2, and so on).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3466e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3466e-119">See Also</span></span>  
 [<span data-ttu-id="3466e-120">Componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="3466e-120">Pipeline Components</span></span>](../core/pipeline-components.md)