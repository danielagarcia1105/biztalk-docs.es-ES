---
title: 'De sesión único: Evento 11040 | Microsoft Docs'
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
ms.openlocfilehash: eefc6c65e07b430851606ce7779aad3771776a83
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019074"
---
# <a name="single-sign-on-event-11040"></a>De sesión único: Evento 11040
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                  Inicio de sesión único (SSO) empresarial                                                                  |
| Versión del producto |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    Identificador del evento     |                                                                            11040                                                                            |
|  Origen del evento   |                                                                           ENTSSO                                                                            |
|    Componente    |                                                                             N/D                                                                             |
|  Nombre simbólico  |                                                                  SSO_WARN_NETWORK_SERVICE                                                                   |
|  Texto del mensaje   | El servicio SSO se está ejecutando en una cuenta de servicio de red. Existen algunas consideraciones especiales para esta cuenta. Para obtener información detallada, consulte la documentación.%r |
  
## <a name="explanation"></a>Explicación  
 El servicio SSO se está ejecutando en una cuenta de servicio de red. Existen algunas consideraciones especiales para esta cuenta. Por ejemplo, se debe reiniciar el equipo después de agregar una cuenta de servicio de red. Además, la ejecución en una cuenta de servicio de red restringe la ejecución a escenarios muy limitados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para obtener más información, consulte [recomendaciones de seguridad de inicio de sesión único](../core/sso-security-recommendations.md).