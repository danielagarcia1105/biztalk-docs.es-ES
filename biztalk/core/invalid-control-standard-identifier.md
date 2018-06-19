---
title: Identificador de estándar de Control no válido. | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d2b5a54-7f29-49c9-8bcf-a5b4b6d07ad3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94975e63d5781200ee1bfd9d14896c1e5fe722a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257020"
---
# <a name="invalid-control-standard-identifier"></a>Identificador de estándar de control no válido.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12Ta1InvalidControlStandardIdentifierDescription|  
|Texto del mensaje|Identificador de estándar de control no válido.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del identificador de estándar de control de intercambio (campo ISA11) del intercambio no coincidía con una entrada en la enumeración que especifica el esquema. El esquema es X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el identificador de estándar de control de intercambio usado en el intercambio coincide con una entrada en la enumeración para el campo ISA11 y, a continuación, reenvíe el intercambio.