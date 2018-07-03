---
title: Eliminación de resúmenes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, digests
- messages, digests
- digests
- databases, deleting digests
- maintaining databases, deleting digests
ms.assetid: bcc7cb11-2f6a-4996-ad50-040d41993e09
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10e32f8d86d6723965e8a27ad51f7551fdda0b60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002405"
---
# <a name="deleting-digests"></a>Eliminación de resúmenes
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] almacena los resúmenes de los mensajes salientes, por lo que puede validarlas con contenido de la señal. Sin embargo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no elimina los resúmenes de después de la validación. Periódicamente, es posible que desea eliminar estos resúmenes para mantener el rendimiento del sistema.  
  
## <a name="when-and-how-to-delete-digests"></a>Cuándo y cómo eliminar resúmenes  
 Resúmenes de se almacenan en la tabla MessageDigestHelper de la base de datos BTARNDATA. Periódicamente, desea eliminar estos resúmenes de la tabla mediante el uso de un procedimiento almacenado que elimina solo los resúmenes que tienen más de un período determinado. La tabla MessageDigestHelper contiene un `TimeCreated` propiedad que puede usar para este propósito.  
  
 Crear un procedimiento almacenado con la siguiente instrucción SQL (como modificado para sus fines) y ejecute el procedimiento almacenado para eliminar el antiguos resúmenes. Esta instrucción de ejemplo elimina todos los resúmenes de más de siete días:  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  El procedimiento almacenado debe incluir una llamada a `getutcdate`, no `getdate`, ya que todos los [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] bases de datos utilizan la hora UTC (hora Universal coordinada).  
  
## <a name="see-also"></a>Vea también  
 [Mantenimiento de bases de datos BTARN](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)