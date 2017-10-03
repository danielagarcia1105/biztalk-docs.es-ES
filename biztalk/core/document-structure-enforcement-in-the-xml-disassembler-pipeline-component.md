---
title: "Documentar el cumplimiento de la estructura en el componente de canalización de desensamblador XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], document structure
- pipeline components, XML Disassembler
ms.assetid: ac405bf2-f92b-4b45-8256-dd188ec9510a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e14b20292b23a0f50362940e3b873fa37a3f5bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="document-structure-enforcement-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="5b9ec-102">Obligatoriedad de estructura del documento en el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="5b9ec-102">Document Structure Enforcement in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="5b9ec-103">Si se hace referencia explícita a un esquema de sobres o documento en el desensamblador XML, éste procesa únicamente los documentos con tipos de mensaje que se adaptan al esquema.</span><span class="sxs-lookup"><span data-stu-id="5b9ec-103">If a document or envelope schema is explicitly referenced in the XML Disassembler, the XML Disassembler processes only those documents with message types conforming to the schema.</span></span> <span data-ttu-id="5b9ec-104">No se procesan otros documentos, independientemente de que se haga referencia o no a un esquema implementado para ellos.</span><span class="sxs-lookup"><span data-stu-id="5b9ec-104">No other documents are processed, regardless of whether a deployed schema is referenced for them.</span></span>  
  
 <span data-ttu-id="5b9ec-105">El desensamblador XML impone el orden especificado de esquemas de sobres; sin embargo, el orden de los esquemas de documentos no viene impuesto.</span><span class="sxs-lookup"><span data-stu-id="5b9ec-105">The XML Disassembler enforces the specified order of envelope schemas; however, the order of document schemas is not enforced.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b9ec-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b9ec-106">See Also</span></span>  
 <span data-ttu-id="5b9ec-107">[Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="5b9ec-107">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="5b9ec-108">Cómo configurar el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="5b9ec-108">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)