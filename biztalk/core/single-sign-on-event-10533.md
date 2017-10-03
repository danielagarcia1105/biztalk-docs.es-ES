---
title: "Inicio de sesión único: Evento 10533 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31abd828-5f10-43f7-b99e-f3195250130c
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 661c2eb91e0b8886f200319e9595f9d25c7023f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10533"></a>Inicio de sesión único: Evento 10533
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10533|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_INFO_GOT_CURRENT_SECRET|  
|Texto del mensaje|Se obtuvo el secreto actual desde el servidor secreto principal.%r<br /><br /> Nombre del servidor secreto: %1 %r<br /><br /> MSID: %2|  
  
## <a name="explanation"></a>Explicación  
 Este evento de información indica que SSO cuenta con el secreto principal actual.  
  
## <a name="user-action"></a>Acción del usuario  
  
-   No es necesario que el usuario realice ninguna acción.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)  
  
-   [Administrar el secreto principal](../core/managing-the-master-secret.md)