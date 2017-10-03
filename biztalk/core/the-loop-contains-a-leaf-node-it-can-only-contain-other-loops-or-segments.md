---
title: El bucle contiene un nodo de hoja. Solo puede contener otros bucles o segmentos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a0ee5e6-519d-4c95-8681-de5a37741d56
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d03349389fb108d434cce67afc5be13fd2a3d513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-loop-contains-a-leaf-node-it-can-only-contain-other-loops-or-segments"></a>El bucle contiene un nodo de hoja. Sólo puede contener otros bucles o segmentos.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|SchemaCode125ELoopContainsLeafNode|  
|Texto del mensaje|El bucle contiene un nodo de hoja. Sólo puede contener otros bucles o segmentos.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante debido a que el intercambio no se ajustaba al esquema del documento. En este caso, un bucle contenía un nodo hoja sin hijos, mientras que el esquema especificada que el bucle solo podía contener otros bucles o segmentos.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del conjunto de transacciones que corrija el bucle de modo que no contenga nodos de hoja y vuelva a enviar el intercambio.