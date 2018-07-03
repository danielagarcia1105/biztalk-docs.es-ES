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
# <a name="delimiters-known-issues"></a>Problemas conocidos de delimitadores
Esta sección contiene información útil que puede ayudar a evitar errores de delimitador.  
  
## <a name="characters-not-recommended-to-be-used-as-delimiters"></a>No se recomienda que se usarán como delimitadores de caracteres  
 Se recomienda que no use los siguientes caracteres como delimitadores ya que podrían causar errores:  
  
-   Caracteres null  
  
-   Espacios  
  
## <a name="extra-delimiters-in-a-header-or-body-field-cause-multiple-errors"></a>Delimitadores adicionales en un encabezado o un campo de cuerpo provocan varios errores  
 Cuando haya un delimitador extra en un campo en un V2 HL7. X mensaje, el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) analizador puede generar dos mensajes de error, uno relacionadas con la validación de XML y el otro relacionadas con la validación estructural.  
  
## <a name="trailing-delimiters-permitted-in-hl7-batch-segments"></a>Los delimitadores finales permiten en segmentos de lote de HL7  
 HL7 batch segmentos definidos como FHS, BHS, BTS y FTS puede tener delimitadores finales y no están limitados por la marca de delimitador al final, ya que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no valida los delimitadores finales para segmentos de procesamiento por lotes.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)