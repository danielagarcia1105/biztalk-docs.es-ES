---
title: Conjunto de transacciones no admitido | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ffe8528-f34f-4189-8ee6-4ae1afb50c92
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 751b4bdff008a191a2367faea62fa92b6c15011b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-set-not-supported"></a>Conjunto de transacciones no admitido.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12TsNotSupportedDescription|  
|Texto del mensaje|Conjunto de transacciones no admitido.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque no se ha implementado ningún esquema de documento para el tipo de documento de dicho conjunto de transacciones.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] implemente un esquema de documento para el tipo de documento del conjunto de transacciones.