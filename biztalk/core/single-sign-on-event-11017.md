---
title: 'De sesión único: Evento 11017 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a4f7264-18aa-4eca-97c9-d5fd7e90e2cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e0883abfd3bc86f6e41fd11e0feafa79b080b13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024194"
---
# <a name="single-sign-on-event-11017"></a>De sesión único: Evento 11017
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                               Inicio de sesión único (SSO) empresarial                                                                                                                                |
| Versión del producto |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                               |
|    Identificador del evento     |                                                                                                                                         11017                                                                                                                                          |
|  Origen del evento   |                                                                                                                                         ENTSSO                                                                                                                                         |
|    Componente    |                                                                                                                                          N/D                                                                                                                                           |
|  Nombre simbólico  |                                                                                                                           SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK                                                                                                                           |
|  Texto del mensaje   | La asignación no es válida porque la cuenta de Windows no se encuentra en la cuenta de usuarios de aplicación de la aplicación. La asignación se ha eliminado.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Los usuarios de aplicación: %4 |
  
## <a name="explanation"></a>Explicación  
 La cuenta de Windows especificada nunca formó parte de la cuenta de usuarios de aplicación de esta aplicación o formó parte de ella en determinado momento, pero se la modificado o quitado. La asignación se ha eliminado.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe la información de la cuenta de sincronización de contraseñas del sistema y asegúrese de que sea válida. Posteriormente, vuelva a crear la asignación. Tenga en cuenta que el Asistente para creación de asignación reduce el riesgo de información de asignación no válida.