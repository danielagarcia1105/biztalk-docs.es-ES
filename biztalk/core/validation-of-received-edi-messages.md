---
title: "Validación de mensajes EDI recibidos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c56a3c0-042e-4611-8131-d51098064f0f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcc48b343332ea6b402841ec5ed1f5c9af49b2dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="validation-of-received-edi-messages"></a>Validación de mensajes EDI recibidos
Cuando la canalización de recepción EDI procesa un mensaje entrante, se llevan a cabo una serie de validaciones en los datos del sobre y del mensaje. Siempre se llevan a cabo algunos de estos procesos. Otros sólo se realizan si usted los habilita. Entre estas validaciones, se incluyen las siguientes:  
  
-   **Las validaciones que siempre se realizan son**:  
  
    -   Validación de la estructura del sobre de intercambio.  
  
    -   Validación del sobre con respecto al acuerdo entre socios comerciales (o acuerdo de reserva si no se ha definido ningún acuerdo).  
  
    -   Validación de esquema del sobre con respecto al esquema de control.  
  
    -   Validación de esquema de los elementos de datos de conjuntos de transacciones con respecto al esquema de mensaje.  
  
    -   Validación de los tipos de conjuntos de transacciones en un único grupo en función de la asignación conjunto de transacciones-grupo proporcionada por los estándares X12.  
  
-   **Las validaciones que se realizan solo si se habilitan son**:  
  
    -   Validación EDI realizada en elementos de datos de conjuntos de transacciones. Esta se lleva a cabo si se habilita en las propiedades de acuerdo.  
  
    -   Validación extendida realizada en elementos de datos de conjuntos de transacciones. Esta se lleva a cabo si se habilita en las propiedades de acuerdo.  
  
    -   Validación de campos cruzados en los elementos de datos del conjunto de transacciones (sólo mensajes con codificación X12). Esta se lleva a cabo si se habilita en el esquema del mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Validación estructural de EDI](../core/edi-structural-validation.md)   
 [Validación de propiedades de acuerdo](../core/agreement-properties-validation.md)   
 [Validación de tipo (elemento de datos) de EDI](../core/edi-type-data-element-validation.md)   
 [Validación extendida (BTS-XSD)](../core/extended-bts-xsd-validation.md)   
 [Validación de esquemas](../core/schema-validation2.md)   
 [Campo de segmento validación cruzada](../core/cross-field-segment-validation.md)