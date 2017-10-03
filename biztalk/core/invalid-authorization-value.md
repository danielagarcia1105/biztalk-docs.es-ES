---
title: "Valor de autorización no válido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70d0dd75-b045-4b67-ba23-78551493f074
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4e83d35e379babeedca783fa8eb00774ccf05ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-authorization-value"></a>Valor de autorización no válido.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12Ta1InvalidAuthorizationValueDescription|  
|Texto del mensaje|Valor de autorización no válido.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor de la información sobre autorización en ISA02 no se ajustaba al tipo de datos que especifica el esquema (X12_AN) o no tenía el número de dígitos que requiere el esquema (10). El esquema es X12ServiceSchema en BaseArtifacts.dll.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el valor del encabezado ISA02 se ajusta al tipo de datos de X12:AN y tiene 10 dígitos (con espacios finales) y vuelva a enviar el intercambio.