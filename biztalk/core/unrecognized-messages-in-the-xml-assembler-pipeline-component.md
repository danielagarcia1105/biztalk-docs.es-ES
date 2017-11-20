---
title: "Componente de canalización de mensajes desconocidos en el ensamblador XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XMLNorm.AllowUnrecognizedMessage property
- XML Assembler [pipeline component], unrecognized messages
- pipeline components, XML Assembler
ms.assetid: dd98512a-33a4-4b2e-977e-1b3a30747c6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6766554374413c3d1b6a3ce385f24d4046521c91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="ddbcf-102">Mensajes desconocidos en el componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="ddbcf-102">Unrecognized Messages in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="ddbcf-103">El componente de ensamblador XML trata los mensajes como “desconocidos” si:</span><span class="sxs-lookup"><span data-stu-id="ddbcf-103">The XML Assembler component treats a message as "unrecognized" if a message has:</span></span>  
  
-   <span data-ttu-id="ddbcf-104">No hay ninguna parte del cuerpo</span><span class="sxs-lookup"><span data-stu-id="ddbcf-104">No body part.</span></span>  
  
-   <span data-ttu-id="ddbcf-105">Hay una parte del cuerpo vacía.</span><span class="sxs-lookup"><span data-stu-id="ddbcf-105">An empty body part.</span></span>  
  
-   <span data-ttu-id="ddbcf-106">No hay datos en la parte del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="ddbcf-106">No data in the body part.</span></span>  
  
-   <span data-ttu-id="ddbcf-107">No hay ningún esquema implementado asociado.</span><span class="sxs-lookup"><span data-stu-id="ddbcf-107">No associated schema deployed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddbcf-108">A los mensajes que no sean XML siempre se les trata como desconocidos.</span><span class="sxs-lookup"><span data-stu-id="ddbcf-108">Non-XML messages are always treated as unrecognized.</span></span>  
  
 <span data-ttu-id="ddbcf-109">La manera en que el ensamblador XML controla un mensaje desconocido se controla mediante la **XMLNorm.AllowUnrecognizedMessage** propiedad de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ddbcf-109">The manner in which the XML Assembler handles an unrecognized message is controlled by the **XMLNorm.AllowUnrecognizedMessage** message context property.</span></span>  
  
 <span data-ttu-id="ddbcf-110">Cuando **XMLNorm.AllowUnrecognizedMessage** está establecido en **True**, el ensamblador XML controla los documentos XML como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="ddbcf-110">When **XMLNorm.AllowUnrecognizedMessage** is set to **True**, the XML Assembler handles XML documents as follows:</span></span>  
  
-   <span data-ttu-id="ddbcf-111">Un mensaje sin ninguna parte del cuerpo, con una parte del cuerpo vacía o con datos vacíos en la parte del cuerpo pasa sin ningún cambio a través del desensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="ddbcf-111">A message with no body part or with an empty body part or empty data in the body part passes unchanged through the assembler.</span></span>  
  
-   <span data-ttu-id="ddbcf-112">Un documento que no tiene un esquema implementado asociado pasa sin ningún cambio a través del ensamblador.</span><span class="sxs-lookup"><span data-stu-id="ddbcf-112">A document that does not have a deployed schema associated with it passes unchanged through the assembler.</span></span>  
  
-   <span data-ttu-id="ddbcf-113">El ensamblador procesa un documento que tiene un esquema implementado asociado (independientemente de si se hace referencia explícita al esquema en una propiedad del componente o si se ha encontrado durante el proceso de resolución del esquema).</span><span class="sxs-lookup"><span data-stu-id="ddbcf-113">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
 <span data-ttu-id="ddbcf-114">Si **XMLNorm.AllowUnrecognizedMessage** está establecido en **False**, el ensamblador XML controla los documentos XML como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="ddbcf-114">If **XMLNorm.AllowUnrecognizedMessage** is set to **False**, the XML Assembler handles XML documents as follows:</span></span>  
  
-   <span data-ttu-id="ddbcf-115">Un mensaje sin ninguna parte del cuerpo, con una parte del cuerpo vacía o con datos vacíos en la parte del cuerpo no se procesa.</span><span class="sxs-lookup"><span data-stu-id="ddbcf-115">A message with no body part or with an empty body part or empty data in the body part is not processed.</span></span> <span data-ttu-id="ddbcf-116">Se genera un informe de error y se suspende el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ddbcf-116">An error is reported and the message is suspended.</span></span>  
  
-   <span data-ttu-id="ddbcf-117">Un mensaje que no tenga un esquema implementado asociado no se procesa.</span><span class="sxs-lookup"><span data-stu-id="ddbcf-117">A message that does not have a deployed schema associated with it is not processed.</span></span> <span data-ttu-id="ddbcf-118">Se genera un informe de error y se suspende el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ddbcf-118">An error is reported and the message is suspended.</span></span>  
  
-   <span data-ttu-id="ddbcf-119">El ensamblador procesa un documento que tiene un esquema implementado asociado (independientemente de si se hace referencia explícita al esquema en una propiedad del componente o si se ha encontrado durante el proceso de resolución del esquema).</span><span class="sxs-lookup"><span data-stu-id="ddbcf-119">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
-   <span data-ttu-id="ddbcf-120">De forma predeterminada, el componente de ensamblador XML no permite mensajes desconocidos (es decir, **XMLNorm.AllowUnrecognizedMessages** se considera **False** si no se establece en el contexto del mensaje).</span><span class="sxs-lookup"><span data-stu-id="ddbcf-120">By default, the XML Assembler component does not allow unrecognized messages (that is, **XMLNorm.AllowUnrecognizedMessages** is considered **False** if it is not set on the message context).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddbcf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddbcf-121">See Also</span></span>  
 <span data-ttu-id="ddbcf-122">[Componente de canalización de ensamblador XML](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="ddbcf-122">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="ddbcf-123">[Cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="ddbcf-123">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="ddbcf-124">Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="ddbcf-124">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)