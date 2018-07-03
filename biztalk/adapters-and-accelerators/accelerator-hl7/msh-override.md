---
title: Invalidación de MSH | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, MSH segments
- routing, messages
- subscriptions
- messages, routing
- routing, MSH segments
- send ports, subscriptions
- MSH segments
- send ports, multiple ports
ms.assetid: 4f5700bc-c8f4-40c9-9c9c-2220fa2627ba
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73508f573e4584ae841779301c426fa06bb78144
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974253"
---
# <a name="msh-override"></a>Invalidación de MSH
Antes de Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) enruta un mensaje saliente de HL7 a un puerto de envío, es posible que desea reemplazar determinados valores dentro del segmento de MSH. Es posible que desee hacer esto cuando la suscripción para un mensaje contiene varios puertos de envío, y cada puerto de envío debería ver un valor diferente en el campo aplicación de recepción.  
  
## <a name="see-also"></a>Vea también  
 [Invalidaciones de campos MSH](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md)   
 [Confirmaciones](../../adapters-and-accelerators/accelerator-hl7/acknowledgments.md)