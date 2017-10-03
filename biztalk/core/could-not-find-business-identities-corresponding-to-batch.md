---
title: No se pudo encontrar las identidades de negocio correspondientes al lote | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9baf11-e9c6-482d-a47d-aa99852939bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f1027186e5b001d21e08bbabcfc100400a02d5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="could-not-find-business-identities-corresponding-to-batch"></a>No encuentran las identidades de negocio correspondientes al lote
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|IdentitiesNotFoundForBatch|  
|Texto del mensaje|No encuentran las identidades de negocio correspondientes al lote {0}.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que el servidor BizTalk no pudo procesar un mensaje por lotes por no tener datos suficientes.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que esté presente un lote con el identificador dado en las propiedades del acuerdo contenedor y que estén especificadas las identidades empresariales adecuadas para el acuerdo.