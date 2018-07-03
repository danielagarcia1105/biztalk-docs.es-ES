---
title: 'De sesión único: Evento 10852 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9d6e5ff-95de-448a-8a4c-1f2d43ab57d4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2474b255e2577f60e0c37c4b25df00c7c4379db3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002245"
---
# <a name="single-sign-on-event-10852"></a>De sesión único: Evento 10852
## <a name="details"></a>Detalles  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                   Inicio de sesión único (SSO) empresarial                                   |
| Versión del producto |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    Identificador del evento     |                                             10852                                             |
|  Origen del evento   |                                            ENTSSO                                             |
|    Componente    |                                              N/D                                              |
|  Nombre simbólico  |                         ENTSSO_E_CREATE_FIELD_NO_DIRECT_PASSWORD_SYNC                         |
|  Texto del mensaje   | No se puede crear el campo porque la aplicación tiene establecido el marcador "sincronización directa de contraseñas". |
  
## <a name="explanation"></a>Explicación  
 Si una aplicación tiene establecido el marcador de sincronización directa de contraseñas, no se pueden crear campos.  
  
## <a name="user-action"></a>Acción del usuario  
 No existen acciones del usuario. Esta opción no se admite.