---
title: El segmento UNA no es válido. No contenía 6 campos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c939d8d3-e6fb-4505-836d-31559fc5f1a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00d2a66e414bfe41e03c1e096034a620369064b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286404"
---
# <a name="una-segment-is-invalid-it-did-not-contain-6-fields"></a>El segmento UNA no es válido. No contenía 6 campos.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|UnaDidNotContainSixDelimiters|  
|Texto del mensaje|El segmento UNA no es válido. No contenía 6 campos.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio EDIFACT entrante porque el segmento UNA contenía menos de seis elementos de datos.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del intercambio que se asegure de que el segmento UNA contiene seis elementos de datos y vuelva a enviar el intercambio.