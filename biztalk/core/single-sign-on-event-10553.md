---
title: 'De sesión único: Evento 10553 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0da8faf-8127-4d2e-a2ef-e5af20aff34f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0103305692cfb978820cd94e9a42a3b384f5ba4d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013461"
---
# <a name="single-sign-on-event-10553"></a>De sesión único: Evento 10553
## <a name="details"></a>Detalles  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10553                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N/D                             |
|  Nombre simbólico  |           SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED           |
|  Texto del mensaje   |               Acceso denegado al servidor de administración.%r                |
  
## <a name="explanation"></a>Explicación  
 Un cliente llamó al servidor de administración pero no se aceptó la llamada. Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el cliente.  
  
## <a name="user-action"></a>Acción del usuario  
 Tome nota de la información incluida en el registro de eventos y póngase en contacto con los Servicios de soporte técnico de Microsoft.