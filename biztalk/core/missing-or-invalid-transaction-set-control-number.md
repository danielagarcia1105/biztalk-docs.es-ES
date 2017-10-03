---
title: "Número de control de conjunto de transacciones no válida o ausente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6064b974-e8cd-4486-abc2-010afe0d956e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e9448c9be2cd05c7f7d8c18c13730933c1b5824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="missing-or-invalid-transaction-set-control-number"></a>El número de control de conjunto de transacciones falta o no es válido.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12TsMissingOrInvalidTsControlNumberDescription|  
|Texto del mensaje|El número de control de conjunto de transacciones falta o no es válido.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción o de envío no pudo procesar el intercambio porque el valor del número de control del conjunto de transacciones (en el campo ST02) faltaba o contenía un valor no válido. El número de control del conjunto de transacciones debe ser un valor alfanumérico.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
1.  Asegúrese de que cada conjunto de transacciones tiene un número de control del conjunto de transacciones.  
  
2.  Asegúrese de que cada número de control del conjunto de transacciones es un valor alfanumérico.