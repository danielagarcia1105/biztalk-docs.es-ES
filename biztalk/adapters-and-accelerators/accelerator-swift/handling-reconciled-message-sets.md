---
title: Control de conjuntos de mensajes reconciliar | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAA
- messages, reconciled sets
ms.assetid: 05cd0cf6-f0fd-4cbe-83c6-1ed5f2da8822
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d3a06955e0072348098ddd7f191bf4862fb119a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986093"
---
# <a name="handling-reconciled-message-sets"></a>Control de conjuntos de mensajes conciliados
Cuando devuelve una respuesta a AAS [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] registra la respuesta en el cuadro de mensajes y coincide con la respuesta o las respuestas al mensaje original. Puede implementar el comportamiento de la aplicación personalizada con esta información. Para ello, desarrollar controladores personalizados que implementan conjuntos reconciliar/respuesta al mensaje de reacciones específica del cliente. Puede crear controladores personalizados que haga lo siguiente:  

- Procesar los mensajes que se correlacionan FRR con un mensaje de confirmación negativo MTS21_FIN_ACKNAK, que indica que SWIFT no ha recibido correctamente el mensaje de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. Esto puede permitir que un taller de reparación solucionar el mensaje y vuelva a enviar a AAS y la red SWIFT, que después de la reparación, espero que pueda recibir el mensaje correctamente. Para obtener más información sobre esta solución, consulte [ejemplo de controlador NAK de FRR](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).  

- Quitar conjuntos de respuesta de mensajes publicados por la orquestación en una carpeta de archivos con nombres de archivo único que indica las relaciones de los mensajes en el conjunto. A continuación, puede realizar lógica de negocios en estos mensajes.  

- Procesar mensajes de tiempo de espera.  

- Los resultados de la transmisión del mensaje de registro y, a continuación, descartar los mensajes reales.
