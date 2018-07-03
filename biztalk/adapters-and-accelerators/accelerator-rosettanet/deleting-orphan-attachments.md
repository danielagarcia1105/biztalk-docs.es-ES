---
title: Eliminar datos adjuntos huérfanos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maintaining databases, deleting orphaned attachments
- databases, deleting orphaned attachments
- attachments
ms.assetid: 38280464-9c9d-4890-9fc5-4b8031dd3f88
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99b31633c27aaed7cb8ae7289f383a5bfcac8d1b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971893"
---
# <a name="deleting-orphan-attachments"></a>Eliminar datos adjuntos huérfanos
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] almacena los datos adjuntos de los mensajes recibidos. En determinadas circunstancias, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] guarda los datos adjuntos, pero elimina el mensaje asociado de la tabla MessagesToLOB, lo que produce datos adjuntos huérfanos. Esto puede ocurrir cuando se envía un mensaje que tiene datos adjuntos y tiene un manifiesto que no es válido, por ejemplo, un manifiesto en qué NumberOfAttachments = 0. Periódicamente, es posible que desee eliminar datos adjuntos huérfanos para mantener el rendimiento del sistema.  
  
## <a name="how-to-delete-orphan-attachments"></a>Cómo eliminar datos adjuntos huérfanos  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] almacena los datos adjuntos en la tabla de datos adjuntos de la base de datos BTARNDATA. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] almacena los mensajes asociados en la tabla MessagesToLOB. Datos adjuntos huérfanos se produce cuando los datos adjuntos tienen un `outMessageID` propiedad que no corresponde a la `MessageID` propiedad de un mensaje en la tabla MessagesToLOB.  
  
 Periódicamente, es posible que desee eliminar los datos adjuntos de la tabla mediante el uso de un procedimiento almacenado que elimina solo los datos adjuntos que no tiene un mensaje correspondiente en la tabla MessagesToLOB. Es un ejemplo de la instrucción SQL para el procedimiento almacenado:  
  
```  
delete from attachments where outMessageID not in (select messageid from messagestolob)  
```  
  
 Además, se recomienda que elimine los datos adjuntos que tienen más de un período determinado y no requieren una investigación más. La tabla de datos adjuntos contiene un `TimeCreated` propiedad que puede usar para eliminar antiguos archivos adjuntos. Este proceso es similar al proceso que se usa para eliminar el antiguos resúmenes. Para una instrucción SQL de ejemplo para un procedimiento almacenado que elimina resúmenes antiguos, consulte [eliminando resúmenes](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md).  
  
 También se recomienda que indexar los datos adjuntos y MessagestoLOB tablas en las columnas respectivas de MessageID.  
  
## <a name="see-also"></a>Vea también  
 [Mantenimiento de bases de datos BTARN](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)