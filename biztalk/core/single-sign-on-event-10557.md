---
title: 'De sesión único: Evento 10557 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f29bc394-4c56-4ded-93a1-004afb3a054a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 612231da7c3098eca4d3cc901b83b66e48e09c9f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997533"
---
# <a name="single-sign-on-event-10557"></a>De sesión único: Evento 10557
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                        Inicio de sesión único (SSO) empresarial                                                                                         |
| Versión del producto |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    Identificador del evento     |                                                                                                  10557                                                                                                   |
|  Origen del evento   |                                                                                                  ENTSSO                                                                                                  |
|    Componente    |                                                                                                   N/D                                                                                                    |
|  Nombre simbólico  |                                                                                   SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS                                                                                   |
|  Texto del mensaje   | No se permite que los usuarios de aplicación controlen asignaciones para aplicaciones de grupo.%r<br /><br /> Nombre de dominio: %1 %r<br /><br /> Nombre de usuario: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Usuario cliente: %4 |
  
## <a name="explanation"></a>Explicación  
 Un usuario de aplicación no tiene privilegios suficientes para crear o controlar asignaciones para aplicaciones de grupo.  
  
## <a name="user-action"></a>Acción del usuario  
 Esta actividad debe realizarla el administrador de aplicaciones.