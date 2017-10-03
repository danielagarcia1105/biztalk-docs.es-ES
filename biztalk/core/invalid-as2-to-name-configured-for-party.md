---
title: "AS2 no válido: nombre configurado para la entidad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a203e5f2-d1d9-433f-b2bb-d679bb8fea58
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c06adc5a459f7dfd05508312494555fb2651114
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-as2-to-name-configured-for-party"></a>Nombre AS2-To no válido configurado para Entidad
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|InvalidAS2ToNameConfiguredError|  
|Texto del mensaje|AS2 no válido: nombre configurado para la entidad: {0} valor: {1}|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que el codificador o descodificador de AS2 no pudo procesar el mensaje AS2 porque el valor del encabezado AS2-To configurado para la entidad identificada no se ajustaba a las especificaciones de AS2 RFC 4130.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el encabezado AS2-To configurado para la entidad se ajusta a las especificaciones de la sección 6.2 de AS2 RFC 4130.