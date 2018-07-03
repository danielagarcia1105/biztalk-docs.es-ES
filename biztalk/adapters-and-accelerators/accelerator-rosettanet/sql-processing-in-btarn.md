---
title: Procesamiento de SQL en BTARN | Microsoft Docs
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
ms.openlocfilehash: 21255c03a9a9c1f2a30eb7f716c5e1bf285a3c5b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000717"
---
# <a name="sql-processing-in-btarn"></a>Procesamiento de SQL en BTARN
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] usa un adaptador de SQL para enrutar un mensaje de la aplicación de línea de negocio (LOB). Utiliza un puerto de envío SQL para redirigir un mensaje a la aplicación de LOB.  
  
## <a name="message-flow"></a>Flujo de mensajes  
 En el iniciador o el equipo de respuesta, la aplicación de LOB de back-end enruta un mensaje a la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] usa un adaptador de SQL para mover el mensaje de la tabla MessagesFromLOB al proceso privado. Para obtener más información, consulte "Adaptador de SQL" en la Ayuda de BizTalk Server.  
  
 Puede elegir usar un adaptador de archivo para enviar contenido de servicio a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], en lugar de usar el adaptador SQL predeterminado. Si decide usar un adaptador de archivo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no admite datos adjuntos.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)