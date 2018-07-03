---
title: 'De sesión único: Evento 10666 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 103947bb-e843-4427-a28a-1cceec90e2ae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a82308e721f53f9d4eb81fdbdad771b69a1cade5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018274"
---
# <a name="single-sign-on-event-10666"></a>De sesión único: Evento 10666
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                         Inicio de sesión único (SSO) empresarial                                                                          |
| Versión del producto |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                         |
|    Identificador del evento     |                                                                                   10666                                                                                    |
|  Origen del evento   |                                                                                   ENTSSO                                                                                   |
|    Componente    |                                                                                    N\D                                                                                     |
|  Nombre simbólico  |                                                                  SSO_INFO_DAMPED_EXTERNAL_PASSWORD_CHANGE                                                                  |
|  Texto del mensaje   | Se descartó el cambio de contraseña externa (se detectó como duplicado y se descartó).%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta externa: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que se determinó que el cambio de contraseña externa era un duplicado y se lo descartó.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
