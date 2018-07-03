---
title: 'De sesión único: Evento 10743 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2908bc9-1fac-4ab9-869f-0c5512864da4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd0c8c170a17fade96daa0b9ecc0a3613afb1236
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003669"
---
# <a name="single-sign-on-event-10743"></a>De sesión único: Evento 10743
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                   Inicio de sesión único (SSO) empresarial                                                                    |
| Versión del producto |                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    Identificador del evento     |                                                                             10743                                                                              |
|  Origen del evento   |                                                                             ENTSSO                                                                             |
|    Componente    |                                                                              N\D                                                                               |
|  Nombre simbólico  |                                                                    SSO_ERROR_REPLAY_STOPPED                                                                    |
|  Texto del mensaje   | Se detuvo la reproducción de cambios de contraseña externa almacenados debido a errores.%r<br /><br /> Archivo de reproducción: %1 %r<br /><br /> Datos adicionales: %2 %r<br /><br /> Código de error: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que se detuvo la reproducción de cambios de contraseña externa almacenados debido a errores.  

 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.  

  Para obtener más información, vea los recursos siguientes:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
