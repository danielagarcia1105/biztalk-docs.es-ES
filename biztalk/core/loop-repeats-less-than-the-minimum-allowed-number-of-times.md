---
title: Menor que el mínimo permitido de número de veces que un bucle se repite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0be21d1d-86da-456b-83e6-c91f1dc9fb48
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5457110830a2e38e592ff58e7da672373a139d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012317"
---
# <a name="loop-repeats-less-than-the-minimum-allowed-number-of-times"></a>El bucle se repite un número de veces inferior al mínimo permitido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                          X12SeLoopRepeatsLessTimesDescription                          |
|  Texto del mensaje   |               El bucle se repite un número de veces inferior al mínimo permitido.               |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía un bucle que se repetía menos veces que el número mínimo que requiere el esquema del mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el bucle se repite en el intercambio al menos el número de veces que indica la propiedad MinOccurs especificada para el bucle en el esquema del mensaje y vuelva a enviar el mensaje.