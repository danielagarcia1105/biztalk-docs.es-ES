---
title: "Inicio de sesión único: Evento 11019 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ec07b00-d567-4518-89eb-340e4f92429b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb4b2d2494a404566c7350a9e9988d429a3e335c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11019"></a>Inicio de sesión único: Evento 11019
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11019|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_PS_WARN_NOT_IN_GROUP_DELETE_FAILED|  
|Texto del mensaje|La asignación no es válida porque la cuenta de Windows no se encuentra en la cuenta de usuarios de aplicación de la aplicación. No se puedo eliminar la asignación. Se ignorará la asignación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Usuarios de aplicación: %4 %r<br /><br /> Código de error: %5|  
  
## <a name="explanation"></a>Explicación  
 La cuenta de Windows especificada nunca formó parte de la cuenta de usuarios de aplicación de esta aplicación o formó parte de ella en determinado momento, pero se la modificado o quitado. La asignación no se ha eliminado.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe la información de la cuenta de sincronización de contraseñas del sistema y asegúrese de que sea válida. Posteriormente, vuelva a crear la asignación. Tenga en cuenta que el Asistente para creación de asignación reduce el riesgo de información de asignación no válida. Puede eliminar la asignación con error. Si no la elimina, se ignorará.