---
title: Mantenimiento de las tablas de base de datos sin repudio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- databases, purging
- databases, non-repudiation database
- maintaining databases, purging
- purging databases
- databases, maintaining
- non-repudiation, database
ms.assetid: 29222510-325b-4cd7-854b-6f548a63fd08
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ceea893a49512167242eb6552e6a23c5a84cd18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966229"
---
# <a name="maintaining-the-non-repudiation-database-tables"></a>Mantenimiento de las tablas de base de datos sin repudio
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] almacena los mensajes para fines sin repudio en las tablas MessageStorageIn y MessageStorageOut de la base de datos BTARNArchive. Muchos mensajes en estas tablas pueden afectar al rendimiento del sistema. Desea mantener estas tablas de base de datos sin repudio periódicamente purgar y archivar los mensajes de dichas tablas, según corresponda.  
  
## <a name="routine-database-maintenance"></a>Mantenimiento rutinario de la base de datos  
 Cuando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] recibe un mensaje, siempre se guarda el mensaje en la tabla MessageStorageIn y se establece inicialmente el **ToBePurged** campo "1", lo que indica que el mensaje no requieren un sin repudio. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] a continuación, descifra y descodifica el mensaje para determinar cuál es el acuerdo. Después de descifrado y la descodificación, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] examina el contrato para ver si debe guardar el mensaje para fines sin repudio. Si es así, Establece la **ToBePurged** campo "0" y rellene los demás campos del mensaje. Si no, abandona el **ToBePurged** campo como "1" y no rellene los demás campos del mensaje.  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no se elimina automáticamente los mensajes con el **ToBePurged** campo establecido en "1". Además, no archiva mensajes guardados para el no rechazo a otras tablas. Estos dos conjuntos de mensajes pueden acumular en la tabla MessageStorageIn y afectar al rendimiento. Como parte del mantenimiento rutinario en la base de datos, puede hacer lo siguiente:  
  
-   Ejecutar un procedimiento almacenado que contiene el código SQL siguiente instrucción para eliminar todos los mensajes en la tabla MessageStorageIn cuyos **ToBePurged** campo no es igual a "0":  
  
    ```  
    delete MessageStorageIn where ToBePurged <> 0  
    ```  
  
-   Después de un período adecuado (puede dictar qué directiva de empresa), ejecute un procedimiento almacenado para archivar los mensajes de rechazo a una base de datos sin conexión que no afectará al rendimiento. Este período se puede determinar mediante el **TimeCreated** campo en la tabla MessageStorageIn. Una vez transcurrido el período de rechazo de un mensaje, puede eliminar el mensaje de la base de datos de archivo mediante el uso de la siguiente instrucción SQL (lo que elimina los mensajes que tienen más de siete días):  
  
    ```  
    delete <archive table name> where datediff(d, TimeCreated, GetUTCDATA())>7  
    ```  
  
> [!NOTE]
>  El **TimeCreated** campo en la tabla MessageStorageIn está en formato UTC.  
  
> [!NOTE]
>  No debe eliminar un mensaje entrante que tiene menos de un hora de antigüedad.  
  
 Cuando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía un mensaje saliente, tiene acceso al acuerdo sin repudio. Si el contrato requiere sin repudio, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] guarda el mensaje en la tabla MessageStorageOut. Si no es así, no guarda el mensaje en la tabla. Esto significa que no hay ninguna necesidad de un **ToBePurged** campo en esta tabla. El mantenimiento solo necesario para la tabla MessageStorageOut consiste en archivar los mensajes de rechazo a una base de datos sin conexión tras un período adecuado, y eliminar cada mensaje después de su período de no repudio ha expirado. Puede hacerlo con la siguiente instrucción SQL (lo que elimina los mensajes que tienen más de siete días):  
  
```  
delete MessageStorageOut where datediff(d, TimeCreated, GetUTCDATA())>7  
```  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes RNIF](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md)   
 [Administrar la configuración, certificados, bases de datos y seguridad](manage-configuration-certificates-databases-security.md)