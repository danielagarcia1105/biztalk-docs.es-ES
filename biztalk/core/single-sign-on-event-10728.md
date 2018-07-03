---
title: 'De sesión único: Evento 10728 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f579189c-c9a5-4d2c-a3d5-f0ba03c5a3ef
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5e37738d0bf566b2faf3b5b65c1152cd3ef6405
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995293"
---
# <a name="single-sign-on-event-10728"></a>De sesión único: Evento 10728
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                     Inicio de sesión único (SSO) empresarial                                                                                                                     |
| Versión del producto |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    Identificador del evento     |                                                                                                                               10728                                                                                                                               |
|  Origen del evento   |                                                                                                                              ENTSSO                                                                                                                               |
|    Componente    |                                                                                                                                N\D                                                                                                                                |
|  Nombre simbólico  |                                                                                                                         SSO_ERROR_VERSION                                                                                                                         |
|  Texto del mensaje   | Esta versión de servidor de SSO no es compatible con la base de datos de SSO. Actualice el servidor secreto principal.%r<br /><br /> Nombre de SQL Server: %1 %r<br /><br /> Nombre de la base de datos SSO: %2 %r<br /><br /> Versión de la base de datos SSO: %3 %r<br /><br /> Versión requerida: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que la versión de servidor de SSO es más reciente que la base de datos de SSO (versión que la creó originalmente).  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Actualice el servidor secreto principal de SSO para que coincida con la versión actual de este servidor de SSO. De este modo, se actualizará la base de datos de SSO a la versión actual.  

  Para obtener más información, vea los recursos siguientes:  

- [Administración del secreto maestro](../core/managing-the-master-secret.md)
