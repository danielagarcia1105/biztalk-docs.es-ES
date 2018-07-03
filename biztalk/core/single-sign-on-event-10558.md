---
title: 'De sesión único: Evento 10558 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d9a281d6a6ca20a274db4b3ffe5b2697ff812c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974875"
---
# <a name="single-sign-on-event-10558"></a>De sesión único: Evento 10558
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                  Inicio de sesión único (SSO) empresarial                                                                                   |
| Versión del producto |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    Identificador del evento     |                                                                                            10558                                                                                             |
|  Origen del evento   |                                                                                            ENTSSO                                                                                            |
|    Componente    |                                                                                             N/D                                                                                              |
|  Nombre simbólico  |                                                                                  SSO_WARN_USER_OWN_MAPPINGS                                                                                  |
|  Texto del mensaje   | Sólo se permiten usuarios de aplicación para controlar sus propias asignaciones.%r<br /><br /> Nombre de dominio: %1 %r<br /><br /> Nombre de usuario: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Usuario cliente: %4 |
  
## <a name="explanation"></a>Explicación  
 Un usuario de aplicación intentó controlar las asignaciones de otro usuario. Esto no está permitido.  
  
## <a name="user-action"></a>Acción del usuario  
 Las asignaciones sólo pueden ser controladas por los usuarios de aplicación de esas asignaciones específicas.