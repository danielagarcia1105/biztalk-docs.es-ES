---
title: 'De sesión único: Evento 10519 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e709957e-a690-4a44-a863-07b2a55dae7b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 770ade349f00ff3fa95bbfb84474047ef06cc70b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980317"
---
# <a name="single-sign-on-event-10519"></a>De sesión único: Evento 10519
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                                                                                                                         Inicio de sesión único (SSO) empresarial                                                                                                                                                                                                                                          |
| Versión del producto |                                                                                                                                                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                                                                         |
|    Identificador del evento     |                                                                                                                                                                                                                                                   10519                                                                                                                                                                                                                                                    |
|  Origen del evento   |                                                                                                                                                                                                                                                   ENTSSO                                                                                                                                                                                                                                                   |
|    Componente    |                                                                                                                                                                                                                                                    N\D                                                                                                                                                                                                                                                     |
|  Nombre simbólico  |                                                                                                                                                                                                                                        SSO_WARN_BAD_APP_ADMIN_GROUP                                                                                                                                                                                                                                        |
|  Texto del mensaje   | Cuenta de administradores de aplicación no válida para esta aplicación. Si se trata de una cuenta local, compruebe si existe en el servidor. Si se trata de una cuenta de dominio, póngase en contacto con el administrador de dominio. Habilite la aplicación cuando la cuenta sea válida. Puede ignorar este mensaje si no usará esta aplicación en este equipo.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Administradores de aplicación: %2 %r<br /><br /> Cuentas no válidas: %3 %r<br /><br /> Código de error: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que una cuenta de grupo de administradores de aplicación no es una cuenta de Windows válida. Hay una cuenta de grupo de administradores de aplicación por cada aplicación afiliada.  

## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  

- Compruebe si existe la cuenta de administradores de aplicación.  

- Use la utilidad de administración de SSO para comprobar si la aplicación afiliada especificada está configurada para usar la cuenta de administradores de aplicación adecuada.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Grupos de usuarios de SSO](../core/sso-user-groups.md)  

- [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)  

- [Cómo actualizar las propiedades de una aplicación afiliada](../core/how-to-update-the-properties-of-an-affiliate-application.md)
