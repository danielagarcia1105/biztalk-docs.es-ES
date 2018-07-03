---
title: 'De sesión único: Evento 10697 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4263ecbd-939e-4374-b0b6-aada3b2af900
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991d17351ddbaa998c0f7c90774e1615f3bc472e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980405"
---
# <a name="single-sign-on-event-10697"></a>De sesión único: Evento 10697
## <a name="details"></a>Detalles  

|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                           Inicio de sesión único (SSO) empresarial                                           |
| Versión del producto |                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                           |
|    Identificador del evento     |                                                     10697                                                     |
|  Origen del evento   |                                                    ENTSSO                                                     |
|    Componente    |                                                      N\D                                                      |
|  Nombre simbólico  |                                       SSO_ERROR_PROGRESS_FILE_MISMATCH                                        |
|  Texto del mensaje   | El archivo de progreso está dañado.%r<br /><br /> Archivo de reproducción: %1 %r<br /><br /> Datos adicionales: %2 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo abrir el archivo de progreso porque no coincide con el archivo de reproducción correspondiente. Si SSO no puede abrir un archivo de progreso, comenzará en el registro inicial del primero archivo de reproducción.  

 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
