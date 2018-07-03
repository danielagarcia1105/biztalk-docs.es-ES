---
title: 'De sesión único: Evento 10610 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6a400eb-7cf2-49df-befb-caf76e845fdf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c90855c1f136dc8204afe718ea4456c834ab667
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024410"
---
# <a name="single-sign-on-event-10610"></a>De sesión único: Evento 10610
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                       Inicio de sesión único (SSO) empresarial                                                       |
| Versión del producto |                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    Identificador del evento     |                                                                 10610                                                                 |
|  Origen del evento   |                                                                ENTSSO                                                                 |
|    Componente    |                                                                  N/D                                                                  |
|  Nombre simbólico  |                                                      SSO_WARN_CRED_CACHE_FAILED                                                       |
|  Texto del mensaje   | La memoria caché de credenciales detectó un error inesperado y se cerró. Esto puede afectar el rendimiento.%r<br /><br /> Código de error: %1 |
  
## <a name="explanation"></a>Explicación  
 La memoria caché de credenciales detectó un error inesperado y se cerró. Si bien este error puede afectar el rendimiento, no afectará la funcionalidad.  
  
## <a name="user-action"></a>Acción del usuario  
 Reinicie el servicio SSO cuando lo considere conveniente.