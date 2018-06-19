---
title: 'Inicio de sesión único: Evento 11068 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f09a1191-ae67-4156-a8a5-d24e4439fc68
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be824a9205d81aaaeb9fd87129133b94b4f2e379
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277812"
---
# <a name="single-sign-on-event-11068"></a>Inicio de sesión único: Evento 11068
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11068|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE|  
|Texto del mensaje|Acceso denegado al servidor de búsqueda. Este servidor de SSO actualmente no está configurado para permitir búsqueda remota. Use 'ssoconfig -remoteLookup yes' o la MMC de administración de SSO.%r|  
  
## <a name="explanation"></a>Explicación  
 Se denegó el acceso al servidor de búsqueda porque el servidor de ENTSSO no está configurado para permitir búsqueda remota.  
  
## <a name="user-action"></a>Acción del usuario  
 Para permitir búsqueda remota, en la **complemento de servidores**, **avanzadas** ficha, seleccione **Permitir búsqueda remota**.  
  
 Para obtener más información, consulte [cómo utilizar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md).