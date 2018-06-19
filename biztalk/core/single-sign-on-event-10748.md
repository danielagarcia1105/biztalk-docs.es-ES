---
title: 'Inicio de sesión único: Evento 10748 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4b18ea-6565-4c0b-89f8-30a8c67601ba
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d83f0bfec0137e0788b55ca6aa5857f3dcfcc50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276508"
---
# <a name="single-sign-on-event-10748"></a>Inicio de sesión único: Evento 10748
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10748|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_PS_ADAPTER_NOT_RUNNING|  
|Texto del mensaje|No se pudo establecer la comunicación con el adaptador de destino.<br /><br /> Es posible que no esté en ejecución o que no se haya inicializado.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Nombre del servidor SSO: %3 %r<br /><br /> Código de error: %4|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que la sincronización de contraseñas no pudo comunicarse con el adaptador de sincronización de contraseñas especificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Compruebe el adaptador externo.  
  
-   Use las herramientas del complemento MMC o de la línea de comandos para habilitar el adaptador.  
  
-   Compruebe si en los registros de eventos del sistema y la aplicación existen errores asociados.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)