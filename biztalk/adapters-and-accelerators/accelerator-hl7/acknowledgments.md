---
title: Confirmaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, acknowledgements
- parties, acknowledgements
- acknowledgements, about acknowledgements
- acknowledgements, messages
- acknowledgements, parties
ms.assetid: d25352a4-bae9-4de9-a504-2339bea25c4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46dedd4f2173fd4a3ad36c272963334b4ce66a20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969789"
---
# <a name="acknowledgments"></a>Confirmaciones
Configurar confirmaciones HL7 en el nivel de entidad mediante el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) configuración del explorador. Las confirmaciones se aplican a las entidades que envían mensajes de HL7 a través de una ubicación de recepción (posiblemente el adaptador MLLP) y el HL7 2.X canalización de recepción. Cuando completa un mensaje de análisis y la validación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede crear un mensaje de confirmación que contiene el resultado (éxito o error), el proceso de validación. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede devolver mensajes de confirmación de dos maneras. Si la entidad remitente original enviado el mensaje original a través de un bidireccional recibir la configuración del puerto, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] devuelve el mensaje de confirmación a través de esa ubicación original del puerto. Si el puerto envío original enviado el mensaje original a través de un sentido puerto de recepción [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía el mensaje de confirmación en la base de datos de cuadro de mensajes y se distribuye con el modelo de suscripción.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] realiza la asociación de entidad para recibir el mensaje procesar automáticamente en función del valor dentro del campo de aplicación de envío del mensaje HL7 (MSH 3.1).  
  
## <a name="see-also"></a>Vea también  
 [Flujo de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-flow.md)