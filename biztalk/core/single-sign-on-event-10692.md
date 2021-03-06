---
title: 'De sesión único: Evento 10692 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78a476ca-32eb-4f37-a807-25850503db6e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37148a774504599b99665b57691316c35d0783bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987285"
---
# <a name="single-sign-on-event-10692"></a>De sesión único: Evento 10692
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                      Inicio de sesión único (SSO) empresarial                                                                                                                      |
| Versión del producto |                                                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                      |
|    Identificador del evento     |                                                                                                                                10692                                                                                                                                |
|  Origen del evento   |                                                                                                                               ENTSSO                                                                                                                                |
|    Componente    |                                                                                                                                 N\D                                                                                                                                 |
|  Nombre simbólico  |                                                                                                                    SSO_WARN_REPLAY_ACCESS_DENIED                                                                                                                    |
|  Texto del mensaje   | No se puede reproducir el cambio de contraseña externa porque el autor de la llamada original ya no es miembro de la cuenta de acceso del adaptador.%r<br /><br /> Archivo de reproducción: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> El llamador original: %3 %r<br /><br /> Obtener acceso a la cuenta: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo realizar el cambio (en la base de datos de SSO) especificado en el archivo de reproducción dado que la cuenta que originalmente especificaba tal cambio ya no es válida.  

 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  

- Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
