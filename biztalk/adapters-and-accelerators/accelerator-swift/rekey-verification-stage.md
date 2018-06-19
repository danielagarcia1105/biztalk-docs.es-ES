---
title: Regenerar la fase de comprobación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- rekey verification
- stages, rekey verification
ms.assetid: 8a2880b6-bb25-4af5-9f51-d0b090ca38c8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9fe163a8351b0edc904f81d77a7ea341de13df6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214204"
---
# <a name="rekey-verification-stage"></a>Regenerar la fase de comprobación
Cuando una verificación regenerar fase se produce en el flujo de trabajo de reparación de mensajes, una copia del mensaje original se mantiene por mensaje reparar y nuevo envío y una copia exacta del mensaje se envía a la Bandeja de entrada del Comprobador de regenerar la comprobación. En la comprobación de regeneración de claves, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] reparación de mensajes y nuevo envío borra los campos especificados para la reentrada manual.  
  
 Este concepto se explica con más detalle en la [seguridad del servidor en tiempo de ejecución](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md) tema. El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario participa en la fase de comprobación regenerar debe volver a especificar manualmente en los campos borrados, a través de la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formar, valores que coinciden exactamente con los del mensaje original (de fase de la creación o la reparación). A continuación, el Comprobador de firma el mensaje con un certificado válido y envía el mensaje.  
  
 Si los valores de los campos rekeyed no coincide exactamente con los campos del mensaje original, reparación de mensajes y nuevo envío restablece la fase en el flujo de trabajo y devuelve el mensaje a la Bandeja de entrada del taller de reparación. También valida la firma del Comprobador que cambia los campos. Si no se valida el Comprobador, envía el mensaje a la Bandeja de entrada del comprobador.