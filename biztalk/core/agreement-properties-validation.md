---
title: "Validación de propiedades de acuerdo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d565c26-37ef-4aee-aebb-3152880242a1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20c01ec281005cbeaffda6dcd2349c1153a531b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="agreement-properties-validation"></a>Validación de las propiedades del acuerdo
Las propiedades de acuerdo incluyen comprobaciones de números de control duplicados en intercambios, grupos o conjuntos de transacciones. La canalización de recepción de EDI llevará a cabo estas validaciones únicamente si están habilitadas en las propiedades del acuerdo. Estas validaciones incluyen lo siguiente:  
  
-   Comprobar si existe un número de control de intercambio duplicado (ISA13 en X12 o UNB5 en EDIFACT). Especifique un valor de tiempo (en días) para establecer el intervalo de tiempo válido para esta comprobación.  
  
-   Comprobar si existe un número de control de grupo duplicado en un intercambio (GS6 en X12 o UNG5 en EDIFACT).  
  
-   Comprobar si existe un número de control del conjunto de transacciones duplicado en un grupo funcional (ST2 en X12 o UNH1 en EDIFACT)  
  
## <a name="see-also"></a>Vea también  
 [Validación del mensaje EDI](../core/edi-message-validation.md)