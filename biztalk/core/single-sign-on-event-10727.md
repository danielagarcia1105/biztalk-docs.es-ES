---
title: 'Inicio de sesión único: Evento 10727 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ff7ac94-6f1e-4e56-853e-efc50b1fa1b6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ceadb1bc742a11e05e54757b44618020c93b0d04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270892"
---
# <a name="single-sign-on-event-10727"></a>Inicio de sesión único: Evento 10727
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10727|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_REPLAY_RECORD_FAILED|  
|Texto del mensaje|Error al reproducir el cambio de contraseña externa almacenado.%r<br /><br /> Adaptador: %1 %r<br /><br /> Nombre de archivo: %2 %r<br /><br /> Código de error: %3|  
  
## <a name="explanation"></a>Explicación  
 Esta advertencia indica que SSO no pudo reproducir el cambio de contraseña registrado en el archivo de reproducción.  
  
 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  
  
-   Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Cómo configurar la sincronización de contraseña](../core/how-to-configure-password-synchronization.md)  
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)