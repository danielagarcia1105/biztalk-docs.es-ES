---
title: 'Inicio de sesión único: Evento 10542 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8e12444-b47c-4919-85b6-85c8e33b8342
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ebcf97a9de014d0651c9f239c1ae6e846925f3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271180"
---
# <a name="single-sign-on-event-10542"></a>Inicio de sesión único: Evento 10542
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10542|  
|Origen del evento|ENTSSO|  
|Componente|CO|  
|Nombre simbólico|SSO_WARN_APP_TICKETS_VALIDATED|  
|Texto del mensaje|Si no se validan, los vales no pueden canjearse para esta aplicación.%r<br /><br /> Nombre de la aplicación: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que los vales de aplicación no pueden canjearse si no se validan. Cuando se canjean vales de aplicación, pueden o no validarse. La validación mejora la seguridad al comparar el nombre del usuario que emitió el vale con el nombre del usuario que figura en el mensaje de BizTalk. Si los nombres no coinciden, se produce un error de validación. Cuando el mensaje de BizTalk se transmite a través de un host que no es de confianza, el nombre del usuario de este mensaje cambia al nombre del host que no es de confianza. La validación garantiza que el mensaje de BizTalk sólo se transmita a través de hosts de confianza. Este mensaje indica específicamente que es necesaria la validación en el nivel de sistema de aplicaciones (debido a la configuración de opciones del sistema SSO), pero que el usuario que llama no proporcionó la información de validación.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Si usa BizTalk Server, asegúrese de que los mensajes se envíen solamente a través de hosts de BizTalk de confianza. De este modo, disminuirá el riesgo de alteración de datos en el mensaje.  
  
-   Si el escenario lo permite, desactive la validación para esta aplicación. La validación es una opción administrativa que se puede desactivar tanto para el sistema como para esta aplicación específica solamente.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Vales de SSO](../core/sso-tickets.md)  
  
-   [Cómo mostrar las propiedades de una aplicación afiliada](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [Cómo actualizar las propiedades de una aplicación afiliada](../core/how-to-update-the-properties-of-an-affiliate-application.md)