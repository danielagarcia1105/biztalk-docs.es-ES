---
title: Lotes de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f893d16-2670-4463-9a89-6f5be912a045
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13936fc06807d0bdc4f8e13dbd7742919dc894b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990701"
---
# <a name="message-batches"></a>Lotes de mensajes
Cuando el adaptador tiene un grupo de mensajes que hay que procesar al mismo tiempo, debe dividir estos mensajes en lotes para optimizar el rendimiento. Mediante programación, los lotes de mensajes consisten en colecciones de mensajes con una operación asociada. Agrupar los mensajes en un lote en lugar de enviar los mensajes de forma individual, optimizar el uso de recursos y tareas de procesamiento. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el procesamiento por lotes para:  

- Amortizar el costo de las transacciones entre varios mensajes.  

- Aumentar la velocidad mediante la reducción del número interno de ciclos de ida y vuelta de base de datos.  

- Hacen un uso más eficaz de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de subprocesos procesando los mensajes de forma asincrónica.  

  Un lote es una unidad de trabajo atómica. Es decir, todas las operaciones que contiene se realizan correctamente o se producen errores en todas. Si una operación en un lote se realiza correctamente pero se producen errores en otra operación, todas las operaciones que componen el lote quedan invalidadas y los mensajes deben volver a enviarse. Ello significa que un adaptador debe realizar tres operaciones en respuesta a un lote con errores:  

- Determinar qué mensajes tienen errores.  

- Decidir qué hacer con los mensajes con errores.  

- Volver a enviar los mensajes sin errores.
