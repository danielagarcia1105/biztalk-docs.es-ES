---
title: "Número de control de ISA e IEA no coinciden con | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f9091ea-460b-464b-acd5-8dc0488b61e5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd2f86d767b6065a6aeaa02f887dc8b6bd056fbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="control-number-in-isa-and-iea-do-not-match"></a>El número de control de ISA e IEA no coinciden.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|-|  
|Texto del mensaje|El número de control de ISA e IEA no coinciden.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción AS2 no pudo procesar el intercambio entrante porque los números de control del intercambio contenidos en los campos ISA13 e IEA02 del intercambio no tienen el mismo valor.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que los números de control de intercambio contenido en los campos ISA13 e IEA02 del intercambio tienen el mismo valor y, a continuación, reenvíe el intercambio.