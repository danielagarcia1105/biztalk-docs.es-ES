---
title: 'De sesión único: Evento 11059 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac5b6ce7-8819-4b9d-85f7-f5dfaf940487
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a22b2a68acc6cd4be3d5cf854a4d965d897e302
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965781"
---
# <a name="single-sign-on-event-11059"></a>De sesión único: Evento 11059
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                               Inicio de sesión único (SSO) empresarial                                                                                                               |
| Versión del producto |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    Identificador del evento     |                                                                                                                         11059                                                                                                                         |
|  Origen del evento   |                                                                                                                        ENTSSO                                                                                                                         |
|    Componente    |                                                                                                                          N/D                                                                                                                          |
|  Nombre simbólico  |                                                                                                          SSO_INFO_INVALID_USER_NOT_IN_GROUP                                                                                                           |
|  Texto del mensaje   | No se pudo crear la asignación porque el usuario especificado no es miembro de la cuenta de usuarios de aplicación.%r<br /><br /> Cuenta de Windows: %1\\%2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Usuarios de aplicación: %4 %r<br /><br /> Código de error: %5 |
  
## <a name="explanation"></a>Explicación  
 No se pudo crear la asignación porque el usuario especificado no es miembro de la cuenta de usuarios de aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 Póngase en contacto con el administrador de ENTSSO para consultarle cómo ser miembro de una cuenta de usuarios de aplicación.