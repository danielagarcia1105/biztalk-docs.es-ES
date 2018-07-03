---
title: 'De sesión único: Evento 10603 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139d1eb5-af88-4216-9604-c052f3db13c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5416ae8a2dcfdf5a3da6d8c1d00eb5a556fc3599
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970069"
---
# <a name="single-sign-on-event-10603"></a>De sesión único: Evento 10603
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                             Inicio de sesión único (SSO) empresarial                                                              |
| Versión del producto |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    Identificador del evento     |                                                                       10603                                                                        |
|  Origen del evento   |                                                                       ENTSSO                                                                       |
|    Componente    |                                                                        N/D                                                                         |
|  Nombre simbólico  |                                                                 SSO_WARN_DB_ACCESS                                                                 |
|  Texto del mensaje   | No se pudo obtener acceso a la base de datos de SSO. Si esta condición persiste, el servicio SSO se desconectará.%r<br /><br /> %1.%r<br /><br /> Código de Error SQL: %2 |
  
## <a name="explanation"></a>Explicación  
 La base de datos de SSO no está disponible.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe el código de error de SQL de la advertencia. Es posible que ésta ofrezca ayuda. De lo contrario, póngase en contacto con los Servicios de soporte técnico de Microsoft.