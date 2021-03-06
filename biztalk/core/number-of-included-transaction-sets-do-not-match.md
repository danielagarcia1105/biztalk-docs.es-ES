---
title: Número de conjuntos de transacciones incluidos no coincide. | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db958803-4667-4558-81a6-70c62d6fe8bf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93d2f51abc20f9cb790d2e6df62443f428c03dc8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970109"
---
# <a name="number-of-included-transaction-sets-do-not-match"></a>El número de conjuntos de transacciones incluidos no coincide.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                           X12FaNumberOfTsMismatchDescription                           |
|  Texto del mensaje   |                    El número de conjuntos de transacciones incluidos no coincide.                    |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que el número de conjuntos de transacciones del grupo del intercambio X12 no es igual al número del finalizador de grupo (campo GE01). Esto tiene lugar cuando el intercambio se conserva y se suspende al producirse un error. (El mensaje de error no se envía si el intercambio se conserva y los conjuntos de transacciones se suspenden al producirse un error o bien si el intercambio se divide.)  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el número que aparece en el campo GE01 del finalizador de grupo es el mismo que el número de conjuntos de transacciones del intercambio y vuelva a enviar el intercambio.