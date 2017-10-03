---
title: "Inicio de sesión único: Evento 10561 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 770e6fc1-0854-4555-8f2a-5f199e3aaca7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5148633c7fffabe0ef4bb4789fe4ded58336c10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10561"></a>Inicio de sesión único: Evento 10561
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10561|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_ERROR_BACKUP_FAILED_MEDIA|  
|Texto del mensaje|El archivo especificado para copia de seguridad de secretos principales debe estar en un sistema de archivos NTFS o en un medio extraíble.%r<br /><br /> Nombre de archivo: %1 %r<br /><br /> El usuario cliente: %2 %r<br /><br /> Equipo cliente: %3 %r<br /><br /> Código de error: %4|  
  
## <a name="explanation"></a>Explicación  
 Se intentó realizar una copia de seguridad mediante un medio no válido, como un archivo FAT. El archivo especificado para copia de seguridad de secretos principales debe estar en un sistema de archivos NTFS o en un medio extraíble.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe el formato de medio y asegúrese de que sea NTFS o extraíble.