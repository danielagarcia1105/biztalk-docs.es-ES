---
title: "Inicio de sesión único: Evento 10599 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd671aa5-b243-4081-9a4e-87103be9a1d7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d82ef4062f586ca82bf7e797dae44d6add8f7c68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10599"></a>Inicio de sesión único: Evento 10599
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10599|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_ENTSSO_IS_ADMIN|  
|Texto del mensaje|El servicio SSO se está ejecutando en una cuenta de administrador local. Por motivos de seguridad, esta práctica no es recomendable. Consulte la documentación de details.%r<br /><br /> Cuenta de servicio SSO: %1|  
  
## <a name="explanation"></a>Explicación  
 El servicio SSO especificado se está ejecutando en una cuenta de administrador local. Por motivos de seguridad, esta práctica no es recomendable.  
  
## <a name="user-action"></a>Acción del usuario  
 Para obtener más información, consulte [recomendaciones de seguridad de SSO](../core/sso-security-recommendations.md).