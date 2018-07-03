---
title: 'De sesión único: Evento 10523 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6cee5e88-7c30-45f7-9a2a-f907d8f5bd91
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be71c63079dfda8a8573bf6f1316fce0e1e0b9c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972485"
---
# <a name="single-sign-on-event-10523"></a>De sesión único: Evento 10523
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                         Inicio de sesión único (SSO) empresarial                                                                                         |
| Versión del producto |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                         |
|    Identificador del evento     |                                                                                                   10523                                                                                                   |
|  Origen del evento   |                                                                                                  ENTSSO                                                                                                   |
|    Componente    |                                                                                                    N\D                                                                                                    |
|  Nombre simbólico  |                                                                                        SSO_INFO_RESTORE_SECRET_OK                                                                                         |
|  Texto del mensaje   | Los secretos principales se restauraron correctamente.%r<br /><br /> Nombre de archivo: %1 %r<br /><br /> MSID actual: %2 %r<br /><br /> MSID anterior: %3 %r<br /><br /> Usuario cliente: %4 %r<br /><br /> Equipo cliente: %5 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que los secretos principales se restauraron correctamente.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Administración del secreto maestro](../core/managing-the-master-secret.md)  

- [Servidor de secreto maestro](../core/master-secret-server.md)
