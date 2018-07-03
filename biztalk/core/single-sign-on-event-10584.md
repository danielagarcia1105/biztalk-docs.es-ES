---
title: 'De sesión único: Evento 10584 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9377d-b4fd-48a6-961a-3629b3db644a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0188f09ab94bd14df0dbe3fee0b91341cd9eb087
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996725"
---
# <a name="single-sign-on-event-10584"></a>De sesión único: Evento 10584
## <a name="details"></a>Detalles  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  Nombre del producto   |                   Inicio de sesión único (SSO) empresarial                    |
| Versión del producto |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    Identificador del evento     |                             10584                              |
|  Origen del evento   |                             ENTSSO                             |
|    Componente    |                              N/D                               |
|  Nombre simbólico  |                   SSO_WARN_NO_IMPERSONATION                    |
|  Texto del mensaje   | No se pudo suplantar al cliente.%r<br /><br /> Código de error: %1 |
  
## <a name="explanation"></a>Explicación  
 El sistema ENTSSO no verifica la identidad del cliente durante su suplantación. Si el sistema no puede suplantar un cliente, puede deberse a una de las tres causas siguientes: el cliente puede estar intentando realizar una actividad habitual, el cliente puede estar intentando infiltrarse en la seguridad del sistema o la aplicación cliente pude estar diseñada para bloquear la suplantación.  
  
## <a name="user-action"></a>Acción del usuario  
 Busque la aplicación cliente, determine qué está intentando realizar y si está o no bloqueando la suplantación.