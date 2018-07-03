---
title: Codificación de caracteres en el componente de canalización de ensamblador de archivo sin formato | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Flat File Assembler [pipeline component], character encoding
- IBaseMessagePart.Charset property
- pipeline components, Flat File Assembler
- Codepage property
- XMLNorm.SourceCharset property
- XMLNorm.TargetCharset property
- Target Charset property
ms.assetid: 0cf3c0fd-f036-4190-83ce-9064ef4e823c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47c1b85531a2efe13b91383a4bb5a8deb35b63e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986341"
---
# <a name="character-encoding-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="71d3c-102">Codificación de caracteres en el componente de canalización de ensamblador de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="71d3c-102">Character Encoding in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="71d3c-103">El ensamblador de archivo sin formato puede crear mensajes con una codificación de caracteres especificada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="71d3c-103">The Flat File Assembler can produce messages in user-specified character encoding.</span></span> <span data-ttu-id="71d3c-104">Puede especificar la codificación de caracteres en varios niveles:</span><span class="sxs-lookup"><span data-stu-id="71d3c-104">You can specify the character encoding at several levels:</span></span>  
  
- <span data-ttu-id="71d3c-105">**Esquema.**</span><span class="sxs-lookup"><span data-stu-id="71d3c-105">**Schema.**</span></span> <span data-ttu-id="71d3c-106">Establecer el **codepage** propiedad en el esquema de archivo sin formato para el documento.</span><span class="sxs-lookup"><span data-stu-id="71d3c-106">Set the **codepage** property in the flat file schema for the document.</span></span>  
  
- <span data-ttu-id="71d3c-107">**Componente.**</span><span class="sxs-lookup"><span data-stu-id="71d3c-107">**Component.**</span></span> <span data-ttu-id="71d3c-108">Establecer el **destino Charset** propiedad del componente en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="71d3c-108">Set the **Target Charset** component property in Pipeline Designer.</span></span>  
  
- <span data-ttu-id="71d3c-109">**Mensaje.**</span><span class="sxs-lookup"><span data-stu-id="71d3c-109">**Message.**</span></span> <span data-ttu-id="71d3c-110">Establecer el **XMLNorm.TargetCharset** propiedad en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="71d3c-110">Set the **XMLNorm.TargetCharset** property on the message context.</span></span>  
  
  <span data-ttu-id="71d3c-111">El valor de la propiedad establecida en un contexto del mensaje siempre reemplaza la establecida en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="71d3c-111">The value of the property set on a message context always overrides the one set in Pipeline Designer.</span></span> <span data-ttu-id="71d3c-112">Además, el valor establecido en el Diseñador de canalizaciones siempre sobrescribe el valor establecido como un **codepage** propiedad en un esquema de documento de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="71d3c-112">Also, the value set in Pipeline Designer always overwrites the value set as a **codepage** property in a flat file document schema.</span></span>  
  
  <span data-ttu-id="71d3c-113">El ensamblador de archivo sin formato utiliza el siguiente algoritmo para determinar la codificación que se utilizará para un mensaje de salida:</span><span class="sxs-lookup"><span data-stu-id="71d3c-113">The Flat File Assembler uses the following algorithm to determine which encoding to use for an output message:</span></span>  
  
- <span data-ttu-id="71d3c-114">Si el **XMLNorm.TargetCharset** está establecida la propiedad de contexto, su valor se utiliza para la codificación.</span><span class="sxs-lookup"><span data-stu-id="71d3c-114">If the **XMLNorm.TargetCharset** context property is set, its value is used for encoding.</span></span>  
  
- <span data-ttu-id="71d3c-115">De lo contrario, si la **destino charset** se especifica la propiedad en el Diseñador de canalizaciones, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="71d3c-115">Otherwise, if the **Target charset** property in Pipeline Designer is specified, its value is used.</span></span>  
  
- <span data-ttu-id="71d3c-116">De lo contrario, si la **codepage** se especifica la propiedad en el esquema de archivo sin formato, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="71d3c-116">Otherwise, if the **codepage** property in the flat file schema is specified, its value is used.</span></span>  
  
- <span data-ttu-id="71d3c-117">De lo contrario, si la **XMLNorm.SourceCharset** propiedad se especifica, se utiliza su valor.</span><span class="sxs-lookup"><span data-stu-id="71d3c-117">Otherwise, if the **XMLNorm.SourceCharset** property is specified, its value is used.</span></span>  
  
- <span data-ttu-id="71d3c-118">O bien, se utiliza "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="71d3c-118">Otherwise, "UTF-8" is used.</span></span> <span data-ttu-id="71d3c-119">Observe que el componente de canalización de ensamblador de archivo sin formato no pone marca de orden de bytes en los mensajes salientes cuando se utiliza la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="71d3c-119">Note that the Flat File Assembler pipeline component does not put byte order mark on outgoing messages when UTF-8 encoding is used.</span></span>  
  
  <span data-ttu-id="71d3c-120">El ensamblador de archivo sin formato guarda la codificación de información en la parte del cuerpo del objeto de mensaje de BizTalk en el **IBaseMessagePart.Charset** propiedad.</span><span class="sxs-lookup"><span data-stu-id="71d3c-120">The Flat File Assembler saves encoding information on the body part of the BizTalk message object in the **IBaseMessagePart.Charset** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d3c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="71d3c-121">See Also</span></span>  
 <span data-ttu-id="71d3c-122">[Componente de canalización de ensamblador de archivo sin formato](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="71d3c-122">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="71d3c-123">[Cómo configurar el componente de canalización de ensamblador de archivo sin formato](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="71d3c-123">[How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="71d3c-124">Pipelines\AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="71d3c-124">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)