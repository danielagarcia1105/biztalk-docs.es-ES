---
title: Lectura de Batchdescriptions desde la base de datos no se pudo | Microsoft Docs
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
ms.openlocfilehash: f7e539cbc4a8a7227815c7d836b61b028bcee2f5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990629"
---
# <a name="reading-batch-descriptions-from-database-failed"></a>Error en la lectura de BatchDescriptions desde la base de datos
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                 LoadBatchFiltersFailed                                 |
|  Texto del mensaje   |     Error en la lectura de BatchDescriptions desde la base de datos. Error: {0}. Seguimiento de la pila: {1}.      |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que BizTalk Server no pudo cargar los filtros especificados de los lotes configurados para comparar propiedades de contexto de mensajes entrantes.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que la base de datos de administración esté activa y sea posible conectarse a ella.