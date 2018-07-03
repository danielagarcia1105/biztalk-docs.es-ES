---
title: Las condiciones de Error de confirmación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, errors
- errors, acknowledgements
ms.assetid: 605c7fa0-2365-4cb6-92fb-6df570905ca8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26bc0524e76521fcb673c6d5d3dc70f43cb12798
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970261"
---
# <a name="acknowledgment-error-conditions"></a>Condiciones de Error de confirmación
Las condiciones siguientes se producen un error irrecuperable de condición al Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) es la confirmación de procesamiento de mensajes (ACK):  
  
- Faltan campos obligatorios en MSH9  
  
- Faltan campos obligatorios en MSH12  
  
  Las condiciones siguientes producen una condición de error no grave. En esta situación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera la confirmación, pero también se suspende la confirmación:  
  
- Falta un campo obligatorio en MSH11  
  
- Falta un valor MSH10  
  
- Errores de tipo de enumeración para los campos opcionales en el encabezado.  
  
> [!NOTE]
>  Errores de tipo de enumeración se encuentran en el encabezado al 15 de MSH está establecido en AL o ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera una confirmación ACK con el estado **MSA_1 = CR**.  
  
## <a name="see-also"></a>Vea también  
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [Tipos de esquema de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [Segmento de confirmación del mensaje](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [Configurar un puerto de envío para recibir confirmaciones](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)