---
title: Durante la serialización nodo raíz no se coloca en el elemento de inicio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ea4aa6f-0f9c-4b7b-b7f6-24a5ce954048
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce91021f966ac1179a5137373df09fe7f3c4cece
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978421"
---
# <a name="during-serialization-root-node-is-not-placed-at-start-element"></a>Durante la serialización, el nodo raíz no se coloca en el elemento de inicio.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |             Durante la serialización, el nodo raíz no se coloca en el elemento de inicio.              |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar un intercambio entrante porque el conjunto de transacciones no comienza con un encabezado ST o UNH.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que cada uno de los conjuntos de transacciones de un intercambio comienza por un segmento ST (para intercambios X12) o por un segmento UNH (para intercambios EDIFACT) y vuelva a enviar el intercambio.