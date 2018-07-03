---
title: 'De sesión único: Evento 10555 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9c663-4aa8-4ca5-be63-d4461a2a8517
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a44b3c72659cec8295e7a6625e7b6d94259283c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000309"
---
# <a name="single-sign-on-event-10555"></a>De sesión único: Evento 10555
## <a name="details"></a>Detalles  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10555                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N/D                             |
|  Nombre simbólico  |          SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED           |
|  Texto del mensaje   | Acceso denegado al servidor secreto.%r<br /><br /> Usuario cliente: %1 |
  
## <a name="explanation"></a>Explicación  
 Se envió un mensaje al servidor pero se bloqueó la respuesta. Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el servidor.  
  
## <a name="user-action"></a>Acción del usuario  
 Tome nota de la información incluida en el registro de eventos y póngase en contacto con los Servicios de soporte técnico de Microsoft.