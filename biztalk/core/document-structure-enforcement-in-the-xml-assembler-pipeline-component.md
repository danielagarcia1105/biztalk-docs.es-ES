---
title: "Documentar el cumplimiento de la estructura en el componente de canalización de ensamblador XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add XML declaration property
- pipeline components, XML Assembler
ms.assetid: c121ec4b-c02b-4626-a5be-2937500dbefa
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e46dbc613439b24403c66c345b9023151b409213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="document-structure-enforcement-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="603f9-102">Obligatoriedad de estructura del documento en el componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="603f9-102">Document Structure Enforcement in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="603f9-103">Si se hace referencia explícita a los esquemas de sobres o de documentos en el ensamblador XML, éste garantiza que únicamente se procesen los documentos con el tipo de mensaje correspondiente a los esquemas a los que se hace referencia. </span><span class="sxs-lookup"><span data-stu-id="603f9-103">If document or envelope schemas are explicitly referenced in the XML Assembler, the XML Assembler ensures that only documents with the message type corresponding to referenced schemas are processed.</span></span> <span data-ttu-id="603f9-104">El resto de documentos no se procesa, aunque puede implementarse un esquema para ellos.</span><span class="sxs-lookup"><span data-stu-id="603f9-104">All the other documents are not processed even though a schema may be deployed for them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="603f9-105">El esquema de sobre se toma solo del primer mensaje.</span><span class="sxs-lookup"><span data-stu-id="603f9-105">The envelope schema is taken from the first message only.</span></span> <span data-ttu-id="603f9-106">Las propiedades del sobre siempre se toman del primer mensaje.</span><span class="sxs-lookup"><span data-stu-id="603f9-106">The properties for the envelope are always taken from the first message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="603f9-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="603f9-107">See Also</span></span>  
 <span data-ttu-id="603f9-108">[Componente de canalización de ensamblador XML](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="603f9-108">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="603f9-109">[Cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="603f9-109">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="603f9-110">Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="603f9-110">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)