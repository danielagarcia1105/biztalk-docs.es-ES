---
title: No se puede serializar el mensaje por lotes porque no hay ninguna entidad asociada con el puerto de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d697ff9c-a6d1-4a3c-9ec3-4cd496f7eec2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b20d10a2c7b584eccc7d1fb57e5132a4ac0d608
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241484"
---
# <a name="batch-message-cannot-be-serialized-as-there-is-no-party-associated-with-send-port"></a>El mensaje de procesamiento por lotes no puede serializarse puesto que no existe ninguna entidad asociada al puerto de envío
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor de procesamiento por lotes|  
|Nombre simbólico|BatchMessageSerializationFailureDueToMissingParty|  
|Texto del mensaje|El mensaje de procesamiento por lotes no puede serializarse puesto que no existe ninguna entidad asociada al puerto de envío {0}. Asegúrese de que hay una entidad asociada al puerto.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar un intercambio conservado porque no pudo determinar la entidad a la que debe enviarse el mensaje. No pudo determinar la entidad porque no se configuró la propiedad de contexto de DestinationPartyName. Como resultado, la canalización de envío no pudo determinar la configuración de sobre.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pase el mensaje por una canalización de envío de atravesar y, a continuación, determine la propiedad de contexto DestinationPartyName para el mensaje. Compruebe que existe la entidad. Si no existe, créela y vuelva a enviar el mensaje.