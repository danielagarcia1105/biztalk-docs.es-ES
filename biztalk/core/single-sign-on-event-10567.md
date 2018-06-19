---
title: 'Inicio de sesión único: Evento 10567 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f29c8d9-3da2-4de7-b61f-8c586382b68f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb6f57bed2f386363d3ae4d92b4e300061056826
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270036"
---
# <a name="single-sign-on-event-10567"></a>Inicio de sesión único: Evento 10567
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10567|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_INVALID_APP_USER_GROUP|  
|Texto del mensaje|Cuenta de usuarios de aplicación no válida para actualización de la aplicación.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Usuarios de aplicación: %2 %r<br /><br /> Cuentas no válidas: %3 %r<br /><br /> Código de error: %4|  
  
## <a name="explanation"></a>Explicación  
 Ha intentado actualizar una cuenta de usuarios de aplicación que no es válida o que no existe.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe si el nombre de la cuenta es correcto.