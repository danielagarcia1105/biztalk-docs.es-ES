---
title: 'Inicio de sesión único: Evento 10851 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 582b92bf-2833-47cd-b685-1245e870d81d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdd719c77dc77fb626f97460ed92bd74ab6da812
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276548"
---
# <a name="single-sign-on-event-10851"></a>Inicio de sesión único: Evento 10851
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10851|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC|  
|Texto del mensaje|No se puede asignar la aplicación a un adaptador de sincronización de contraseñas porque tiene establecido el marcador "sincronización directa de contraseñas".|  
  
## <a name="explanation"></a>Explicación  
 Una aplicación no puede usar al mismo tiempo la sincronización directa de contraseñas y un adaptador de sincronización de contraseñas.  
  
## <a name="user-action"></a>Acción del usuario  
 Revise la aplicación y decida si debe o no tener sincronización directa de contraseñas. Si es así, deje el marcador establecido tal como está y no intente asignar la aplicación a un adaptador de sincronización de contraseñas. De lo contrario, desactive el marcador y asigne la aplicación a un adaptador de sincronización de contraseñas según corresponda.