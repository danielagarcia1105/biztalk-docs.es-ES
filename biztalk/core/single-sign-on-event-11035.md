---
title: 'De sesión único: Evento 11035 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d551083c-a897-4a76-a40c-2254d3a3e52e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 194d3069f0b74022e6b16a28de1c7f81ae3030f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001725"
---
# <a name="single-sign-on-event-11035"></a>De sesión único: Evento 11035
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                               Inicio de sesión único (SSO) empresarial                                                                                                                                                |
| Versión del producto |                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                               |
|    Identificador del evento     |                                                                                                                                                         11035                                                                                                                                                          |
|  Origen del evento   |                                                                                                                                                         ENTSSO                                                                                                                                                         |
|    Componente    |                                                                                                                                                          N/D                                                                                                                                                           |
|  Nombre simbólico  |                                                                                                                                           SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER                                                                                                                                            |
|  Texto del mensaje   | Cambio de contraseña de Windows. Se detectó una asignación para esta cuenta de Windows pero se la ignoró porque la sincronización de contraseñas no está configurada para la aplicación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Aplicación: %3 %r<br /><br /> Cuenta externa: %4 %r<br /><br /> Usuario cliente: %5 |
  
## <a name="explanation"></a>Explicación  
 Se detectó una asignación para esta cuenta de Windows pero se la ignoró porque la sincronización de contraseñas no está configurada para la aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 Para obtener información sobre cómo configurar la sincronización de contraseñas, consulte [la sincronización de contraseña](../core/password-synchronization2.md).