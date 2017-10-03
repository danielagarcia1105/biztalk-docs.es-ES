---
title: "Validación de mensajes EDI salientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 491303c0-b585-409e-a289-a2f6f9f82469
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 946e90eb58c9b81e0cd7fa9bf2c02cc49af021ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="validation-of-outgoing-edi-messages"></a>Validación de mensajes EDI salientes
Cuando la canalización de envío EDI procesa un mensaje que se va a enviar, se llevan a cabo una serie de validaciones en los datos del sobre y del mensaje. Siempre se llevan a cabo algunos de estos procesos. Otros sólo se realizan si usted los habilita. Entre estas validaciones, se incluyen las siguientes:  
  
-   Validación de esquema de los elementos de datos de conjuntos de transacciones con respecto al esquema de mensaje. Esta validación siempre se lleva a cabo.  
  
-   Validación de campos cruzados en los elementos de datos del conjunto de transacciones (sólo mensajes con codificación X12). Esta validación se realiza si se habilita en el esquema de mensaje.  
  
-   Validación EDI realizada en elementos de datos de conjuntos de transacciones. Esto se lleva a cabo si se habilita en las propiedades de acuerdo.  
  
-   Validación extendida realizada en elementos de datos de conjuntos de transacciones. Esto se lleva a cabo si se habilita en las propiedades de acuerdo.  
  
-   Validación de los conjuntos de transacciones en un único grupo basado en el conjunto de transacciones; asignación de grupo, según los estándares X12. Esto se realiza solo cuando la **opción de procesamiento por lotes de entrada** propiedad está establecida en **conservar intercambio: suspender intercambio en caso de Error** o **conservar intercambio: Suspender transacción Establece en caso de Error**.  
  
## <a name="see-also"></a>Vea también  
 [Validación estructural de EDI](../core/edi-structural-validation.md)   
 [Validación de propiedades de acuerdo](../core/agreement-properties-validation.md)   
 [Validación de tipo (elemento de datos) de EDI](../core/edi-type-data-element-validation.md)   
 [Validación extendida (BTS-XSD)](../core/extended-bts-xsd-validation.md)   
 [Validación de esquemas](../core/schema-validation2.md)   
 [Campo de segmento validación cruzada](../core/cross-field-segment-validation.md)