---
title: 'De sesión único: Evento 11031 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ecd24c2-e251-4eb9-b3ca-ec0f095bb23a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f90be8f631bbd9503de3401bc84d27af32aa991a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015085"
---
# <a name="single-sign-on-event-11031"></a>De sesión único: Evento 11031
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                Inicio de sesión único (SSO) empresarial                                                                                                                                |
| Versión del producto |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    Identificador del evento     |                                                                                                                                          11031                                                                                                                                          |
|  Origen del evento   |                                                                                                                                         ENTSSO                                                                                                                                          |
|    Componente    |                                                                                                                                           N/D                                                                                                                                           |
|  Nombre simbólico  |                                                                                                                         SSO_INFO_PS_WIN_CHANGE_INVALID_MAPPING                                                                                                                          |
|  Texto del mensaje   | Cambio de contraseña de Windows. Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque ya no es válida.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Aplicación: %3 %r<br /><br /> Cuenta externa: %4 %r<br /><br /> Usuario cliente: %5 |
  
## <a name="explanation"></a>Explicación  
 Es posible que la cuenta de Windows exista y sea válida, pero no es la cuenta de usuarios de aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 Elimine la asignación e intente crearla nuevamente.