---
title: "Eliminar resúmenes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, digests
- messages, digests
- digests
- databases, deleting digests
- maintaining databases, deleting digests
ms.assetid: bcc7cb11-2f6a-4996-ad50-040d41993e09
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fefa59a7638b7dc4627d5d7a019d753b4f6290b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deleting-digests"></a>Eliminación de resúmenes
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] almacena resúmenes para los mensajes salientes, para que pueda validar el contenido de señal. Sin embargo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no elimina los resúmenes de después de la validación. Periódicamente, puede que desee eliminar estos resúmenes para mantener el rendimiento del sistema.  
  
## <a name="when-and-how-to-delete-digests"></a>Cuándo y cómo eliminar resúmenes  
 Resúmenes de se almacenan en la tabla MessageDigestHelper de la base de datos BTARNDATA. Periódicamente, puede que desee eliminar estos resúmenes de la tabla mediante el uso de un procedimiento almacenado que elimina solo los resúmenes que tienen más de un período determinado. La tabla MessageDigestHelper contiene un `TimeCreated` propiedad que puede usar para este propósito.  
  
 Crear un procedimiento almacenado con la siguiente instrucción SQL (como modificado para sus fines) y ejecute el procedimiento almacenado para eliminar resúmenes anteriores. Esta declaración de ejemplo elimina todos los resúmenes de más de siete días:  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  El procedimiento almacenado debe incluir una llamada a `getutcdate`, no `getdate`, ya que todos los [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] bases de datos utilizan la hora UTC (hora Universal coordinada).  
  
## <a name="see-also"></a>Vea también  
 [Mantener bases de datos BTARN](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)