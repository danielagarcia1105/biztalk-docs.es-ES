---
title: 'De sesión único: Evento 10596 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d70aabcf-aa53-40bf-8937-44f191af1aec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a1e565ca3b96663e0ece5a2cf68c02d3258ac5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008797"
---
# <a name="single-sign-on-event-10596"></a>De sesión único: Evento 10596
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                         Inicio de sesión único (SSO) empresarial                                                                                                          |
| Versión del producto |                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    Identificador del evento     |                                                                                                                   10596                                                                                                                    |
|  Origen del evento   |                                                                                                                   ENTSSO                                                                                                                   |
|    Componente    |                                                                                                                    N/D                                                                                                                     |
|  Nombre simbólico  |                                                                                                     SSO_WARN_TICKET_USER_NOT_IN_GROUP                                                                                                      |
|  Texto del mensaje   | No se puede canjear el vale porque el usuario para el que se emitió no es miembro de la cuenta de usuarios de aplicación.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Vale emitido para: %2 %r<br /><br /> Los usuarios de aplicación: %3 |
  
## <a name="explanation"></a>Explicación  
 No se puede canjear el vale porque el usuario para el que se emitió no es miembro de la cuenta de usuarios de aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 Vuelva a emitir el vale para un usuario que sea miembro de la cuenta de usuarios de aplicación.