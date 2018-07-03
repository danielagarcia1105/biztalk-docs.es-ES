---
title: Falta el finalizador del conjunto de transacciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07753300-fe47-47a6-a947-6abec10c1c90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b23ddf1905bc0067d5d35b625d4a66ec058028fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985133"
---
# <a name="transaction-set-trailer-missing"></a>Falta el finalizador del conjunto de transacciones.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                             X12TsTrailerMissingDescription                             |
|  Texto del mensaje   |                            Falta el finalizador del conjunto de transacciones.                             |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el conjunto de transacciones entrantes o que la canalización de envío no pudo procesar el conjunto de transacciones salientes porque el conjunto de transacciones no incluyó el finalizador del conjunto de transacciones SE (para conjuntos de transacciones X12) o el finalizador de mensaje UNT (para conjuntos de transacciones EDIFACT).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del conjunto de transacciones que agregue a este un finalizador del conjunto de transacciones SE (para conjuntos de transacciones X12) o el finalizador de mensaje UNT (para conjuntos de transacciones EDIFACT) y, a continuación, vuelva a enviar el conjunto de transacciones.