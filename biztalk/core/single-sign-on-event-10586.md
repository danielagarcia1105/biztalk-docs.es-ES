---
title: 'De sesión único: Evento 10586 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7d480e9-dc34-44ac-9272-0caf80237bd9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b353c5d9fb569da7bcc35927e31ce5c3e68ae11
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978881"
---
# <a name="single-sign-on-event-10586"></a>De sesión único: Evento 10586
## <a name="details"></a>Detalles  
  
|                 |                                                             |
|-----------------|-------------------------------------------------------------|
|  Nombre del producto   |                  Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]  |
|    Identificador del evento     |                            10586                            |
|  Origen del evento   |                           ENTSSO                            |
|    Componente    |                             N/D                             |
|  Nombre simbólico  |                   SSO_WARN_CRED_CACHE_OFF                   |
|  Texto del mensaje   | La memoria caché de credenciales se deshabilitó para este servidor de SSO. |
  
## <a name="explanation"></a>Explicación  
 Se deshabilitó la memoria caché de credenciales que, por lo general, está habilitada. Sólo el administrador del sistema puede habilitar o deshabilitar la memoria caché de credenciales. En ciertos casos, si se deshabilita esta memoria, hay más credenciales actuales del sistema ENTSSO, aunque esto podría disminuir el rendimiento.  
  
## <a name="user-action"></a>Acción del usuario  
 Para volver a habilitar la caché de credenciales, vea la tabla de propiedades de aplicaciones afiliadas en [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).