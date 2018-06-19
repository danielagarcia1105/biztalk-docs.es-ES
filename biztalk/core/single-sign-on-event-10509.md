---
title: 'Inicio de sesión único: Evento 10509 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f906823f-db3f-45fc-bf61-cbe6a9566bd7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4d61cbb7af195aa88c36b64149366334c835b80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270356"
---
# <a name="single-sign-on-event-10509"></a>Inicio de sesión único: Evento 10509
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10509|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_INFO_SERVICE_REMOVE_FAILED|  
|Texto del mensaje|No se pudo quitar el servicio SSO.%r<br /><br /> Código de error: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento indica que no se pudo desinstalar el servicio ENTSSO. Este evento sólo puede ocurrir durante la desinstalación manual de Inicio de sesión único empresarial.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar el evento, haga lo siguiente:  
  
-   Compruebe si en los registros de eventos del sistema y la aplicación existen errores relacionados de ENTSSO u otros servicios.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Instalación de SSO](../core/installing-sso.md)  
  
-   [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)