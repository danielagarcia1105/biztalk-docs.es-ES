---
title: 'De sesión único: Evento 10525 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3cba8ef4-4e48-44a7-b791-bab7dc4b9cc0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae350ce6b1688d908dedb3961007401300d8d2fc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968197"
---
# <a name="single-sign-on-event-10525"></a>De sesión único: Evento 10525
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                      Inicio de sesión único (SSO) empresarial                                                                       |
| Versión del producto |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    Identificador del evento     |                                                                                10525                                                                                 |
|  Origen del evento   |                                                                                ENTSSO                                                                                |
|    Componente    |                                                                                 N\D                                                                                  |
|  Nombre simbólico  |                                                                     SSO_INFO_GENERATE_SECRET_OK                                                                      |
|  Texto del mensaje   | El nuevo secreto principal se generó correctamente.%r<br /><br /> MSID: %1 %r<br /><br /> Usuario cliente: %2 %r<br /><br /> Equipo cliente: %3 %r<br /><br /> Id. de seguimiento: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que se generó un nuevo secreto principal correctamente.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)  

- [Administración del secreto maestro](../core/managing-the-master-secret.md)
