---
title: 'Inicio de sesión único: Evento 11040 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6ccdc06-9677-4454-ae2c-8dde78d6f3f8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9eafbbe1c0cbcb0db96c94d072ed511e69b2d6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276916"
---
# <a name="single-sign-on-event-11040"></a>Inicio de sesión único: Evento 11040
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11040|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_NETWORK_SERVICE|  
|Texto del mensaje|El servicio SSO se está ejecutando en una cuenta de servicio de red. Existen algunas consideraciones especiales para esta cuenta. Para obtener información detallada, consulte la documentación.%r|  
  
## <a name="explanation"></a>Explicación  
 El servicio SSO se está ejecutando en una cuenta de servicio de red. Existen algunas consideraciones especiales para esta cuenta. Por ejemplo, se debe reiniciar el equipo después de agregar una cuenta de servicio de red. Además, la ejecución en una cuenta de servicio de red restringe la ejecución a escenarios muy limitados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para obtener más información, consulte [recomendaciones de seguridad de SSO](../core/sso-security-recommendations.md).