---
title: Problemas conocidos de delimitadores | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, delimiters
- delimiters
ms.assetid: 4eaacb3c-9d8d-43da-91dd-8bb25dec70e1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6de686d136d0158315dfd00eba9690b8ffcbdccc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985653"
---
# <a name="delimiters-known-issues"></a><span data-ttu-id="1a19c-102">Problemas conocidos de delimitadores</span><span class="sxs-lookup"><span data-stu-id="1a19c-102">Delimiters Known Issues</span></span>
<span data-ttu-id="1a19c-103">Esta sección contiene información útil que puede ayudar a evitar errores de delimitador.</span><span class="sxs-lookup"><span data-stu-id="1a19c-103">This section contains useful information that may help you avoid delimiter errors.</span></span>  
  
## <a name="characters-not-recommended-to-be-used-as-delimiters"></a><span data-ttu-id="1a19c-104">No se recomienda que se usarán como delimitadores de caracteres</span><span class="sxs-lookup"><span data-stu-id="1a19c-104">Characters not recommended to be used as delimiters</span></span>  
 <span data-ttu-id="1a19c-105">Se recomienda que no use los siguientes caracteres como delimitadores ya que podrían causar errores:</span><span class="sxs-lookup"><span data-stu-id="1a19c-105">It is recommended that you do not use the following characters as delimiters as they might cause errors:</span></span>  
  
-   <span data-ttu-id="1a19c-106">Caracteres null</span><span class="sxs-lookup"><span data-stu-id="1a19c-106">Null characters</span></span>  
  
-   <span data-ttu-id="1a19c-107">Espacios</span><span class="sxs-lookup"><span data-stu-id="1a19c-107">Spaces</span></span>  
  
## <a name="extra-delimiters-in-a-header-or-body-field-cause-multiple-errors"></a><span data-ttu-id="1a19c-108">Delimitadores adicionales en un encabezado o un campo de cuerpo provocan varios errores</span><span class="sxs-lookup"><span data-stu-id="1a19c-108">Extra delimiters in a header or body field cause multiple errors</span></span>  
 <span data-ttu-id="1a19c-109">Cuando haya un delimitador extra en un campo en un V2 HL7. X mensaje, el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) analizador puede generar dos mensajes de error, uno relacionadas con la validación de XML y el otro relacionadas con la validación estructural.</span><span class="sxs-lookup"><span data-stu-id="1a19c-109">When you have an extra delimiter in a field in an HL7 V2.X message, the Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) parser might generate two error messages, one related to XML validation and the other related to structural validation.</span></span>  
  
## <a name="trailing-delimiters-permitted-in-hl7-batch-segments"></a><span data-ttu-id="1a19c-110">Los delimitadores finales permiten en segmentos de lote de HL7</span><span class="sxs-lookup"><span data-stu-id="1a19c-110">Trailing delimiters permitted in HL7 batch segments</span></span>  
 <span data-ttu-id="1a19c-111">HL7 batch segmentos definidos como FHS, BHS, BTS y FTS puede tener delimitadores finales y no están limitados por la marca de delimitador al final, ya que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no valida los delimitadores finales para segmentos de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="1a19c-111">HL7 defined batch segments such as FHS, BHS, BTS, and FTS can have trailing delimiters and are not constrained by the trailing delimiter flag, because [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not validate trailing delimiters for batching segments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a19c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a19c-112">See Also</span></span>  
 [<span data-ttu-id="1a19c-113">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="1a19c-113">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)