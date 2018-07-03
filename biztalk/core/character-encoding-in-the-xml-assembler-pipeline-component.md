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
# <a name="character-encoding-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="628ec-102">Codificación de caracteres en el componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="628ec-102">Character Encoding in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="628ec-103">El componente de canalización de ensamblador XML puede crear mensajes con codificación de caracteres que el usuario especifica de dos formas, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="628ec-103">The XML Assembler pipeline component can produce messages in user-specified character encoding in two ways, as shown in the following table.</span></span>  
  
|<span data-ttu-id="628ec-104">Nivel de codificación</span><span class="sxs-lookup"><span data-stu-id="628ec-104">Encoding level</span></span>|<span data-ttu-id="628ec-105">Método de codificación</span><span class="sxs-lookup"><span data-stu-id="628ec-105">Encoding method</span></span>|  
|--------------------|---------------------|  
|<span data-ttu-id="628ec-106">Componente</span><span class="sxs-lookup"><span data-stu-id="628ec-106">Component</span></span>|<span data-ttu-id="628ec-107">Establecer el **destino charset** propiedad del componente en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="628ec-107">Set the **Target charset** component property in Pipeline Designer.</span></span>|  
|<span data-ttu-id="628ec-108">de mensaje</span><span class="sxs-lookup"><span data-stu-id="628ec-108">Message</span></span>|<span data-ttu-id="628ec-109">Establecer el **XMLNorm.TargetCharset** propiedad en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="628ec-109">Set the **XMLNorm.TargetCharset** property on the message context.</span></span> <span data-ttu-id="628ec-110">**Nota:** mensajes de una propiedad de contexto siempre reemplaza cualquier propiedad de contexto establecido en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="628ec-110">**Note:**  A message context property always overrides any context property set in Pipeline Designer.</span></span>|  
  
 <span data-ttu-id="628ec-111">El ensamblador XML utiliza el siguiente algoritmo para determinar la codificación del mensaje de salida:</span><span class="sxs-lookup"><span data-stu-id="628ec-111">The XML Assembler uses the following algorithm to determine output message encoding:</span></span>  
  
1. <span data-ttu-id="628ec-112">Si el **XMLNorm.TargetCharset** se establece la propiedad de contexto, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="628ec-112">If the **XMLNorm.TargetCharset** context property is set, its value is used.</span></span>  
  
2. <span data-ttu-id="628ec-113">De lo contrario, si la **destino charset** propiedad se especifica en el Diseñador de canalizaciones, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="628ec-113">Otherwise, if the **Target charset** property is specified in Pipeline Designer, its value is used.</span></span>  
  
3. <span data-ttu-id="628ec-114">De lo contrario, si la **XMLNorm.SourceCharset** propiedad se especifica, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="628ec-114">Otherwise, if the **XMLNorm.SourceCharset** property is specified, its value is used.</span></span>  
  
4. <span data-ttu-id="628ec-115">Si no está configurada ninguna de las propiedades anteriores, se utiliza la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="628ec-115">If none of the preceding properties is set, UTF-8 encoding is used.</span></span>  
  
   <span data-ttu-id="628ec-116">El ensamblador XML guarda la información de codificación de un objeto de mensaje de BizTalk en el `IBaseMessagePart.Charset` propiedad.</span><span class="sxs-lookup"><span data-stu-id="628ec-116">The XML Assembler saves the encoding information of a BizTalk message object in the `IBaseMessagePart.Charset` property.</span></span> <span data-ttu-id="628ec-117">Al utilizar la codificación Unicode o UTF-8, el ensamblador XML siempre agrega la marca de orden de bytes (BOM) a los mensajes de salida.</span><span class="sxs-lookup"><span data-stu-id="628ec-117">When using Unicode or UTF-8 encoding, the XML Assembler always adds the byte order mark (BOM) to outgoing messages.</span></span>  
  
   <span data-ttu-id="628ec-118">Tenga en cuenta que cuando se usa el valor predeterminado XML enviar una canalización, que contiene el componente de ensamblador XML, los documentos se pueden codificar con el mismo juego de caracteres como cuando se hayan enviado al servidor, o pueden estar codificados con UTF-8 si se crearon documentos en el servidor y **XMLNorm.TargetCharset** no se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="628ec-118">Note that when using the default XML send pipeline, which contains the XML Assembler component, the produced documents may be encoded by using the same charset as when they were submitted into the server, or they may be encoded by using UTF-8 if documents were created within the server and **XMLNorm.TargetCharset** was not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="628ec-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="628ec-119">See Also</span></span>  
 <span data-ttu-id="628ec-120">[Componente de canalización de ensamblador XML](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="628ec-120">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="628ec-121">[Cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="628ec-121">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="628ec-122">Pipelines\AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="628ec-122">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)