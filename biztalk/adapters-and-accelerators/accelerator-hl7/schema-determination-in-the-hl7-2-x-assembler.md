---
title: Determinación del esquema en el ensamblador HL7 2.X | Microsoft Docs
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
ms.openlocfilehash: 962f9576032ec8b42542111502c2b6d6698f98d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983653"
---
# <a name="schema-determination-in-the-hl7-2x-assembler"></a>Determinación del esquema en el ensamblador HL7 2.X
Cuando un mensaje fluye al serializador, el serializador en el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) usa MSH5 (entidad de destino) del mensaje para determinar las operaciones que se realizará en el mensaje. Estas operaciones incluyen:  
  
- Si se debe realizar la validación de XML de segmentos de cuerpo  
  
- Si se debe validar los tipos de datos personalizados para los segmentos de cuerpo  
  
- Si desea permitir delimitadores en el cuerpo de la derecha  
  
- Qué espacio de nombres de destino de esquema usará el serializador  
  
- Si el serializador se debe asignar el encabezado  
  
  Para determinar el esquema, el serializador realiza lo siguiente:  
  
- Establece el espacio de nombres de destino (**TargetNS**) en el mismo valor que el espacio de nombres configurado para la entidad de destino  
  
- Extrae **Rootnode** desde el **BTS. MessageType** propiedad promocionada  
  
  El **doctype** se convierte en **TargetNS + "#" + Rootnode**.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Procesamiento de archivos planos BTAHL72X](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)