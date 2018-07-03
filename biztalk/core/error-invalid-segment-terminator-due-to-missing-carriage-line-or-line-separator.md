---
title: El intercambio contenía un error estructural. Una causa probable es el terminador de segmento no válido debido a la falta de carro y de línea y- o avance de línea podría | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 035e37d5-d4a8-49d0-8d75-3bcf2426cac7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e1d3c90d69b3e482ac570538f5dcc6997a63aea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988773"
---
# <a name="the-interchange-had-structural-error-a-likely-cause-is-invalid-segment-terminator-due-to-missing-carriage-line-and-or-line-feed-seperators"></a>El intercambio contenía un error estructural. Una causa probable es el terminador de segmento no válido debido a la falta de carro y de línea y- o podría avance de línea
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                   |
| Versión del producto |                                                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                                               |
|    Identificador del evento     |                                                                                                                                           -                                                                                                                                           |
|  Origen del evento   |                                                                                                EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                 |
|    Componente    |                                                                                                                                      Motor EDI                                                                                                                                       |
|  Nombre simbólico  |                                                                                                                        EfactInterchangeStructuralErrorAfterUnb                                                                                                                        |
|  Texto del mensaje   | El intercambio con Id. '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía un error estructural. La causa probable podría ser un finalizador de segmento no válido debido a la ausencia de separadores de retorno de carro o avance de línea. La parte situada después del error se está suspendiendo. Consulte Cola de suspensión para obtener información detallada. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción, la canalización de envío o la orquestación por lotes no pudo procesar el intercambio EDIFACT porque un segmento del intercambio no tenía el terminador de segmento requerido. Para un intercambio entrante, los separadores se identifican en el segmento UNA o, si no está presente el segmento UNA, en la propiedad de canalización EfactDelimiters. Para un intercambio saliente, los separadores se identifican en la página Definición de segmento UNA del cuadro de diálogo Propiedades de EDI.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar este error, asegúrese de que todos los segmentos del intercambio tengan el terminador de segmento requerido y vuelva a enviar el intercambio.