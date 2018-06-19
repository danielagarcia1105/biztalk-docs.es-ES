---
title: 'AS2 no válido: nombre configurado para la entidad | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cde739bd-f6f7-4e4a-8f02-9a99e9d82fc9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c370476eeccc085783c761cefb41a52eead8e208
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256980"
---
# <a name="invalid-as2-from-name-configured-for-party"></a>Nombre AS2-From no válido configurado para Entidad
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|InvalidAS2FromNameConfiguredError|  
|Texto del mensaje|AS2 no válido: nombre configurado para la entidad: {0} valor: {1}|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que el codificador o descodificador de AS2 no pudo procesar el mensaje AS2 porque el valor del encabezado AS2-From configurado para la entidad identificada no se ajustaba a las especificaciones de AS2 RFC 4130.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el encabezado AS2-From configurado para la entidad se ajusta a las especificaciones de la sección 6.2 de AS2 RFC 4130 y vuelva a enviar el mensaje.