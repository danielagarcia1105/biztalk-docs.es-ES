---
title: 'De sesión único: Evento 10676 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec0e86fb-921d-4505-b458-51b565123ea7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63228e82546e100c81bf01c301d7d9507f147671
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991933"
---
# <a name="single-sign-on-event-10676"></a>De sesión único: Evento 10676
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                             Inicio de sesión único (SSO) empresarial                                                                                             |
| Versión del producto |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    Identificador del evento     |                                                                                                       10676                                                                                                       |
|  Origen del evento   |                                                                                                      ENTSSO                                                                                                       |
|    Componente    |                                                                                                        N\D                                                                                                        |
|  Nombre simbólico  |                                                                                          SSO_ERROR_REQUIRE_OLD_PASSWORD                                                                                           |
|  Texto del mensaje   | Cambio de contraseña externa. Al cambiar la contraseña de una cuenta externa, el adaptador debe proporcionar la contraseña anterior.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta externa: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que el adaptador de sincronización de contraseñas se configuró para esperar una contraseña anterior del sistema externo, pero no se proporcionó tal contraseña. El sistema externo (el adaptador de sincronización de contraseñas externas) no está configurado o no funciona como se previó o bien, la configuración del adaptador de sincronización de contraseñas es incorrecta. Este error también puede devolver el código de error con nombre simbólico ENTSSO_E_REQUIRE_OLD_PASSWORD.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

-   Use las herramientas de administración de SSO para establecer la propiedad configurable de usuario **comprobar contraseña antigua** en la ficha de propiedades Opciones de adaptador de sincronización de contraseña. Esta propiedad también puede establecerse durante la creación de adaptadores a través de las herramientas de línea de comandos (ssops.exe) con el nombre de marcador `verifyOldPassword` y durante la creación de un nuevo adaptador de sincronización de contraseñas mediante el Asistente para adaptador de sincronización de contraseñas.  

## <a name="more-info"></a>Más información

- [Sincronización de contraseñas](../core/password-synchronization2.md)  

- **Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
