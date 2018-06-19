---
title: Determinación del esquema en el ensamblador 2.X HL7 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, assembler
- MSH5
- assembler, schemas
ms.assetid: 464c006e-4fae-4e2a-99ea-157301c0179e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50a430750846ae2567f063f9aa77221bad9c97e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206100"
---
# <a name="schema-determination-in-the-hl7-2x-assembler"></a>Determinación del esquema en el ensamblador 2.X HL7
Cuando se transmite un mensaje para el serializador, el serializador en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) usa MSH5 (entidad de destino) del mensaje para determinar las operaciones que se realizarán en el mensaje. Estas operaciones incluyen:  
  
-   Si se debe realizar la validación de XML para los segmentos de cuerpo  
  
-   Si se debe validar los tipos de datos personalizados para los segmentos de cuerpo  
  
-   Si desea permitir delimitadores en el cuerpo finales  
  
-   Qué espacio de nombres de destino de esquema va a usar el serializador  
  
-   Si el serializador se debe asignar el encabezado  
  
 Para determinar el esquema, el serializador realiza lo siguiente:  
  
-   Establece el espacio de nombres de destino (**TargetNS**) en el mismo valor que el espacio de nombres configurado para la entidad de destino  
  
-   Extrae **Rootnode** desde el **BTS. MessageType** propiedad promocionada  
  
 El **doctype** se convierte en **TargetNS + "#" + Rootnode**.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Procesamiento de archivo sin formato BTAHL72X](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)