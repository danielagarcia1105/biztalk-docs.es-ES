---
title: 'Inicio de sesión único: Evento 10611 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4549ac01-b828-478f-aea0-862e14fac149
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3582ee070b960b7eb17facc8d48e0b3e11dc5b9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270420"
---
# <a name="single-sign-on-event-10611"></a>Inicio de sesión único: Evento 10611
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10611|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_INFO_SERVICE_STARTING_NO_SSL|  
|Texto del mensaje|Se está iniciando el servicio SSO.%r<br /><br /> Nombre de equipo: %1 %r<br /><br /> Nombre SQL Server: %2 %r<br /><br /> Nombre de la base de datos SSO: %3 %r<br /><br /> No se usa SSL. Consulte la documentación para obtener información detallada sobre el procedimiento para proteger la conexión con SQL Server.|  
  
## <a name="explanation"></a>Explicación  
 El servicio ENTSSO se está iniciando sin usar la Capa de sockets seguros (SSL). Se recomienda proteger la conexión entre el servicio SSO y SQL.  
  
## <a name="user-action"></a>Acción del usuario  
 Consulte la documentación en [cómo habilitar SSL para SSO](../core/how-to-enable-ssl-for-sso.md)  
  
 .