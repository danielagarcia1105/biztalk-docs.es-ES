---
title: Documento de validación en el componente de canalización de desensamblador XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], document validation
- XML Disassembler [pipeline component], warnings
ms.assetid: feb25033-46d3-48ed-8e1f-0cd123e94149
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2dcea790208bf0234c67c8c941e6355fb367d82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239388"
---
# <a name="document-validation-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="271fc-102">Validación de documentos en el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="271fc-102">Document Validation in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="271fc-103">De forma predeterminada, el desensamblador XML no valida los documentos XML con respecto a un esquema.</span><span class="sxs-lookup"><span data-stu-id="271fc-103">By default, the XML Disassembler does not validate XML documents against a schema.</span></span> <span data-ttu-id="271fc-104">Sin embargo, puede configurar el desensamblador XML para validar un documento XML mediante el establecimiento del **validar la estructura del documento** propiedad.</span><span class="sxs-lookup"><span data-stu-id="271fc-104">However, you can configure the XML Disassembler to validate an XML document by setting the **Validate Document Structure** property.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="271fc-105">Si un campo para promoción se declara con un tipo de datos simples pero contiene datos complejos, la promoción de la propiedad causará resultados impredecibles.</span><span class="sxs-lookup"><span data-stu-id="271fc-105">If a field for promotion is declared with a simple data type but contains complex data, the property promotion will cause unpredictable results.</span></span> <span data-ttu-id="271fc-106">Para evitar este escenario, configure el desensamblador XML para llevar a cabo la validación de documentos estableciendo la **validar la estructura del documento** propiedad **True**.</span><span class="sxs-lookup"><span data-stu-id="271fc-106">To avoid this scenario, configure the XML Disassembler to perform document validation by setting the **Validate Document Structure** property to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="271fc-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="271fc-107">See Also</span></span>  
 <span data-ttu-id="271fc-108">[Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="271fc-108">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="271fc-109">Cómo configurar el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="271fc-109">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)