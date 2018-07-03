---
title: Codificación de caracteres en el componente de canalización de desensamblador de archivos planos | Microsoft Docs
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
- pipeline components, Flat File Disassembler
- Flat File Disassembler [pipeline component], character encoding
ms.assetid: 0dbe24fb-c431-4edf-8aa9-4c040d6a7b32
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a7ef27ec23fb7470aff74df2915150f892e07a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988813"
---
# <a name="character-encoding-in-the-flat-file-disassembler-pipeline-component"></a><span data-ttu-id="8e1ad-102">Codificación de caracteres en el componente de canalización de desensamblador de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="8e1ad-102">Character Encoding in the Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="8e1ad-103">El componente de desensamblador de archivo sin formato utiliza el siguiente algoritmo para determinar la codificación que se utilizará para procesar un mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="8e1ad-103">The following algorithm is used by the Flat File Disassembler component to determine which encoding to use for processing an incoming message:</span></span>  
  
1. <span data-ttu-id="8e1ad-104">Si en los datos existe una marca de orden de bytes, la información de codificación vendrá determinada por ésta.</span><span class="sxs-lookup"><span data-stu-id="8e1ad-104">If a byte order mark exists in the data, encoding information is determined from it.</span></span> <span data-ttu-id="8e1ad-105">Esta información de codificación no se conserva el Desensamblador (es decir, no se guarda en el **XMLNorm.SourceCharset** propiedad).</span><span class="sxs-lookup"><span data-stu-id="8e1ad-105">This encoding information is not preserved by the disassembler (that is, it is not saved to the **XMLNorm.SourceCharset** property).</span></span>  
  
2. <span data-ttu-id="8e1ad-106">De lo contrario, si la **IBaseMessagePart.Charset** propiedad está establecida, se utiliza la codificación especificada no existe.</span><span class="sxs-lookup"><span data-stu-id="8e1ad-106">Otherwise, if the **IBaseMessagePart.Charset** property is set, the encoding specified there is used.</span></span>  
  
3. <span data-ttu-id="8e1ad-107">En caso contrario, si el encabezado o el esquema de documento contienen información de página de códigos, se utiliza ésta.</span><span class="sxs-lookup"><span data-stu-id="8e1ad-107">Otherwise, if the header or document schema contains codepage information, it is used.</span></span>  
  
4. <span data-ttu-id="8e1ad-108">En caso contrario, se utiliza la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="8e1ad-108">Otherwise, UTF-8 encoding is used.</span></span>  
  
   <span data-ttu-id="8e1ad-109">Los anteriores casos 2, 3 y 4, el Desensamblador guarda la información de codificación en el contexto del mensaje en el **XMLNorm.SourceCharset** propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e1ad-109">For the preceding cases 2, 3, and 4, the disassembler saves the encoding information on the message context in the **XMLNorm.SourceCharset** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e1ad-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e1ad-110">See Also</span></span>  
 <span data-ttu-id="8e1ad-111">[Componente de canalización de desensamblador de archivos sin formato](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="8e1ad-111">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="8e1ad-112">[Cómo configurar el componente de canalización de desensamblador de archivos sin formato](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="8e1ad-112">[How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="8e1ad-113">Pipelines\AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="8e1ad-113">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)