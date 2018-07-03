---
title: 'De sesión único: Evento 10614 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1f9cd21-3f4b-446f-a4c7-15266973adf1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba6cae7c64b5eeff339499f279aa85917211cbba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968173"
---
# <a name="single-sign-on-event-10614"></a>De sesión único: Evento 10614
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                        Inicio de sesión único (SSO) empresarial                                                                                                        |
| Versión del producto |                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                        |
|    Identificador del evento     |                                                                                                                  10614                                                                                                                  |
|  Origen del evento   |                                                                                                                 ENTSSO                                                                                                                  |
|    Componente    |                                                                                                                   N/D                                                                                                                   |
|  Nombre simbólico  |                                                                                                     SSO_WARN_INVALID_TICKET_TIMEOUT                                                                                                     |
|  Texto del mensaje   | Valor de tiempo de espera de vale no válido para actualización de información global.%r<br /><br /> Tiempo de espera de vale: %1 minutos %r<br /><br /> Tiempo de espera mínimo de vale: %r de 1 minuto<br /><br /> Tiempo de espera máximo de vale: %2 minutos %r<br /><br /> Código de error: %3 |
  
## <a name="explanation"></a>Explicación  
 El valor de tiempo de espera de vale especificado no es válido.  
  
## <a name="user-action"></a>Acción del usuario  
 Use la información proporcionada en el mensaje de advertencia para corregir el valor.