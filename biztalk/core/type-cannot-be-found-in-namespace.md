---
title: No se encuentra el tipo de espacio de nombres | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66387fa6-3ba3-499f-99d6-bb0033c68adc
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 515dd9b6b73b43bee22ffc7b67745bb45adcaf6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="type-cannot-be-found-in-namespace"></a>No se encuentra el tipo en el espacio de nombres
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Error: El tipo "{0}" no se encuentra en el espacio de nombres "{{1}"|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que los artefactos que se crean hacen referencias a tipos que no se encuentran en el espacio de nombres especificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Agregue una referencia que contenga el tipo que no se encuentra y vuelva a ejecutar el asistente (si es propietario del Servicio WCF que está intentando consumir). En caso contrario, póngase en contacto con el proveedor de servicios.