---
title: "Número de control de grupo de GS y GE no coinciden con | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2419f61-2717-4347-a4be-54362330c7e3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05bb9e879e9a994215ba052fc3549d5bdb28e9fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="group-control-number-in-gs-and-ge-do-not-match"></a>El número de control de grupo de GS y GE no coinciden.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12FaControlNumberMismatchDescription|  
|Texto del mensaje|El número de control de grupo de GS y GE no coinciden.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio X12 entrante porque los números de control contenidos en los campos GS06 y GE02 del intercambio no tienen el mismo valor.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que los números de control de grupo contenidos en los campos GS06 y GE02 del intercambio tienen el mismo valor y, a continuación, reenvíe el intercambio.