---
title: 'De sesión único: Evento 10817 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1668b81-e7f4-46d2-aebe-47007f70372b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e42873f0b56c43a7c997a2476ba2b15148d4639
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979197"
---
# <a name="single-sign-on-event-10817"></a>De sesión único: Evento 10817
## <a name="details"></a>Detalles  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10817                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N/D                             |
|  Nombre simbólico  |              ENTSSO_E_NOTIFICATION_NOT_FOUND               |
|  Texto del mensaje   |         No se encuentra la notificación especificada.          |
  
## <a name="explanation"></a>Explicación  
 El cambio de contraseña especificó un GUID de notificación que no se puede encontrar.  
  
## <a name="user-action"></a>Acción del usuario  
 Para determinar el GUID adecuado de la notificación, consulte la configuración del adaptador de sincronización de contraseñas.