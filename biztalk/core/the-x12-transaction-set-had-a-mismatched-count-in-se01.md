---
title: El X12 conjunto de transacciones tiene un recuento que no coincide con SE01 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a90079f5-5939-40b6-9756-d7943240c125
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 947a557a81c6857b5d31f447acb2ec5a46cfcef9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993357"
---
# <a name="the-x12-transaction-set-had-a-mismatched-count-in-se01"></a>El conjunto de transacciones X12 tiene un recuento que no coincide con SE01
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                       |
| Versión del producto |                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                   |
|    Identificador del evento     |                                                               -                                                               |
|  Origen del evento   |                    EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
|    Componente    |                                                          Motor EDI                                                           |
|  Nombre simbólico  |                                                     X12StSeCountMismatch                                                      |
|  Texto del mensaje   | El conjunto de transacciones X12 tiene un recuento que no coincide con SE01. SE01 era {0}, mientras que debería haber sido {1}. Se han realizado las correcciones necesarias. |
  
## <a name="explanation"></a>Explicación  
 Esta advertencia indica que el número que aparece en el finalizador del conjunto de transacciones (campo SE01) no coincidía con el número de segmentos del conjunto de transacciones del intercambio. La canalización de envío corrige el recuento del campo SE01 y expone la advertencia.  
  
## <a name="user-action"></a>Acción del usuario  
 No se requiere ninguna acción.