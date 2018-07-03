---
title: El bucle contiene un nodo de hoja. Solo puede contener otros bucles o segmentos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0ee5e6-519d-4c95-8681-de5a37741d56
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8d88e0fb114255d19310eefb87e00c820b17420
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014237"
---
# <a name="the-loop-contains-a-leaf-node-it-can-only-contain-other-loops-or-segments"></a>El bucle contiene un nodo de hoja. Sólo puede contener otros bucles o segmentos.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                           SchemaCode125ELoopContainsLeafNode                           |
|  Texto del mensaje   |       El bucle contiene un nodo de hoja. Sólo puede contener otros bucles o segmentos.       |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante debido a que el intercambio no se ajustaba al esquema del documento. En este caso, un bucle contenía un nodo hoja sin hijos, mientras que el esquema especificada que el bucle solo podía contener otros bucles o segmentos.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del conjunto de transacciones que corrija el bucle de modo que no contenga nodos de hoja y vuelva a enviar el intercambio.