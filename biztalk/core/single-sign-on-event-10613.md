---
title: 'De sesión único: Evento 10613 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a87ca19-24a0-4cf8-984f-2f70d7b5018c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 250f113e0cd60b417cee29d32f8e61fbf38632dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023810"
---
# <a name="single-sign-on-event-10613"></a>De sesión único: Evento 10613
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                   Inicio de sesión único (SSO) empresarial                                                    |
| Versión del producto |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    Identificador del evento     |                                                             10613                                                              |
|  Origen del evento   |                                                             ENTSSO                                                             |
|    Componente    |                                                              N/D                                                               |
|  Nombre simbólico  |                                                     SSO_ERROR_RPC_CALLBACK                                                     |
|  Texto del mensaje   | Acceso denegado al servidor de SSO.%r<br /><br /> Usuario cliente: %1 %r<br /><br /> Información de llamada RPC: %2: %3 %r<br /><br /> Código de error: %4 |
  
## <a name="explanation"></a>Explicación  
 Un cliente llamó al servidor de SSO pero no se aceptó la llamada. Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el cliente.  
  
## <a name="user-action"></a>Acción del usuario  
 Tenga en cuenta la información de este mensaje y cualquier información relevante en el registro de eventos y póngase en contacto con soporte técnico de Microsoft.