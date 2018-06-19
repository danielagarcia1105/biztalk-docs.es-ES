---
title: Elementos Set de información XML en el componente de canalización de desensamblador XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], information set
- XML Disassembler [pipeline component], processing instructions
- pipeline components, XML Disassembler
ms.assetid: cc82344c-6c4b-4154-a662-0b7ae5caad30
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90b3140cbe23637160aafabdccb37104efd1d318
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289300"
---
# <a name="xml-information-set-elements-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="a1c22-102">Elementos Set de información XML en el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="a1c22-102">XML Information Set Elements in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="a1c22-103">El desensamblador XML controla los elementos Set de información XML como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="a1c22-103">The XML Disassembler handles XML information set elements as follows.</span></span>  
  
|<span data-ttu-id="a1c22-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1c22-104">Element</span></span>|<span data-ttu-id="a1c22-105">Description</span><span class="sxs-lookup"><span data-stu-id="a1c22-105">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1c22-106">comment</span><span class="sxs-lookup"><span data-stu-id="a1c22-106">comment</span></span>|<span data-ttu-id="a1c22-107">Se conservan los comentarios en el documento, sin embargo, no sucede igual con los comentarios de los sobres XML.</span><span class="sxs-lookup"><span data-stu-id="a1c22-107">Comments are preserved in the document; however, any comments in XML envelopes are not preserved.</span></span>|  
|<span data-ttu-id="a1c22-108">CDATA</span><span class="sxs-lookup"><span data-stu-id="a1c22-108">CDATA</span></span>|<span data-ttu-id="a1c22-109">CDATA se conserva en el documento.</span><span class="sxs-lookup"><span data-stu-id="a1c22-109">CDATA is preserved in the document.</span></span> <span data-ttu-id="a1c22-110">Los elementos CDATA que aparecen fuera de un documento (por ejemplo, en un sobre) no se conservan.</span><span class="sxs-lookup"><span data-stu-id="a1c22-110">CDATA elements appearing outside of a document (for example, in an envelope) are not preserved.</span></span>|  
|<span data-ttu-id="a1c22-111">instrucciones de procesamiento</span><span class="sxs-lookup"><span data-stu-id="a1c22-111">processing instructions</span></span>|<span data-ttu-id="a1c22-112">El desensamblador XML conserva las instrucciones de procesamiento que aparecen dentro o antes de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="a1c22-112">The XML Disassembler preserves processing instructions appearing in or before an XML document.</span></span> <span data-ttu-id="a1c22-113">Las instrucciones de procesamiento que aparecen después de un documento XML o antes o después de un sobre no se conservan.</span><span class="sxs-lookup"><span data-stu-id="a1c22-113">Processing instructions appearing after an XML document or before or after an envelope are not preserved.</span></span>|  
|<span data-ttu-id="a1c22-114">declaración XML</span><span class="sxs-lookup"><span data-stu-id="a1c22-114">XML declaration</span></span>|<span data-ttu-id="a1c22-115">Se quita el elemento de declaración XML de cualquier mensaje entrante XML.</span><span class="sxs-lookup"><span data-stu-id="a1c22-115">The XML declaration element of any incoming XML message is removed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1c22-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1c22-116">See Also</span></span>  
 <span data-ttu-id="a1c22-117">[Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="a1c22-117">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="a1c22-118">Cómo configurar el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="a1c22-118">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)