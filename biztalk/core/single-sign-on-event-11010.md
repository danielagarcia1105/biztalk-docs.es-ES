---
title: 'De sesión único: Evento 11010 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22fcd9f3-83bb-44b0-88fc-197c2ef3e72d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ba07dde6b32ebb2f5d92365fcead94c0b4ecc66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965821"
---
# <a name="single-sign-on-event-11010"></a>De sesión único: Evento 11010
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                Inicio de sesión único (SSO) empresarial                                                                                |
| Versión del producto |                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    Identificador del evento     |                                                                                          11010                                                                                          |
|  Origen del evento   |                                                                                         ENTSSO                                                                                          |
|    Componente    |                                                                                           N/D                                                                                           |
|  Nombre simbólico  |                                                                               SSO_WARN_NOT_SSO_AFF_ADMIN                                                                                |
|  Texto del mensaje   | El usuario del cliente no es miembro de la cuenta de administradores afiliados de SSO.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Usuario del cliente: %2\\%3 %r<br /><br /> Administradores afiliados de SSO: %4 |
  
## <a name="explanation"></a>Explicación  
 El usuario del cliente no es miembro de la cuenta de administradores afiliados de SSO. Esta advertencia sólo se muestra cuando los niveles de auditoría se establecen en Alto.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar el problema, debe incluir al usuario del cliente como miembro de la cuenta de administradores afiliados de SSO. Para que esta advertencia no vuelva a aparecer en el futuro, puede reducir los niveles de seguridad.