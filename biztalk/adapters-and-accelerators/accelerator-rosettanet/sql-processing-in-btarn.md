---
title: Procesamiento de SQL en BTARN | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- LOBs
- SQL processing
- messages, message flow
- BTARN, SQL processing
ms.assetid: cfaf804f-3803-438e-a22e-50f487fe21c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24798038ef7110a87efef2850c7787c066ae9511
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005061"
---
# <a name="sql-processing-in-btarn"></a>Procesamiento de SQL en BTARN
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] utiliza un adaptador de SQL para enrutar un mensaje de la aplicación de línea de negocio (LOB). Utiliza un puerto de envío SQL para redirigir un mensaje a la aplicación de LOB.  
  
## <a name="message-flow"></a>Flujo de mensajes  
 En el iniciador o el equipo de respuesta, la aplicación de LOB de back-end enruta un mensaje a la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]usa un adaptador de SQL para mover el mensaje de la tabla MessagesFromLOB al proceso privado. Para obtener más información, vea "Adaptador de SQL" en la Ayuda de BizTalk Server.  
  
 Puede elegir usar un adaptador de archivo para enviar contenido de servicio a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], en lugar de usar el adaptador SQL predeterminado. Si decide usar un adaptador de archivo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no admite datos adjuntos.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)