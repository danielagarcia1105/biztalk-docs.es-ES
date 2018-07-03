---
title: 'De sesión único: Evento 10735 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31c791c6-1901-4441-b329-ed75833cb83e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ede774a4a212d71aa65165f7da1f6de5bb04103c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979229"
---
# <a name="single-sign-on-event-10735"></a>De sesión único: Evento 10735
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                             Inicio de sesión único (SSO) empresarial                                                                                                              |
| Versión del producto |                                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    Identificador del evento     |                                                                                                                       10735                                                                                                                        |
|  Origen del evento   |                                                                                                                       ENTSSO                                                                                                                       |
|    Componente    |                                                                                                                        N\D                                                                                                                         |
|  Nombre simbólico  |                                                                                                              SSO_WARN_PS_APP_DISABLED                                                                                                              |
|  Texto del mensaje   | Cambio de contraseña externa. No se pudo cambiar la contraseña de la cuenta externa porque la aplicación está deshabilitada.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Cuenta externa: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no se cambió la contraseña de la cuenta externa porque la aplicación está deshabilitada.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  

- Habilite la aplicación afiliada.  

  Para obtener más información, vea los recursos siguientes:  

- [Cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
