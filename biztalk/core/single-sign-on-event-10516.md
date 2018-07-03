---
title: 'De sesión único: Evento 10516 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d20df92f-c995-4cbc-a8f9-21cea30b82c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d0f3ab8e5d368c04b1a93b9e7e00efa76c50283
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023530"
---
# <a name="single-sign-on-event-10516"></a>De sesión único: Evento 10516
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                                                                                                 |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                                            Inicio de sesión único (SSO) empresarial                                                                                                                                                            |
| Versión del producto |                                                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                            |
|    Identificador del evento     |                                                                                                                                                                      10516                                                                                                                                                                      |
|  Origen del evento   |                                                                                                                                                                     ENTSSO                                                                                                                                                                      |
|    Componente    |                                                                                                                                                                       N\D                                                                                                                                                                       |
|  Nombre simbólico  |                                                                                                                                                           SSO_ERROR_BAD_SSO_APP_ADMIN                                                                                                                                                           |
|  Texto del mensaje   | Cuenta de administradores afiliados de SSO no válida. Si se trata de una cuenta local, compruebe si existe en el servidor. Si se trata de una cuenta de dominio, póngase en contacto con el administrador de dominio. Cuando la cuenta sea válida, habilite SSO.%r<br /><br /> Administradores afiliados de SSO: %1 %r<br /><br /> Cuentas no válidas: %2 %r<br /><br /> Código de error: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que el grupo o la cuenta de administradores afiliados de SSO creada por el inicio de sesión único empresarial no es una cuenta de Windows válida. La cuenta de administradores afiliados de SSO puede ser una cuenta de grupo de Windows o una cuenta individual. La cuenta de administradores afiliados de SSO también puede ser una cuenta de grupo local o de dominio.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe si existe la cuenta de administradores afiliados de SSO.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Grupos de usuarios de SSO](../core/sso-user-groups.md)  

- [Cómo actualizar la base de datos SSO](../core/how-to-update-the-sso-database.md)
