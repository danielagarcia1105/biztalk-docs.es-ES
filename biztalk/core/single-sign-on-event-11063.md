---
title: 'De sesión único: Evento 11063 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c84f91de-221d-43c4-8d23-3d1b7fd29cf7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a653b8c5cf27925c65d8922a5a561855fdb6a4c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975573"
---
# <a name="single-sign-on-event-11063"></a>De sesión único: Evento 11063
## <a name="details"></a>Detalles  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           11063                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N/D                             |
|  Nombre simbólico  |          SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED          |
|  Texto del mensaje   |      Acceso denegado al servidor de sincronización de contraseñas (para MIIS).%r      |
  
## <a name="explanation"></a>Explicación  
 Se denegó el acceso a la devolución de llamada de MIIS. La causa más probable de este error es que no se pudo usar la autenticación Kerberos entre el sistema ENTSSO y MIIS.  
  
## <a name="user-action"></a>Acción del usuario  
 Confirme si el sistema ENTSSO usa la autenticación Kerberos. Para obtener más información, consulte [recomendaciones de seguridad de inicio de sesión único](../core/sso-security-recommendations.md).