---
title: 'De sesión único: Evento 10710 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 469dc407-be7a-45a1-bcf5-2ba7060a19e2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 888468da03c01f654bd550ce210b02c4a03ad40b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989925"
---
# <a name="single-sign-on-event-10710"></a>De sesión único: Evento 10710
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                          Inicio de sesión único (SSO) empresarial                                                                          |
| Versión del producto |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                          |
|    Identificador del evento     |                                                                                    10710                                                                                    |
|  Origen del evento   |                                                                                   ENTSSO                                                                                    |
|    Componente    |                                                                                     N\D                                                                                     |
|  Nombre simbólico  |                                                                        SSO_INFO_PS_WIN_CHANGE_DAMPED                                                                        |
|  Texto del mensaje   | Se descartó el cambio de contraseña de Windows (se detectó como duplicado y se descartó).%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Usuario cliente: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que el cambio de contraseña de Windows se descartó porque se detectó como duplicado.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, vea los recursos siguientes:  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
