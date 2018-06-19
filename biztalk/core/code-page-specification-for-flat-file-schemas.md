---
title: Especificación de la página para esquemas de archivo sin formato de código | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 825e75f1-893c-4c61-b566-f893d732a907
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64d5cfbc960346e702ed0d4a39ca74bbc4b3634c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232268"
---
# <a name="code-page-specification-for-flat-file-schemas"></a><span data-ttu-id="27ecc-102">Especificación de la página de código para esquemas de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="27ecc-102">Code Page Specification for Flat File Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="27ecc-103">Información general</span><span class="sxs-lookup"><span data-stu-id="27ecc-103">Overview</span></span>
<span data-ttu-id="27ecc-104">El valor de la **página de códigos** propiedad se utiliza para crear un objeto de codificación que se utiliza durante el desensamblado y ensamblado de documentos de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="27ecc-104">The value in the **Code Page** property is used to create an encoding object that is used during the disassembly and assembly of flat file documents.</span></span> <span data-ttu-id="27ecc-105">Este objeto de codificación permite al analizador de archivos sin formato convertir la codificación nativa de un documento de archivo sin formato entrante en la codificación UTF-8 normalizado que se usa internamente en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27ecc-105">This encoding object allows the flat file parser to convert the native encoding of an inbound flat file document into the normalized UTF-8 encoding that is used internally by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="27ecc-106">El objeto de codificación también permite al serializador de archivo sin formato volver a convertir la codificación interna UTF-8 en la codificación nativa del documento de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="27ecc-106">The encoding object also allows the flat file serializer to convert the internal UTF-8 encoding back into the native encoding of the flat file document.</span></span>  
  
 <span data-ttu-id="27ecc-107">La configuración de la **página de códigos** propiedad desempeña un papel importante, pero no exclusivo, para determinar el esquema de codificación de caracteres utilizado por los documentos empresariales de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="27ecc-107">The setting of the **Code Page** property plays an important, but not exclusive, role in determining the character encoding scheme used by your flat file business documents.</span></span> <span data-ttu-id="27ecc-108">Es necesario tener en cuenta cómo el desensamblador de archivos sin formato interpreta los mensajes de archivo sin formato de entrada y cómo el ensamblador de archivos sin formato codificará los caracteres cuando los mensajes de salida se traduzcan al formato de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="27ecc-108">You must consider how inbound flat file messages are interpreted by the flat file disassembler as well as how the flat file assembler will encode characters as outbound messages are translated into flat file format.</span></span>  

## <a name="character-encoding"></a><span data-ttu-id="27ecc-109">Codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="27ecc-109">Character encoding</span></span>  
 <span data-ttu-id="27ecc-110">Hay varios factores que influyen en la determinación de cómo se trata la codificación de caracteres de un determinado mensaje de instancia, entre ellos:</span><span class="sxs-lookup"><span data-stu-id="27ecc-110">There are multiple factors that play a role in determining how character encoding for a given instance message is handled, as follows:</span></span>  
  
-   <span data-ttu-id="27ecc-111">Al desensamblar un mensaje de instancia de archivo sin formato, se utiliza el algoritmo siguiente para determinar y mantener la información de codificación:</span><span class="sxs-lookup"><span data-stu-id="27ecc-111">When disassembling a flat file instance message, the following algorithm is used to determine and preserve encoding information:</span></span>  
  
    1.  <span data-ttu-id="27ecc-112">Si el **Charset** en la parte del cuerpo del mensaje se establece, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="27ecc-112">If the **Charset** in the Message body part is set, its value is used.</span></span>  
  
    2.  <span data-ttu-id="27ecc-113">En caso contrario, si el esquema de sobre (o documento) especifica una página de código mediante la **página de códigos** se utiliza su valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="27ecc-113">Otherwise, if the envelope (or document) schema specifies a code page using the **Code Page** property, its value is used.</span></span>  
  
    3.  <span data-ttu-id="27ecc-114">O bien, si hay una marca de orden de bytes, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="27ecc-114">Otherwise, if a byte order mark is present, its value is used.</span></span>  
  
    4.  <span data-ttu-id="27ecc-115">En caso contrario, considere usar UTF-8.</span><span class="sxs-lookup"><span data-stu-id="27ecc-115">Otherwise, assume UTF-8.</span></span>  
  
-   <span data-ttu-id="27ecc-116">Al ensamblar un mensaje de instancia de archivo sin formato, se utiliza el algoritmo siguiente para determinar el juego de caracteres que se debe usar para la descodificación:</span><span class="sxs-lookup"><span data-stu-id="27ecc-116">When assembling a flat file instance message, the following algorithm is used to determine the character set to use for decoding:</span></span>  
  
-   <span data-ttu-id="27ecc-117">Si el **XMLNorm.TargetCharset** se establece la propiedad de contexto de mensaje, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="27ecc-117">If the **XMLNorm.TargetCharset** message context property is set, its value is used.</span></span>  
  
-   <span data-ttu-id="27ecc-118">De lo contrario, si la **TargetCharset** se establece la propiedad del ensamblador (tiempo de diseño), se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="27ecc-118">Otherwise, if the **TargetCharset** assembler (design-time) property is set, its value is used.</span></span>  
  
-   <span data-ttu-id="27ecc-119">En caso contrario, si el esquema de sobre (o documento) especifica una página de código mediante la **página de códigos** se utiliza su valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="27ecc-119">Otherwise, if the envelope (or document) schema specifies a code page using the **Code Page** property, its value is used.</span></span>  
  
    1.  <span data-ttu-id="27ecc-120">De lo contrario, si la **SourceCharset** se establece la propiedad de contexto de mensaje, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="27ecc-120">Otherwise, if the **SourceCharset** message context property is set, its value is used.</span></span>  
  
    2.  <span data-ttu-id="27ecc-121">En caso contrario, utilice UTF-8.</span><span class="sxs-lookup"><span data-stu-id="27ecc-121">Otherwise, use UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ecc-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="27ecc-122">See Also</span></span>  
 <span data-ttu-id="27ecc-123">**Consideraciones al crear planos esquemas de mensaje de archivo** y **(propiedad de nodo de esquemas de archivo sin formato) de la página de códigos**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="27ecc-123">**Considerations When Creating Flat File Message Schemas** and **Code Page (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>