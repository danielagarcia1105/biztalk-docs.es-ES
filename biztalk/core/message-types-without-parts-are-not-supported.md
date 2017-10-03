---
title: Tipos de mensajes sin partes no se admiten | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0bfb042-feda-4282-a7fa-c13be4ff6254
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e3e6cc0f5d4a2ae18ff6bcb5fa0dc8ef605d730
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-types-without-parts-are-not-supported"></a>No se admiten los tipos de mensajes sin partes
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se admiten los tipos de mensajes sin partes. Corrija el tipo de mensaje de descripción "{0}" servicio "{{1}" y vuelva a ejecutar al asistente.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que el servicio que se intenta consumir no tiene un tipo de mensaje definido.  
  
## <a name="user-action"></a>Acción del usuario  
 Corrija el servicio con el tipo de mensaje adecuado e intente consumirlo (si es propietario de los Servicios WCF que intenta consumir). De lo contrario, póngase en contacto con el proveedor de servicio.  Para obtener información adicional sobre los mensajes, vea el siguiente recurso en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ayuda:  
  
-   [Construcción de mensajes Web](../core/constructing-web-messages.md)