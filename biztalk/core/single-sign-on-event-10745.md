---
title: 'Inicio de sesión único: Evento 10745 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed630e40-d876-4e90-937e-4d2d54fe9f1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fe734562b9d8b3564a08f3f5196d53996bf40ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270828"
---
# <a name="single-sign-on-event-10745"></a>Inicio de sesión único: Evento 10745
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10745|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_ADAPTER_OFFLINE|  
|Texto del mensaje|Adaptador desconectado.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Mensaje de error: %3 %r<br /><br /> Código de error: %4|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que el adaptador especificado está desconectado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
-   Compruebe si en los registros de eventos del sistema y la aplicación existen errores asociados.  
  
-   Compruebe si el adaptador externo presenta errores.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)