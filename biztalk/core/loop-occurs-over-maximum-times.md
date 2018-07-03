---
title: Repetición de bucles superior al máximo permitido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ac9f5d3-04ec-4c40-8a1f-17ef0b143cda
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6587e5b5dcef641f37f24005fe594a084e5de12d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979605"
---
# <a name="loop-occurs-over-maximum-times"></a>Repetición de bucles superior al máximo permitido
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                        X12LoopOccursOverMaximumTimesDescription                        |
|  Texto del mensaje   |                            Repetición de bucles superior al máximo permitido.                             |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía un bucle que se repetía más veces que el número máximo que requiere el esquema del mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el bucle no se repita en el intercambio más del número de veces que indica la propiedad MaxOccurs especificada para el bucle en el esquema del mensaje y vuelva a enviar el mensaje.