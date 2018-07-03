---
title: Codificación de caracteres en el componente de canalización de desensamblador XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], character encoding
- XMLNorm.SourceCharset property
ms.assetid: 37962bdc-cbcb-4559-9ae8-6c4be49b4822
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fee26bdab8566010981e72585358b060009785f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977581"
---
# <a name="character-encoding-in-xml-disassembler-pipeline-component"></a><span data-ttu-id="b3d31-102">Codificación de caracteres en el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="b3d31-102">Character Encoding in XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="b3d31-103">El desensamblador XML utiliza el siguiente algoritmo para determinar la codificación que se utilizará para procesar los mensajes entrantes:</span><span class="sxs-lookup"><span data-stu-id="b3d31-103">The XML Disassembler uses the following algorithm to determine which encoding to use for processing incoming messages:</span></span>  
  
1. <span data-ttu-id="b3d31-104">Si en los datos existe una marca de orden de bytes, la información de codificación vendrá determinada por ésta.</span><span class="sxs-lookup"><span data-stu-id="b3d31-104">If a byte order mark exists in the data, encoding information is determined from it.</span></span>  
  
2. <span data-ttu-id="b3d31-105">De lo contrario, si la **IBaseMessagePart.Charset** propiedad está establecida, se utiliza la codificación especificada no existe.</span><span class="sxs-lookup"><span data-stu-id="b3d31-105">Otherwise, if the **IBaseMessagePart.Charset** property is set, the encoding specified there is used.</span></span>  
  
3. <span data-ttu-id="b3d31-106">En caso contrario, si la declaración XML está presente en el documento XML, se utiliza la codificación que se especifica en él, siempre que la declaración XML sea ANSI.</span><span class="sxs-lookup"><span data-stu-id="b3d31-106">Otherwise if the XML declaration is present in the XML document, the encoding specified there is used, provided the XML declaration is ANSI.</span></span>  
  
4. <span data-ttu-id="b3d31-107">En caso contrario, se utiliza la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b3d31-107">Otherwise, UTF-8 encoding is used.</span></span>  
  
   <span data-ttu-id="b3d31-108">Los anteriores casos 2, 3 y 4, después de que el desensamblador XML determine la codificación, lo guarda en el contexto del mensaje en **XMLNorm.SourceCharset** propiedad.</span><span class="sxs-lookup"><span data-stu-id="b3d31-108">For the preceding cases 2, 3, and 4, after the XML Disassembler determines the encoding, it saves it on the message context in **XMLNorm.SourceCharset** property.</span></span> <span data-ttu-id="b3d31-109">Los mensajes que produce el componente de canalización de desensamblador XML siempre utilizan la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b3d31-109">Messages produced by the XML Disassembler pipeline component always use UTF-8 encoding.</span></span> <span data-ttu-id="b3d31-110">En el caso 1, no se conserva la codificación que determinada la marca de orden de bytes.</span><span class="sxs-lookup"><span data-stu-id="b3d31-110">For case 1, encoding determined from the byte order mark is not preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3d31-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3d31-111">See Also</span></span>  
 <span data-ttu-id="b3d31-112">[Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="b3d31-112">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="b3d31-113">Cómo configurar el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="b3d31-113">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)