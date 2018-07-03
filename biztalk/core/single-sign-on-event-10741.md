---
title: 'De sesión único: Evento 10741 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58b6b093-d136-498f-a3b5-c413150da956
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1901ad4c58f3056b74f50fead72637bc9bb8b62e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006837"
---
# <a name="single-sign-on-event-10741"></a>De sesión único: Evento 10741
## <a name="details"></a>Detalles  

|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                 Inicio de sesión único (SSO) empresarial                                 |
| Versión del producto |                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    Identificador del evento     |                                           10741                                           |
|  Origen del evento   |                                          ENTSSO                                           |
|    Componente    |                                            N\D                                            |
|  Nombre simbólico  |                                SSO_WARN_SAVING_REPLAY_FILE                                |
|  Texto del mensaje   | Guardando archivo de reproducción o progreso.%r<br /><br /> Archivo guardado: %1 %r<br /><br /> Código de error: %2 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que SSO está guardando un archivo de reproducción o progreso.  

 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, vea los recursos siguientes:  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
