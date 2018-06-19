---
title: Problemas conocidos de delimitadores | Documentos de Microsoft
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
ms.openlocfilehash: 18168ade94eed99efff0a062904c14b387de6bcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204692"
---
# <a name="delimiters-known-issues"></a><span data-ttu-id="a6ee6-102">Problemas conocidos de delimitadores</span><span class="sxs-lookup"><span data-stu-id="a6ee6-102">Delimiters Known Issues</span></span>
<span data-ttu-id="a6ee6-103">Esta sección contiene información útil que puede ayudar a evitar errores de delimitador.</span><span class="sxs-lookup"><span data-stu-id="a6ee6-103">This section contains useful information that may help you avoid delimiter errors.</span></span>  
  
## <a name="characters-not-recommended-to-be-used-as-delimiters"></a><span data-ttu-id="a6ee6-104">No se recomienda para usarse como delimitadores de caracteres</span><span class="sxs-lookup"><span data-stu-id="a6ee6-104">Characters not recommended to be used as delimiters</span></span>  
 <span data-ttu-id="a6ee6-105">Se recomienda que no use los siguientes caracteres como delimitadores tal y como podrían producir errores:</span><span class="sxs-lookup"><span data-stu-id="a6ee6-105">It is recommended that you do not use the following characters as delimiters as they might cause errors:</span></span>  
  
-   <span data-ttu-id="a6ee6-106">Caracteres null</span><span class="sxs-lookup"><span data-stu-id="a6ee6-106">Null characters</span></span>  
  
-   <span data-ttu-id="a6ee6-107">Espacios</span><span class="sxs-lookup"><span data-stu-id="a6ee6-107">Spaces</span></span>  
  
## <a name="extra-delimiters-in-a-header-or-body-field-cause-multiple-errors"></a><span data-ttu-id="a6ee6-108">Delimitadores adicionales en un encabezado o un campo de cuerpo provocan varios errores</span><span class="sxs-lookup"><span data-stu-id="a6ee6-108">Extra delimiters in a header or body field cause multiple errors</span></span>  
 <span data-ttu-id="a6ee6-109">Si tiene un delimitador adicional en un campo de un V2 HL7. X mensaje, el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) analizador podría generar dos mensajes de error, uno relacionadas con la validación de XML y el otro relacionadas con la validación estructural.</span><span class="sxs-lookup"><span data-stu-id="a6ee6-109">When you have an extra delimiter in a field in an HL7 V2.X message, the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) parser might generate two error messages, one related to XML validation and the other related to structural validation.</span></span>  
  
## <a name="trailing-delimiters-permitted-in-hl7-batch-segments"></a><span data-ttu-id="a6ee6-110">Los delimitadores finales permiten en segmentos de lote de HL7</span><span class="sxs-lookup"><span data-stu-id="a6ee6-110">Trailing delimiters permitted in HL7 batch segments</span></span>  
 <span data-ttu-id="a6ee6-111">HL7 lote segmentos definidos como FHS, BHS, BTS y FT puede tener los delimitadores finales y no está restringidos por la marca de delimitadores finales, porque [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no valida los delimitadores finales para procesar por lotes segmentos.</span><span class="sxs-lookup"><span data-stu-id="a6ee6-111">HL7 defined batch segments such as FHS, BHS, BTS, and FTS can have trailing delimiters and are not constrained by the trailing delimiter flag, because [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not validate trailing delimiters for batching segments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ee6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6ee6-112">See Also</span></span>  
 [<span data-ttu-id="a6ee6-113">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="a6ee6-113">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)