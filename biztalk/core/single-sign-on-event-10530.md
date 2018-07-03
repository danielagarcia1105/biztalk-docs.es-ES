---
title: 'De sesión único: Evento 10530 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb37305-26fe-46a7-958d-3ed7f6876a7b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38eb770f795d23286b2a057a428e3bfec73e1674
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974885"
---
# <a name="single-sign-on-event-10530"></a>De sesión único: Evento 10530
## <a name="details"></a>Detalles  

|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                             Inicio de sesión único (SSO) empresarial                                              |
| Versión del producto |                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    Identificador del evento     |                                                       10530                                                        |
|  Origen del evento   |                                                       ENTSSO                                                       |
|    Componente    |                                                        N\D                                                         |
|  Nombre simbólico  |                                            SSO_INFO_GOT_PREVIOUS_SECRET                                            |
|  Texto del mensaje   | Se obtuvo el secreto anterior desde el servidor secreto principal.%r<br /><br /> Nombre del servidor secreto: %1 %r<br /><br /> MSID: %2 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que SSO cuenta con el secreto principal anterior.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)  

- [Administración del secreto maestro](../core/managing-the-master-secret.md)
