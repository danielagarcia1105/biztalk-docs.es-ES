---
title: 'De sesión único: Evento 11045 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7212f42-355d-446f-bd07-5fb4e799b607
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35e8a331aca4d53ab86c8950fa7858db7f15fe8f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996181"
---
# <a name="single-sign-on-event-11045"></a>De sesión único: Evento 11045
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                       Inicio de sesión único (SSO) empresarial                                                                                       |
| Versión del producto |                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    Identificador del evento     |                                                                                                 11045                                                                                                 |
|  Origen del evento   |                                                                                                ENTSSO                                                                                                 |
|    Componente    |                                                                                                  N/D                                                                                                  |
|  Nombre simbólico  |                                                                                   SSO_WARN_EXISTING_MAPPING_WINDOWS                                                                                   |
|  Texto del mensaje   | No se pudo crear la asignación porque ya existe una para la cuenta de Windows especificada.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Nombre de la aplicación: %2 %r<br /><br /> Cuenta de Windows: %3 |
  
## <a name="explanation"></a>Explicación  
 Ya existe una asignación para la cuenta de Windows especificada y no se permiten duplicados.  
  
## <a name="user-action"></a>Acción del usuario  
 No es necesario que el usuario realice ninguna acción.