---
title: Codificación de caracteres en el componente de canalización de ensamblador XML | Documentos de Microsoft
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
ms.openlocfilehash: 82709af574e3577990cf99cd430e1a5e6a7f8485
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232108"
---
# <a name="character-encoding-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="12c65-102">Codificación de caracteres en el componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="12c65-102">Character Encoding in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="12c65-103">El componente de canalización de ensamblador XML puede crear mensajes con codificación de caracteres que el usuario especifica de dos formas, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="12c65-103">The XML Assembler pipeline component can produce messages in user-specified character encoding in two ways, as shown in the following table.</span></span>  
  
|<span data-ttu-id="12c65-104">Nivel de codificación</span><span class="sxs-lookup"><span data-stu-id="12c65-104">Encoding level</span></span>|<span data-ttu-id="12c65-105">Método de codificación</span><span class="sxs-lookup"><span data-stu-id="12c65-105">Encoding method</span></span>|  
|--------------------|---------------------|  
|<span data-ttu-id="12c65-106">Componente</span><span class="sxs-lookup"><span data-stu-id="12c65-106">Component</span></span>|<span data-ttu-id="12c65-107">Establecer el **juego de caracteres de destino** propiedad del componente en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="12c65-107">Set the **Target charset** component property in Pipeline Designer.</span></span>|  
|<span data-ttu-id="12c65-108">de mensaje</span><span class="sxs-lookup"><span data-stu-id="12c65-108">Message</span></span>|<span data-ttu-id="12c65-109">Establecer el **XMLNorm.TargetCharset** propiedad en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="12c65-109">Set the **XMLNorm.TargetCharset** property on the message context.</span></span> <span data-ttu-id="12c65-110">**Nota:** mensaje de una propiedad de contexto siempre reemplaza cualquier propiedad de contexto establecida en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="12c65-110">**Note:**  A message context property always overrides any context property set in Pipeline Designer.</span></span>|  
  
 <span data-ttu-id="12c65-111">El ensamblador XML utiliza el siguiente algoritmo para determinar la codificación del mensaje de salida:</span><span class="sxs-lookup"><span data-stu-id="12c65-111">The XML Assembler uses the following algorithm to determine output message encoding:</span></span>  
  
1.  <span data-ttu-id="12c65-112">Si el **XMLNorm.TargetCharset** se establece la propiedad de contexto, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="12c65-112">If the **XMLNorm.TargetCharset** context property is set, its value is used.</span></span>  
  
2.  <span data-ttu-id="12c65-113">De lo contrario, si la **juego de caracteres de destino** propiedad se especifica en el Diseñador de canalizaciones, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="12c65-113">Otherwise, if the **Target charset** property is specified in Pipeline Designer, its value is used.</span></span>  
  
3.  <span data-ttu-id="12c65-114">De lo contrario, si la **XMLNorm.SourceCharset** propiedad se especifica, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="12c65-114">Otherwise, if the **XMLNorm.SourceCharset** property is specified, its value is used.</span></span>  
  
4.  <span data-ttu-id="12c65-115">Si no está configurada ninguna de las propiedades anteriores, se utiliza la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="12c65-115">If none of the preceding properties is set, UTF-8 encoding is used.</span></span>  
  
 <span data-ttu-id="12c65-116">El ensamblador XML guarda la información de codificación de un objeto de mensaje de BizTalk en el `IBaseMessagePart.Charset` propiedad.</span><span class="sxs-lookup"><span data-stu-id="12c65-116">The XML Assembler saves the encoding information of a BizTalk message object in the `IBaseMessagePart.Charset` property.</span></span> <span data-ttu-id="12c65-117">Al utilizar la codificación Unicode o UTF-8, el ensamblador XML siempre agrega la marca de orden de bytes (BOM) a los mensajes de salida.</span><span class="sxs-lookup"><span data-stu-id="12c65-117">When using Unicode or UTF-8 encoding, the XML Assembler always adds the byte order mark (BOM) to outgoing messages.</span></span>  
  
 <span data-ttu-id="12c65-118">Tenga en cuenta que cuando se usa el valor predeterminado XML enviar una canalización, que contiene el componente de ensamblador XML, los documentos se pueden codificar mediante el mismo conjunto de caracteres, como cuando se hayan enviado al servidor, o pueden estar codificados con UTF-8 si se crearon documentos en el servidor y **XMLNorm.TargetCharset** no se especificó.</span><span class="sxs-lookup"><span data-stu-id="12c65-118">Note that when using the default XML send pipeline, which contains the XML Assembler component, the produced documents may be encoded by using the same charset as when they were submitted into the server, or they may be encoded by using UTF-8 if documents were created within the server and **XMLNorm.TargetCharset** was not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c65-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="12c65-119">See Also</span></span>  
 <span data-ttu-id="12c65-120">[Componente de canalización de ensamblador XML](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="12c65-120">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="12c65-121">[Cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="12c65-121">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="12c65-122">Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="12c65-122">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)