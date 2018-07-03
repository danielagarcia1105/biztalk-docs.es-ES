---
title: No se puede repetir el componente porque no tiene un recuento de repetición no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 040d7ea4-60a9-495f-91d7-b5b868957e2d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30f71ebf1ef6c0b48876c27e3f5212be42548f9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998605"
---
# <a name="component-cannot-repeat-because-it-has-an-invalid-repetition-count"></a>El componente no puede repetirse. Recuento de repetición no válido
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                            SchemaCode118EInvalidRepetition                             |
|  Texto del mensaje   |           No se puede repetir el componente, tiene un recuento de repetición no válido de {0}           |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque un componente de elemento, elemento, segmento o bucle estaba repetido en el intercambio y el esquema no permite la repetición.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar este error, asegúrese de que el componente de elemento, el elemento, el segmento o el bucle no se repita en el intercambio, según requiere el esquema, y vuelva a enviar el mensaje.