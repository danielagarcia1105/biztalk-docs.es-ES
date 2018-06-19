---
title: 'Inicio de sesión único: Evento 10749 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10986736-77c0-42a7-b2bb-cd20f9f75fa6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 864c887cb6c115a2f766f9c06cbaa292fdbeace2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278460"
---
# <a name="single-sign-on-event-10749"></a>Inicio de sesión único: Evento 10749
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10749|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_PS_CLIENT_PING|  
|Texto del mensaje|No se pudo establecer la conexión con el servidor de SSO de destino.<br /><br /> Compruebe si el servicio SSO está en ejecución en ese servidor y si se puede establecer la conexión con éste.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Nombre del servidor SSO: %3 %r<br /><br /> Código de error: %4|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que la sincronización de contraseñas de SSO no pudo establecer la comunicación con el servidor de SSO de destino.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Use el complemento de servidores de ENTSSO para comprobar el servidor.  
  
-   Inicie el servicio de inicio de sesión único empresarial si no está en ejecución.  
  
-   Compruebe la conexión de red con el servidor de SSO de destino.  
  
-   Compruebe el firewall en el servidor de SSO de destino.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Cómo usar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md)