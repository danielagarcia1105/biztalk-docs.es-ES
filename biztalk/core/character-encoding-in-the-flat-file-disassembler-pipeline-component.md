---
title: "Codificación de caracteres en el componente de canalización de desensamblador de archivos sin formato | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, Flat File Disassembler
- Flat File Disassembler [pipeline component], character encoding
ms.assetid: 0dbe24fb-c431-4edf-8aa9-4c040d6a7b32
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 839a3377f27417757e394c946fe96acc83752355
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="character-encoding-in-the-flat-file-disassembler-pipeline-component"></a><span data-ttu-id="d8440-102">Codificación de caracteres en el componente de canalización de desensamblador de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="d8440-102">Character Encoding in the Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="d8440-103">El componente de desensamblador de archivo sin formato utiliza el siguiente algoritmo para determinar la codificación que se utilizará para procesar un mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="d8440-103">The following algorithm is used by the Flat File Disassembler component to determine which encoding to use for processing an incoming message:</span></span>  
  
1.  <span data-ttu-id="d8440-104">Si en los datos existe una marca de orden de bytes, la información de codificación vendrá determinada por ésta.</span><span class="sxs-lookup"><span data-stu-id="d8440-104">If a byte order mark exists in the data, encoding information is determined from it.</span></span> <span data-ttu-id="d8440-105">Esta información de codificación no se conserva el Desensamblador (es decir, no se guarda en el **XMLNorm.SourceCharset** propiedad).</span><span class="sxs-lookup"><span data-stu-id="d8440-105">This encoding information is not preserved by the disassembler (that is, it is not saved to the **XMLNorm.SourceCharset** property).</span></span>  
  
2.  <span data-ttu-id="d8440-106">De lo contrario, si la **IBaseMessagePart.Charset** propiedad está establecida, se utiliza la codificación especificada no existe.</span><span class="sxs-lookup"><span data-stu-id="d8440-106">Otherwise, if the **IBaseMessagePart.Charset** property is set, the encoding specified there is used.</span></span>  
  
3.  <span data-ttu-id="d8440-107">En caso contrario, si el encabezado o el esquema de documento contienen información de página de códigos, se utiliza ésta.</span><span class="sxs-lookup"><span data-stu-id="d8440-107">Otherwise, if the header or document schema contains codepage information, it is used.</span></span>  
  
4.  <span data-ttu-id="d8440-108">En caso contrario, se utiliza la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="d8440-108">Otherwise, UTF-8 encoding is used.</span></span>  
  
 <span data-ttu-id="d8440-109">Para los anteriores casos 2, 3 y 4, el Desensamblador guarda la información de codificación en el contexto del mensaje en el **XMLNorm.SourceCharset** propiedad.</span><span class="sxs-lookup"><span data-stu-id="d8440-109">For the preceding cases 2, 3, and 4, the disassembler saves the encoding information on the message context in the **XMLNorm.SourceCharset** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8440-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8440-110">See Also</span></span>  
 <span data-ttu-id="d8440-111">[Componente de canalización de desensamblador de archivos sin formato](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="d8440-111">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="d8440-112">[Cómo configurar el componente de canalización de desensamblador de archivos sin formato](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="d8440-112">[How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="d8440-113">Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="d8440-113">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)