---
title: Menos repeticiones de las necesarias | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5bebc13-0e70-4f73-99c0-fed917d79fba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f0ca660f792494e66d3ad26ead90f8878d80a0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974893"
---
# <a name="repeats-less-than-required"></a>Menos repeticiones de las necesarias.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                        X12FeRepeatsLessThanRequiredDescription                         |
|  Texto del mensaje   |                               Menos repeticiones de las necesarias.                               |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que los segmentos de un intercambio X12 entrante que se encuentran dentro o fuera de un bucle se repiten menos veces que las que requiere el esquema del documento.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que los segmentos que se encuentran dentro o fuera de un bucle del intercambio se repiten el número de veces especificado en el esquema y reenvíe el intercambio.