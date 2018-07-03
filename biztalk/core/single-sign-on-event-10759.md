---
title: 'De sesión único: Evento 10759 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5347f3d6-d31a-4c00-a64c-c0b0f680de88
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 177b5d1383a583ddc33a67a7290bff98b1d13364
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967589"
---
# <a name="single-sign-on-event-10759"></a>De sesión único: Evento 10759
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                             Inicio de sesión único (SSO) empresarial                                             |
| Versión del producto |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    Identificador del evento     |                                                       10759                                                       |
|  Origen del evento   |                                                      ENTSSO                                                       |
|    Componente    |                                                        N/D                                                        |
|  Nombre simbólico  |                                       ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA                                        |
|  Texto del mensaje   | El archivo especificado para copia de seguridad o restauración de secretos principales debe estar en un sistema de archivos NTFS o en un medio extraíble. |
  
## <a name="explanation"></a>Explicación  
 Sólo se pueden proteger los sistemas de archivos NTFS o los medios extraíbles.  
  
## <a name="user-action"></a>Acción del usuario  
 Para realizar la copia de seguridad del secreto principal, cambie a un sistema de archivos NTFS o a un medio extraíble.