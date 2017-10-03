---
title: "Identificador de conjunto de transacciones no válida o ausente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 282c8128-7d23-44e2-bf44-e90e52cb5fb1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f23f44587abf67e608cff79150d9633f1707ff2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="missing-or-invalid-transaction-set-identifier"></a>El identificador del conjunto de transacciones falta o no es válido
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|EfactTsMissingOrInvalidTsIdentiferDescription|  
|Texto del mensaje|El identificador del conjunto de transacciones falta o no es válido|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción o de envío no pudo procesar el intercambio EDIFACT porque el valor del identificador del conjunto de transacciones (en el campo UNH2.1) faltaba o contenía un valor no válido.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el intercambio tenga un valor para el campo UNH2.1. Compruebe que el valor de UNH2.1 es un designador de tipo de documento válido de uno o seis dígitos.