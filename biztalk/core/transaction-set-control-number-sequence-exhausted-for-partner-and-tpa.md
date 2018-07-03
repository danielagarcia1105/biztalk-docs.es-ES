---
title: Transaction set control secuencia numérica agotada para el socio y TPA | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f194ca-3e0f-4ad4-8bc8-88aa7e5193a7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c39815ccd013deea9ac4ef78426320e5c371feb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968517"
---
# <a name="transaction-set-control-number-sequence-exhausted-for-partner-and-tpa"></a>Secuencia de número de control del conjunto de transacciones agotada para el socio y TPA
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                           |
| Versión del producto |                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                       |
|    Identificador del evento     |                                                                                   -                                                                                    |
|  Origen del evento   |                                         EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                         |
|    Componente    |                                                                               Motor EDI                                                                               |
|  Nombre simbólico  |                                                                   EdiControlNumberExhaustedForParty                                                                    |
|  Texto del mensaje   | Transaction set control secuencia numérica agotada para el socio '{1}'para el TPA'{2}'. Restablezca la secuencia en {2} - propiedades de EDI mediante la administración de BizTalk Server. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo procesar el documento debido a que el intervalo de control del conjunto de transacciones se ha agotado para el acuerdo en {2}.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, active la casilla para restablecer el número de control del acuerdo {2}, aumente el intervalo de números de control o pulse el botón Restablecer contra la especificación del intervalo de números de control en el acuerdo.