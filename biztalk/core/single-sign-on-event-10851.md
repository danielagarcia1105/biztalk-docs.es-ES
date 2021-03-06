---
title: 'De sesión único: Evento 10851 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 582b92bf-2833-47cd-b685-1245e870d81d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15121c1d7829f04bd9c106ed71da391d401ae564
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987237"
---
# <a name="single-sign-on-event-10851"></a>De sesión único: Evento 10851
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                             Inicio de sesión único (SSO) empresarial                                             |
| Versión del producto |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    Identificador del evento     |                                                       10851                                                       |
|  Origen del evento   |                                                      ENTSSO                                                       |
|    Componente    |                                                        N/D                                                        |
|  Nombre simbólico  |                                     ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC                                      |
|  Texto del mensaje   | No se puede asignar la aplicación a un adaptador de sincronización de contraseñas porque tiene establecido el marcador "sincronización directa de contraseñas". |
  
## <a name="explanation"></a>Explicación  
 Una aplicación no puede usar al mismo tiempo la sincronización directa de contraseñas y un adaptador de sincronización de contraseñas.  
  
## <a name="user-action"></a>Acción del usuario  
 Revise la aplicación y decida si debe o no tener sincronización directa de contraseñas. Si es así, deje el marcador establecido tal como está y no intente asignar la aplicación a un adaptador de sincronización de contraseñas. De lo contrario, desactive el marcador y asigne la aplicación a un adaptador de sincronización de contraseñas según corresponda.