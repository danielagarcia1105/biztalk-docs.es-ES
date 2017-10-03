---
title: "Eliminar datos adjuntos huérfanos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maintaining databases, deleting orphaned attachments
- databases, deleting orphaned attachments
- attachments
ms.assetid: 38280464-9c9d-4890-9fc5-4b8031dd3f88
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7660182793cc82ac938f0dd25011a7c4ad7d7e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deleting-orphan-attachments"></a>Eliminar datos adjuntos huérfanos
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] almacena los datos adjuntos de los mensajes recibidos. En ciertas circunstancias, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] guarda los datos adjuntos, pero elimina el mensaje asociado de la tabla MessagesToLOB, lo que da lugar a un archivo adjunto huérfano. Esto puede ocurrir cuando se envía un mensaje que incluya un archivo adjunto y tiene un manifiesto que no es válido, por ejemplo, un manifiesto en qué NumberOfAttachments = 0. Periódicamente, puede que desee eliminar datos adjuntos de huérfanos para mantener el rendimiento del sistema.  
  
## <a name="how-to-delete-orphan-attachments"></a>Cómo eliminar datos adjuntos huérfanos  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]almacena los datos adjuntos en la tabla de datos adjuntos de la base de datos BTARNDATA. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]almacena los mensajes asociados en la tabla MessagesToLOB. Datos adjuntos huérfanos se produce cuando los datos adjuntos tienen un `outMessageID` propiedad que no se corresponde con el `MessageID` propiedad de un mensaje en la tabla MessagesToLOB.  
  
 Periódicamente, puede que desee eliminar datos adjuntos de la tabla mediante un procedimiento almacenado que elimina solo los datos adjuntos que no tienen un mensaje correspondiente en la tabla MessagesToLOB. Es un ejemplo de la instrucción SQL para el procedimiento almacenado:  
  
```  
delete from attachments where outMessageID not in (select messageid from messagestolob)  
```  
  
 Además, se recomienda que elimine los datos adjuntos que son anteriores a un período determinado y no requieren una investigación más. La tabla de datos adjuntos contiene un `TimeCreated` propiedad que puede usar para eliminar antiguos archivos adjuntos. Este proceso es similar al proceso utilizado para eliminar resúmenes anteriores. Para una instrucción SQL de ejemplo para un procedimiento almacenado que elimina el antiguos resúmenes, consulte [eliminar resúmenes](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md).  
  
 También se recomienda que se puede indizar los datos adjuntos y MessagestoLOB tablas en las columnas respectivas de MessageID.  
  
## <a name="see-also"></a>Vea también  
 [Mantener bases de datos BTARN](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)