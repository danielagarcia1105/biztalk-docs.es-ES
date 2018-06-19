---
title: El elemento tiene una estructura no válida | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb94843c-cd21-48e3-ba30-aed0518b4d78
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b825fb0d2f5b4fe985a2024b1c97e21f4308b58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278164"
---
# <a name="the-element-has-an-invalid-structure"></a>El elemento tiene una estructura no válida
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12NseStructurallyInvalidElementDescription|  
|Texto del mensaje|El elemento '{0}' tiene una estructura no válida.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante, o que la canalización de envío no pudo procesar el intercambio saliente, porque un elemento de datos no tenía la estructura que especifica el esquema aplicable.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, corrija la estructura del elemento de datos en el intercambio saliente o pida al remitente del intercambio que corrija la estructura del elemento de datos en el intercambio entrante, de modo que se ajuste al esquema de documento.