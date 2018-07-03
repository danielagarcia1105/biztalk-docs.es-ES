---
title: 'De sesión único: Evento 10724 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 022a6f73-a24b-4058-91a5-b831f6875409
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b53fcdeaaadefbbb90738c9e8d4e2c0d234e338b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986173"
---
# <a name="single-sign-on-event-10724"></a>De sesión único: Evento 10724
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                     Inicio de sesión único (SSO) empresarial                                                                                      |
| Versión del producto |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    Identificador del evento     |                                                                                               10724                                                                                                |
|  Origen del evento   |                                                                                               ENTSSO                                                                                               |
|    Componente    |                                                                                                N\D                                                                                                 |
|  Nombre simbólico  |                                                                                    SSO_ERROR_REPLAY_SECURITY_2                                                                                     |
|  Texto del mensaje   | Se cambiaron los valores originales de seguridad en el archivo de reproducción o progreso.%r<br /><br /> Nombre de archivo: %1 %r<br /><br /> Seguridad del archivo actual: %2 %r<br /><br /> Seguridad del archivo original: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que se cambió la seguridad en el archivo de reproducción o progreso.  

 Los archivos de reproducción se almacenan en el directorio de archivos de reproducción. De forma predeterminada, la cuenta de servicio SSO se usa para crear tanto archivos de reproducción como el directorio de archivos de reproducción. SSO verifica que no se hayan realizado cambios en la configuración de seguridad de los archivos de reproducción y del directorio de archivos de reproducción desde su creación. Si el directorio de archivos de reproducción se creó con una cuenta diferente, puede aparecer este error cuando la sincronización de contraseñas intenta crear un archivo de reproducción en ese directorio. Se recomienda que los usuarios no cambien la configuración de seguridad de los archivos de reproducción ni del directorio de archivos de reproducción.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe los permisos de la cuenta que se usa para crear archivos de reproducción. Normalmente, dicha cuenta es la cuenta de sistema SSO.  

  Para obtener más información, vea los recursos siguientes:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
