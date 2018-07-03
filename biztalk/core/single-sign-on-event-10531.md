---
title: 'De sesión único: Evento 10531 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 264941f4-7791-4a1f-a0bf-b992c9ccda64
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74dd7f4e39997e3bbd78ffce8a7bd164968bb358
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006765"
---
# <a name="single-sign-on-event-10531"></a>De sesión único: Evento 10531
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                    Inicio de sesión único (SSO) empresarial                                                                                     |
| Versión del producto |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                    |
|    Identificador del evento     |                                                                                              10531                                                                                               |
|  Origen del evento   |                                                                                              ENTSSO                                                                                              |
|    Componente    |                                                                                               N\D                                                                                                |
|  Nombre simbólico  |                                                                                     SSO_ERROR_GET_SECRET_OK                                                                                      |
|  Texto del mensaje   | Solicitud de obtención de secreto principal satisfactoria.%r<br /><br /> Número secreto: %1 %r<br /><br /> MSID: %2 %r<br /><br /> Usuario cliente: %3 %r<br /><br /> Equipo cliente: %4 %r<br /><br /> Id. de seguimiento: %5 |

## <a name="explanation"></a>Explicación  
 Este evento indica que la solicitud de obtención del secreto principal fue satisfactoria.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)  

- [Administración del secreto maestro](../core/managing-the-master-secret.md)
