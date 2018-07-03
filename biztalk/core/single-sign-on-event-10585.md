---
title: 'De sesión único: Evento 10585 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c55ada-1ee3-4626-b044-9c537d11f0d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a423ae8ca3328b2e3846c953036ae70aa6ff4f05
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966837"
---
# <a name="single-sign-on-event-10585"></a>De sesión único: Evento 10585
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                 Inicio de sesión único (SSO) empresarial                                                                                 |
| Versión del producto |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    Identificador del evento     |                                                                                           10585                                                                                           |
|  Origen del evento   |                                                                                          ENTSSO                                                                                           |
|    Componente    |                                                                                            N/D                                                                                            |
|  Nombre simbólico  |                                                                             SSO_WARN_EXPIRED_TICKET_REDEEMED                                                                              |
|  Texto del mensaje   | Se está canjeando un vale después de que caducó el período de tiempo de espera de vale. Esto se permite porque el período de tiempo de espera de vale está deshabilitado para esta aplicación.%r<br /><br /> Nombre de la aplicación: %1 |
  
## <a name="explanation"></a>Explicación  
 El tiempo de espera de vale se puede habilitar o deshabilitar. En este caso, se canjea un vale aunque su período de tiempo de espera ha caducado porque el tiempo de espera está deshabilitado.  
  
## <a name="user-action"></a>Acción del usuario  
 Si el tiempo de espera debía estar deshabilitado, no es necesario que el usuario realice ninguna acción. No obstante, si no tenía conocimiento de que el tiempo de espera de esta aplicación específica estaba deshabilitado, compruebe la aplicación de inmediato para asegurarse de que desea permitirlo.