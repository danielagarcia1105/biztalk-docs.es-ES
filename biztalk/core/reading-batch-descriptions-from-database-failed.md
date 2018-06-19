---
title: Lectura de Batchdescriptions desde la base de datos no se pudo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f959aa35-d957-45b0-bfac-1134b5087d0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66a9049c9f3964b231d7c1370784bccd78fd0836
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268660"
---
# <a name="reading-batch-descriptions-from-database-failed"></a>Error en la lectura de BatchDescriptions desde la base de datos
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|LoadBatchFiltersFailed|  
|Texto del mensaje|Error en la lectura de BatchDescriptions desde la base de datos. Error: {0}. Seguimiento de pila: {1}.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que BizTalk Server no pudo cargar los filtros especificados de los lotes configurados para comparar propiedades de contexto de mensajes entrantes.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que la base de datos de administración esté activa y sea posible conectarse a ella.