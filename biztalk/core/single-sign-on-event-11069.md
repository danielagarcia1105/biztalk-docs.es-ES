---
title: 'De sesión único: Evento 11069 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1accfe68-000c-4b5e-909c-244e18eba110
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e9df27e7a5ac5f4fcedb10935fb8e63a6e0bea0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986165"
---
# <a name="single-sign-on-event-11069"></a>De sesión único: Evento 11069
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                               Inicio de sesión único (SSO) empresarial                                                                                               |
| Versión del producto |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    Identificador del evento     |                                                                                                         11069                                                                                                         |
|  Origen del evento   |                                                                                                        ENTSSO                                                                                                         |
|    Componente    |                                                                                                          N/D                                                                                                          |
|  Nombre simbólico  |                                                                                             SSO_WARN_PS_PCNS_NOT_ALLOWED                                                                                              |
|  Texto del mensaje   | Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde PCNS. Use 'ssoconfig -allowPS PCNS yes' o la MMC de administración de SSO.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Usuario cliente: %2 |
  
## <a name="explanation"></a>Explicación  
 Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde PCNS.  
  
## <a name="user-action"></a>Acción del usuario  
 Para permitir que los cambios de contraseña de Windows desde PCNS, en el **servidores complemento**, **propiedades de sincronización de contraseña** ficha, seleccione **Permitir sincronización de contraseñas desde PCNS.**  
  
 Para obtener más información, consulte [cómo usar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md).