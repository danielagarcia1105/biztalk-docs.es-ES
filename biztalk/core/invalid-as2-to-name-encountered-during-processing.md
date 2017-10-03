---
title: "AS2 no válido: nombre detectado durante el procesamiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84d848b5-b2a3-460d-85d4-c3576e4e3aaf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26d26b929d20cef05c0bb71023a30afa43229fca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-as2-to-name-encountered-during-processing"></a>Se encontró un nombre de AS2-To no válido durante el procesamiento
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|InvalidAS2ToNameEncounteredError|  
|Texto del mensaje|Se encontró un nombre de AS2-To no válido durante el procesamiento.  Valor: {0}|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque el valor del encabezado AS2-To no se ajustaba a las especificaciones de AS2 RFC 4130.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el encabezado AS2-To del mensaje entrante o saliente se ajusta a las especificaciones de la sección 6.2 de AS2 RFC 4130.