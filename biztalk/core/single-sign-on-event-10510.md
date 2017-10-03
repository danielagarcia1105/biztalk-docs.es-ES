---
title: "Inicio de sesión único: Evento 10510 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4553ad4c-9553-4b8b-b3a3-72aed2a61202
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 053f75541597e3b2e721c53714aaaf8517c3c49f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10510"></a>Inicio de sesión único: Evento 10510
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10510|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_INFO_DLL_LOAD_FAILED|  
|Texto del mensaje|No se pudo cargar %1. Compruebe que este archivo está disponible.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de información indica que el servicio SSO no pudo cargar la DLL.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar el evento, realice una o varias de las acciones siguientes:  
  
-   Compruebe si la DLL se encuentra en el directorio de instalación de SSO, normalmente C:\Archivos de programa\Archivos comunes\Inicio de sesión único empresarial. Es posible que el directorio de instalación de SSO sea diferente.  
  
-   Si la única DLL falta o está dañada, intente reemplazarla y, seguidamente, reinicie el servicio.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)