---
title: "Inicio de sesión único: Evento 10522 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd634a57-01dc-44bd-bcf9-668689db7b77
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b56999d7898af01d0009a7722d78aed0dbf5dbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10522"></a>Inicio de sesión único: Evento 10522
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10522|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_REENCRYPT|  
|Texto del mensaje|Error al volver a cifrar la base de datos de SSO. Vuelva a intentarlo en %1 minutos.%r<br /><br /> Código de error: %2|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que se produjo un error al volver a cifrar la base de datos de SSO. Cuando el servicio SSO se inicia en el servidor secreto principal, lo primero que hace es comprobar si la base de datos de SSO aún contiene información cifrada con el secreto principal anterior. Si es así, descifra esa información (mediante el secreto anterior) y vuelva a cifrarla mediante el secreto principal actual. Si, por cualquier motivo, el proceso genera un error, se emite este mensaje de evento.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
-   Compruebe el código de error para determinar la causa del error. Podría ser un problema de red o base de datos. Si se trata de un problema intermitente, no es necesario realizar ninguna acción porque se volverá a intentar el recifrado tras un breve retardo. De lo contrario, detenga el servicio SSO e intente solucionar el problema. Una vez resuelto el problema, reinicie el servicio SSO, ya que el reinicio realizará el recifrado de forma automática.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo mostrar la información de la base de datos SSO](../core/how-to-display-the-sso-database-information.md)  
  
-   [Servidor secreto principal](../core/master-secret-server.md)