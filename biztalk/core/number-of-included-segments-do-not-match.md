---
title: Número de segmentos incluidos no coincide. | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c868de02-fda7-4d84-be50-2c08cde0450c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0d2b91ba8ddecfe4926cbc21834b239eedc4547
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009389"
---
# <a name="number-of-included-segments-do-not-match"></a>El número de segmentos incluidos no coincide.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                        X12TsIncludedSegCountMismatchDescription                        |
|  Texto del mensaje   |                        El número de segmentos incluidos no coincide.                        |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que el número de segmentos del conjunto de transacciones del intercambio X12 no es igual al número del finalizador del conjunto de transacciones (campo SE01). Esto tiene lugar cuando el intercambio se conserva y se suspende al producirse un error.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el número que aparece en el campo SE01 del finalizador de intercambio es el mismo que el número de segmentos del conjunto de transacciones y vuelva a enviar el intercambio.