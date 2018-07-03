---
title: El intercambio contenía un error estructural. La parte situada después del error se ha suspendido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9071825d-7b90-42bf-bcf9-2a15ae36086d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e77100200a4fb2eacb24c6745fcd17011231b991
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967309"
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a>El intercambio contenía un error estructural. La parte situada después del error se ha suspendido
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| Versión del producto |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    Identificador del evento     |                                                                                       -                                                                                        |
|  Origen del evento   |                                             EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                             |
|    Componente    |                                                                                   Motor EDI                                                                                   |
|  Nombre simbólico  |                                                                        EfactInterchangeStructuralError                                                                         |
|  Texto del mensaje   | El intercambio con Id. '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía un error estructural. La parte situada después del error se está suspendiendo. Consulte Cola de suspensión para obtener información detallada. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio EDIFACT entrante porque ha tenido lugar un error estructural en el intercambio. Esto se ha producido con un intercambio que se estaba conservando, con conjuntos de transacciones suspendidos debido al error. Como resultado de este error, el o los conjuntos de transacciones que incluían el error se han suspendido, pero el resto de los conjuntos de transacciones se han procesado como parte del lote conservado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del intercambio que corrija el error estructural y vuelva a enviar el intercambio.