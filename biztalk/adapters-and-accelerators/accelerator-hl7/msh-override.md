---
title: "Invalidación de MSH | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ed4111e2fdb925740d248c9f751f7a80b9f046f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="msh-override"></a>Invalidación de MSH
Antes de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) enruta un mensaje saliente de HL7 a un puerto de envío, puede que desee reemplazar determinados valores dentro del segmento de MSH. Puede que desee hacer esto cuando la suscripción para un mensaje contiene varios puertos de envío, y cada puerto de envío debería ver un valor diferente en el campo de la aplicación de recepción.  
  
## <a name="see-also"></a>Vea también  
 [Invalidaciones de campo de MSH](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md)   
 [Confirmaciones](../../adapters-and-accelerators/accelerator-hl7/acknowledgments.md)