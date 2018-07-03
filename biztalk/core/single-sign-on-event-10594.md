---
title: 'De sesión único: Evento 10594 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f4c6041-39a8-49bc-b39e-66cb6eb2efae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba733d9a919b2af09824242a48a2fa85af8ab481
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004764"
---
# <a name="single-sign-on-event-10594"></a>De sesión único: Evento 10594
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                 Inicio de sesión único (SSO) empresarial                                                                                  |
| Versión del producto |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    Identificador del evento     |                                                                                           10594                                                                                            |
|  Origen del evento   |                                                                                           ENTSSO                                                                                           |
|    Componente    |                                                                                            N/D                                                                                             |
|  Nombre simbólico  |                                                                              SSO_WARN_TICKET_VALIDATE_FAILED                                                                               |
|  Texto del mensaje   | Error al validar el vale. El nombre del remitente debe coincidir con el emisor del vale.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Vale emitido por: %2 %r<br /><br /> Nombre del remitente: %3 |
  
## <a name="explanation"></a>Explicación  
 Para que se valide un vale, deben coincidir los campos Vale emitido por y Nombre del remitente (en el mensaje de advertencia). Sin embargo, si el mensaje se envía a través de un host de BizTalk que no es de confianza, el nombre del remitente cambia al nombre de este host y no se valida el vale.  
  
## <a name="user-action"></a>Acción del usuario  
 Si usa el inicio de sesión único empresarial, asegúrese de que los mensajes se envíen solamente a través de hosts de BizTalk de confianza. De este modo, disminuirá el riesgo de alteración de datos en el mensaje.  
  
 Si comprende plenamente las implicaciones de seguridad del escenario, puede desactivar la validación para esta aplicación. Tenga en cuenta que la validación es una opción administrativa que se puede desactivar tanto para el sistema como para esta aplicación específica solamente.