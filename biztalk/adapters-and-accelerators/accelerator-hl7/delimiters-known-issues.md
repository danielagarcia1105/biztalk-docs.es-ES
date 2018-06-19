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
# <a name="delimiters-known-issues"></a>Problemas conocidos de delimitadores
Esta sección contiene información útil que puede ayudar a evitar errores de delimitador.  
  
## <a name="characters-not-recommended-to-be-used-as-delimiters"></a>No se recomienda para usarse como delimitadores de caracteres  
 Se recomienda que no use los siguientes caracteres como delimitadores tal y como podrían producir errores:  
  
-   Caracteres null  
  
-   Espacios  
  
## <a name="extra-delimiters-in-a-header-or-body-field-cause-multiple-errors"></a>Delimitadores adicionales en un encabezado o un campo de cuerpo provocan varios errores  
 Si tiene un delimitador adicional en un campo de un V2 HL7. X mensaje, el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) analizador podría generar dos mensajes de error, uno relacionadas con la validación de XML y el otro relacionadas con la validación estructural.  
  
## <a name="trailing-delimiters-permitted-in-hl7-batch-segments"></a>Los delimitadores finales permiten en segmentos de lote de HL7  
 HL7 lote segmentos definidos como FHS, BHS, BTS y FT puede tener los delimitadores finales y no está restringidos por la marca de delimitadores finales, porque [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no valida los delimitadores finales para procesar por lotes segmentos.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)