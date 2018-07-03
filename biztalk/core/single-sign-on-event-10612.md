---
title: 'De sesión único: Evento 10612 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9d9e6f5-06b8-4989-a0dc-6e2e5980443b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fdc86dd2143bf8b2b4c27dab66cc4c06ddff5ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973021"
---
# <a name="single-sign-on-event-10612"></a>De sesión único: Evento 10612
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                            Inicio de sesión único (SSO) empresarial                                                                                                                            |
| Versión del producto |                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    Identificador del evento     |                                                                                                                                      10612                                                                                                                                      |
|  Origen del evento   |                                                                                                                                     ENTSSO                                                                                                                                      |
|    Componente    |                                                                                                                                       N/D                                                                                                                                       |
|  Nombre simbólico  |                                                                                                                          SSO_WARN_TRANSACTION_TIMEOUT                                                                                                                           |
|  Texto del mensaje   | El tiempo de espera de transacción supera el máximo recomendado para la operación. Consulte la documentación de details.%r<br /><br /> Id. de transacción: %1 %r<br /><br /> Tiempo de espera de transacción: minutos %2 (cero indica un tiempo de espera infinito) %r<br /><br /> Máximo recomendado: %3 minutos |
  
## <a name="explanation"></a>Explicación  
 El sistema recibió una transacción con un valor de tiempo de espera extremadamente grande. Si el sistema ENTSSO sondea la base de datos de SSO mientras está bloqueada por una transacción de larga duración, el sistema finalmente se desconectará.  
  
## <a name="user-action"></a>Acción del usuario  
 No se requiere ninguna acción del usuario.