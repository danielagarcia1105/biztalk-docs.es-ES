---
title: Enviar errores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3cf61c82-ad48-4555-af53-fb841fd0f503
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67741af0520d990be9a552685c8319aa6a5ae881
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269820"
---
# <a name="send-errors"></a>Enviar errores
Información para diagnosticar y resolver errores de envío de WCF.  
  
## <a name="failed-to-generate-odx-file"></a>No se pudo generar el archivo ODX.

||Detalles del error|  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se pudo generar el archivo ODX.|  
  
### <a name="explanation"></a>Explicación  
 Este error indica que hay un error al consumir el servicio.  
  
### <a name="user-action"></a>Acción del usuario  
 Compruebe que el servicio tenga un método web válido y que estén hospedados los metadatos (si es propietario de los Servicios WCF). En caso contrario, póngase en contacto con el proveedor de servicios.  
  
 Para obtener información adicional sobre el consumo de servicios WCF, vea [consideraciones al consumir servicios WCF con los adaptadores de envío de WCF](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md).
 
## <a name="response-message-body-was-not-read"></a>No se puede leer el cuerpo del mensaje de respuesta
  
||Detalles del error|  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se pudo leer el cuerpo del mensaje de respuesta. (Esto puede indicar el cierre de la conexión.)|  
  
### <a name="explanation"></a>Explicación  
 Es posible que el cliente se haya desconectado antes de que se haya devuelto el mensaje de respuesta.  
  
### <a name="user-action"></a>Acción del usuario  
 Compurebe la conectividad del cliente. Los pasos tomados y la extensión de la acción dependerán del tipo de puerto.   
Para obtener más información, consulte [herramientas y utilidades que se usan para la solución de problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md).