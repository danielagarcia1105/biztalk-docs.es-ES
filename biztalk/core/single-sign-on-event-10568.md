---
title: 'De sesión único: Evento 10568 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 266fd09a-c7e6-4a69-ac1c-1834097fa393
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c94c99580b63c5dc6eede29b595435daa256115
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010253"
---
# <a name="single-sign-on-event-10568"></a>De sesión único: Evento 10568
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                  Inicio de sesión único (SSO) empresarial                                                                                                  |
| Versión del producto |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                  |
|    Identificador del evento     |                                                                                                            10568                                                                                                            |
|  Origen del evento   |                                                                                                           ENTSSO                                                                                                            |
|    Componente    |                                                                                                             N/D                                                                                                             |
|  Nombre simbólico  |                                                                                              SSO_WARN_INVALID_APP_ADMIN_GROUP                                                                                               |
|  Texto del mensaje   | Cuenta de administradores de aplicación no válida para actualización de la aplicación.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Administradores de aplicación: %2 %r<br /><br /> Cuentas no válidas: %3 %r<br /><br /> Código de error: %4 |
  
## <a name="explanation"></a>Explicación  
 Ha intentado actualizar una cuenta de administradores de aplicación que no es válida o que no existe.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe si el nombre de la cuenta es correcto.