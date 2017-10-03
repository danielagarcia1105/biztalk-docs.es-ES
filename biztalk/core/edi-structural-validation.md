---
title: "Validación estructural de EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87086614-5616-441d-915c-2979c63c6e2f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505b9ac55eff0b6adb249d11788308f03902f1d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-structural-validation"></a>Validación estructural de EDI
Las especificaciones EDI de las codificaciones X12 y EDIFACT definen las reglas y convenciones específicas de la estructura de los intercambios EDI. El desensamblador EDI de EDIReceivePipeline comprueba que el sobre de cada mensaje recibido cumple con estas reglas estructurales. EDISendPipeline genera cada mensaje que se va a enviar según estas reglas y valida el sobre antes de enviarlo.  
  
 La validación estructural garantiza que están presentes los encabezados y los finalizadores necesarios. Las comprobaciones de integridad estructural incluyen comprobaciones de número y orden de bucle. Estas comprobaciones siempre se llevan a cabo para asegurarse de que el documento se analizará o serializará correctamente. Se realiza la validación incluso si la **validación de tipo EDI** o **validación extendida** opciones están deshabilitadas. Un intercambio que se produce un error en las validaciones estructurales básicas se suspenderá, incluso si la **validación de tipo EDI** o **validación extendida** opciones están deshabilitadas.  
  
 Los valores de los elementos de datos de los encabezados y finalizadores y el modo en que se separan los encabezados/finalizadores y los elementos de datos vienen determinados en el acuerdo. Se validan mediante la validación del esquema.  
  
 Para obtener más información acerca sobre y el contenido de cada conjunto de encabezados y finalizadores, vea [estructura de mensaje EDI](../core/edi-message-structure.md).  
  
## <a name="see-also"></a>Vea también  
 [Validación del mensaje EDI](../core/edi-message-validation.md)