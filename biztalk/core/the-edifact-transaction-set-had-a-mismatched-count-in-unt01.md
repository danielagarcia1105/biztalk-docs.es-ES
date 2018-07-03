---
title: El conjunto de transacciones de Edifact tiene un recuento no coincidente UNT01 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2859274-78e8-4e16-92b7-c143da6da421
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717260f8e45298c19756707ed042b97ab6e207fb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016051"
---
# <a name="the-edifact-transaction-set-had-a-mismatched-count-in-unt01"></a>El recuento de UNT01 del conjunto de transacciones Edifact no coincide
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| Versión del producto |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    Identificador del evento     |                                                                  -                                                                  |
|  Origen del evento   |                       EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                        |
|    Componente    |                                                             Motor EDI                                                              |
|  Nombre simbólico  |                                                      EfactUnhUntCountMismatch                                                       |
|  Texto del mensaje   | El recuento de UNT01 del conjunto de transacciones Edifact no coincide. UNT01 era {0}, mientras que debería haber sido {1}. Se han realizado las correcciones necesarias. |
  
## <a name="explanation"></a>Explicación  
 Esta advertencia indica que el campo UNT01, que es el recuento de segmentos, no coincidía con el número de segmentos del conjunto de transacciones. O bien el valor de UNT01 ha cambiado o está dañado o se han agregado o eliminado segmentos una vez determinado el recuento. La canalización de envío restableció el campo UNT01 al número de segmentos correcto y, a continuación, envió el intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 No es necesario que el usuario realice ninguna acción.