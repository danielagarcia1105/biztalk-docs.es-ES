---
title: Control de conjuntos de mensajes reconciliarse | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SAA
- messages, reconciled sets
ms.assetid: 05cd0cf6-f0fd-4cbe-83c6-1ed5f2da8822
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fc9f35f9381f82df90acb92e9536bbd967901a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="handling-reconciled-message-sets"></a>Control conciliado conjuntos de mensajes
Cuando AAS devolución una respuesta a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] registra la respuesta en el cuadro de mensajes y coincide con la respuesta o respuestas al mensaje original. Puede implementar un comportamiento de aplicación personalizada con esta información. Para ello, desarrollar controladores personalizados que implementan reacciones específica del cliente a los conjuntos de conciliado/respuesta del mensaje. Puede crear controladores personalizados que haga lo siguiente:  
  
-   Procesar los mensajes que se correlacionan FRR con un mensaje de confirmación negativo MTS21_FIN_ACKNAK, lo que indica que SWIFT no ha recibido correctamente el mensaje de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. Esto puede permitir un taller de reparación solucionar el mensaje y enviarlo de nuevo a la red SWIFT, que después de la reparación espero será capaz de recibir el mensaje correctamente y AAS. Para obtener más información sobre esta solución, consulte [FRR NAK controlador ejemplo](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).  
  
-   Quitar conjuntos de respuesta de mensaje publicados por la orquestación en una carpeta de archivos con nombres de archivo único que indica las relaciones de los mensajes en el conjunto. A continuación, puede realizar la lógica de negocios en estos mensajes.  
  
-   Mensajes de proceso ha superado el tiempo de espera.  
  
-   Los resultados de la transmisión de mensajes de registro y, a continuación, descartar los mensajes reales.