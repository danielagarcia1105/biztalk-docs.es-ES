---
title: Elemento que falta parte de mensaje | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b519315f-d51d-4ca3-a0e6-d08bb920c6c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dd5a423a34d8b6ddf8f4689351b0f6dbcef53c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-part-missing-element"></a>Falta un elemento de parte de mensaje
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Falta un elemento de parte de mensaje. Corrija la parte "{{1}" "{{2}" del tipo de mensaje de descripción "{0}" servicio y vuelva a ejecutar el Asistente|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que el servicio que se intenta consumir no tiene la etiqueta de elemento que identifica el tipo de mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Corrija el servicio con el tipo de mensaje adecuado e intente consumirlo (si es propietario de los Servicios WCF que intenta consumir). En caso contrario, póngase en contacto con el proveedor de servicios.  
  
 Para obtener más información sobre mensajes, vea el recurso siguiente en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Construcción de mensajes Web](../core/constructing-web-messages.md)