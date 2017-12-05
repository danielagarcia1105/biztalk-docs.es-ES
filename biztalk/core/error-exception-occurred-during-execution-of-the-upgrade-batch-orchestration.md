---
title: "Se ha producido una excepción durante la ejecución de la orquestación de lote de actualización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2221a498-98aa-43ab-bc4e-34dcbd92dcf0
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0789853ba253d7d8e51c34a6c1d1ce64829f8d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-upgrade-batch-orchestration"></a>Se produjo una excepción durante la ejecución de la orquestación del lote de actualización
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de BizTalk Server|  
|Componente|Motor de procesamiento por lotes|  
|Nombre simbólico|ExceptionOccuredDuringUpgrade|  
|Texto del mensaje|Se produjo una excepción durante la ejecución de la orquestación del lote de actualización. Mensaje de error: {0}|  
  
## <a name="explanation"></a>Explicación  
 El evento de error,  indica que la orquestación del lote de actualización no pudo procesar correctamente el mensaje debido a la condición de error indicada en el campo Mensaje de error.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, determine cuál es la condición de error desde el campo Mensaje de error, resuelva el error y vuelva a enviar el mensaje.