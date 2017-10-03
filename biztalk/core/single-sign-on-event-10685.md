---
title: "Inicio de sesión único: Evento 10685 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 810b37b5-51c4-4201-8d88-0bf7d9e16dae
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47844a979e93789f4baa94fbcbd58fd23762db84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10685"></a>Inicio de sesión único: Evento 10685
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10685|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_REPLAY_CANNOT_OPEN|  
|Texto del mensaje|No se pudo abrir el archivo de reproducción o progreso.%r<br /><br /> Nombre de archivo: %1 %r<br /><br /> Código de error: %2|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo abrir el archivo de reproducción o progreso. Si SSO no puede abrir un archivo de reproducción, continúa con el próximo archivo de reproducción.  
  
 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO durante parte de la reproducción de un archivo de reproducción.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar el evento de advertencia, haga lo siguiente:  
  
-   Debe comprobar si los registros de eventos del sistema y de la aplicación presentan eventos asociados para determinar por qué SSO no pudo comunicarse con la base de datos de SSO.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo configurar la sincronización de contraseña](../core/how-to-configure-password-synchronization.md)  
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)