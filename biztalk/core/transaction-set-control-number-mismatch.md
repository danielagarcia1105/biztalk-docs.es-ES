---
title: Error de coincidencia de número de Control del conjunto de transacciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c4b0c3f-f3be-4c2c-8719-8e40aa7122b9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd80bac6a5c58306a8d9ca64748ddbb8cb2bc81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278084"
---
# <a name="transaction-set-control-number-mismatch"></a>El número de control de conjunto de transacciones no coincide.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12TsControlNumberMismatchDescription|  
|Texto del mensaje|El número de control de conjunto de transacciones no coincide.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI rechazó el conjunto de transacciones entrantes porque el número de control contenido en el campo SE02 del conjunto de transacciones no coincidió con el número de control en el campo ST02.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del conjunto de transacciones que cambie el número de control en el campo SE02 del conjunto de transacciones rechazado para que coincida con el número de control del campo ST02 y vuelva a enviar el intercambio.