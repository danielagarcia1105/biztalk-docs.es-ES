---
title: "Inicio de sesión único: Evento 10550 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73d63bc5-1e60-426c-a0d6-55c51dbb8d76
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9772885746f2c0519cba84db9ad1bee612607117
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10550"></a>Inicio de sesión único: Evento 10550
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10550|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_ERROR_SERVICE_NOT_SSO_ADMIN|  
|Texto del mensaje|El servicio SSO no pudo iniciarse porque la cuenta de servicio en la que se está ejecutando no es miembro de la cuenta de administradores de SSO.%r<br /><br /> Administradores de SSO: %1 %r<br /><br /> Cuenta de servicio SSO: %2|  
  
## <a name="explanation"></a>Explicación  
 El servicio SSO debe ejecutarse en una cuenta de servicio que sea miembro de la cuenta de administradores de SSO.  
  
## <a name="user-action"></a>Acción del usuario  
 Para obtener más información, consulte [cómo especificar administradores de SSO y cuentas de administradores afiliados](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md).