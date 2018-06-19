---
title: 'Inicio de sesión único: Evento 10543 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46b1ffda-a6c1-408c-acb4-074183d697bc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9bf30640bf61f9c88de3fedbb5727be7a715aa8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270004"
---
# <a name="single-sign-on-event-10543"></a>Inicio de sesión único: Evento 10543
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10543|  
|Origen del evento|ENTSSO|  
|Componente|CO|  
|Nombre simbólico|SSO_WARN_ORIGINAL_TICKET_VALIDATED|  
|Texto del mensaje|El vale se emitió con validación obligatoria. Si no se valida, no puede canjearse para esta aplicación.%r<br /><br /> Nombre de la aplicación: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que se emitió un vale de aplicación con validación obligatoria. Los vales no se pueden canjear si no se validan. La validación de vales se realiza según la aplicación afiliada.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  
  
-   Si usa el inicio de sesión único empresarial, asegúrese de que los mensajes se envíen solamente a través de hosts de confianza. De este modo, disminuirá el riesgo de alteración de datos en el mensaje.  
  
-   Si el escenario lo permite, desactive la validación para esta aplicación. La validación es una opción administrativa que se puede desactivar tanto para el sistema como para esta aplicación específica solamente.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Vales de SSO](../core/sso-tickets.md)  
  
-   [Cómo mostrar las propiedades de una aplicación afiliada](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [Cómo actualizar las propiedades de una aplicación afiliada](../core/how-to-update-the-properties-of-an-affiliate-application.md)