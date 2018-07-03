---
title: 'De sesión único: Evento 10529 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ed70e0-8458-4736-883f-a4536f094dc0
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74bc28f01db257c06223e1b1f79268ca63e3ca49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976949"
---
# <a name="single-sign-on-event-10529"></a>De sesión único: Evento 10529
## <a name="details"></a>Detalles  

|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                             Inicio de sesión único (SSO) empresarial                                             |
| Versión del producto |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    Identificador del evento     |                                                       10529                                                       |
|  Origen del evento   |                                                      ENTSSO                                                       |
|    Componente    |                                                        N\D                                                        |
|  Nombre simbólico  |                                            SSO_INFO_GOT_CURRENT_SECRET                                            |
|  Texto del mensaje   | Se obtuvo el secreto actual desde el servidor secreto principal.%r<br /><br /> Nombre del servidor secreto: %1 %r<br /><br /> MSID: %2 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que SSO obtuvo el secreto principal necesario desde el servidor secreto principal.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)  

- [Administración del secreto maestro](../core/managing-the-master-secret.md)
