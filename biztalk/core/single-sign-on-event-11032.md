---
title: 'De sesión único: Evento 11032 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d58cf9d-6806-4580-8014-7eff88d5cc5f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dc69ecf447f0917f843a0f80a0a25b1ed0b6e0a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022050"
---
# <a name="single-sign-on-event-11032"></a>De sesión único: Evento 11032
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                            Inicio de sesión único (SSO) empresarial                                                                                                                             |
| Versión del producto |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    Identificador del evento     |                                                                                                                                      11032                                                                                                                                       |
|  Origen del evento   |                                                                                                                                      ENTSSO                                                                                                                                      |
|    Componente    |                                                                                                                                       N/D                                                                                                                                        |
|  Nombre simbólico  |                                                                                                                     SSO_INFO_PS_WIN_CHANGE_MAPPING_DISABLED                                                                                                                      |
|  Texto del mensaje   | Cambio de contraseña de Windows. Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque está deshabilitada.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Aplicación: %3 %r<br /><br /> Cuenta externa: %4 %r<br /><br /> Usuario cliente: %5 |
  
## <a name="explanation"></a>Explicación  
 Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque está deshabilitada.  
  
## <a name="user-action"></a>Acción del usuario  
  
-   Para habilitar la asignación, consulte [cómo habilitar una asignación de usuario](../core/how-to-enable-a-user-mapping.md).