---
title: 'Error al procesar el mensaje Edifact en el puerto de envío: sin entidad con nombre | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 678baacb-1f21-4081-b788-ef346c3598ca
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6becad3fefaa8167c9cf1af051731aa08be0d80a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005157"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-party-with-name"></a>Error al procesar el mensaje Edifact en el puerto de envío: sin entidad con nombre
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de BizTalk Server|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|Error al procesar el mensaje Edifact en el puerto de envío {0}. No existe ninguna entidad con {1} del nombre.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo resolver la entidad para el intercambio EDIFACT porque BizTalk Server no pudo hacer coincidir el puerto de envío que se suscribió al intercambio con el puerto de envío asociado con una entidad. Esto se produce si no se promociona la propiedad DestinationPartyName ni las propiedades de calificador e identificador de remitente ni de calificador e identificador de receptor, por lo que no estarán disponibles para la resolución de la entidad del envío.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el puerto de envío que suscribió al intercambio coincide con el puerto de envío asociado con una entidad.