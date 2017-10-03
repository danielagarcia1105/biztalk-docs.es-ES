---
title: "Inicio de sesión único: Evento 10759 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5347f3d6-d31a-4c00-a64c-c0b0f680de88
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81ff42b71499df5848a55848b3dc1067adb830bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10759"></a>Inicio de sesión único: Evento 10759
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10759|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA|  
|Texto del mensaje|El archivo especificado para copia de seguridad o restauración de secretos principales debe estar en un sistema de archivos NTFS o en un medio extraíble.|  
  
## <a name="explanation"></a>Explicación  
 Sólo se pueden proteger los sistemas de archivos NTFS o los medios extraíbles.  
  
## <a name="user-action"></a>Acción del usuario  
 Para realizar la copia de seguridad del secreto principal, cambie a un sistema de archivos NTFS o a un medio extraíble.