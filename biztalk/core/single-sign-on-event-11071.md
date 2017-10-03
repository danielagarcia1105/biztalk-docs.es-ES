---
title: "Inicio de sesión único: Evento 11071 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c0f61b9-cd86-482b-a8fe-0093a928c89b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e744e4f477ee45e6f634e8e4b2ca976754cbecf1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11071"></a>Inicio de sesión único: Evento 11071
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11071|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH|  
|Texto del mensaje|Se descartó el cambio de contraseña de Windows dado que su longitud es de cero caracteres.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Usuario cliente: %3|  
  
## <a name="explanation"></a>Explicación  
 Se descartó el cambio de contraseña de Windows dado que su longitud es de cero caracteres. Se proporcionan la cuenta de Windows y el nombre de cuenta.  
  
## <a name="user-action"></a>Acción del usuario  
 Vuelva a cambiar la contraseña con el número y el tipo de caracteres requeridos por el sistema SSO.