---
title: 'De sesión único: Evento 10521 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00d427ff-74d0-45f5-bb55-ab12b564d767
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8af1b2ac8d2ac3645db6a6a80146832378aececf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008573"
---
# <a name="single-sign-on-event-10521"></a>De sesión único: Evento 10521
## <a name="details"></a>Detalles  

|                 |                                                                       |
|-----------------|-----------------------------------------------------------------------|
|  Nombre del producto   |                       Inicio de sesión único (SSO) empresarial                       |
| Versión del producto |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]       |
|    Identificador del evento     |                                 10521                                 |
|  Origen del evento   |                                ENTSSO                                 |
|    Componente    |                                  N\D                                  |
|  Nombre simbólico  |                     SSO_ERROR_SECRETS_NOT_LOADED                      |
|  Texto del mensaje   | No se pudieron cargar secretos desde el Registro del servidor secreto principal. |

## <a name="explanation"></a>Explicación  
 Este evento de error se produce en el servidor secreto principal cuando no se pueden obtener los secretos principales del Registro. Es posible que haya mensajes de error relacionados en el registro de eventos con información adicional. La causa más probable es que se haya producido un error de permisos o de cifrado cuando la cuenta de servicio SSO intentó obtener acceso al Registro. Esto puede producirse si se ha cambiado la cuenta de servicio SSO. El secreto principal se cifra con una clave basada en la identidad de dicha cuenta. Si se cambia esa cuenta, el secreto principal existente del Registro ya no se puede descifrar.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Cambie la cuenta de servicio SSO. Para ello, haga una copia de seguridad del secreto principal, a continuación, cambie la cuenta de servicio SSO y, por último, restaure el secreto principal. Este procedimiento puede restaurar el secreto principal y debería solucionar este error.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Servidor de secreto maestro](../core/master-secret-server.md)  

- [Administración del secreto maestro](../core/managing-the-master-secret.md)  

- [Configuración de SSO](../core/configuring-sso.md)  

- [Recomendaciones de seguridad de SSO](../core/sso-security-recommendations.md)
