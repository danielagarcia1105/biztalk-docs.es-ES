---
title: Muy pocos elementos de datos encontrados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6eca6c1-73ee-4b9a-be84-461051eda963
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89d82a5015d2285437363f178f88c165e3ba6333
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984781"
---
# <a name="too-few-data-elements-found"></a>No se encontraron suficientes datos de elementos.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                        X12FeTooFewDataElementsFoundDescription                         |
|  Texto del mensaje   |                              No se encontraron suficientes datos de elementos.                               |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque un segmento del intercambio contenía menos elementos de datos de los que requería el esquema de documento o el esquema de servicio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del intercambio que se asegure de que los segmentos incluyan el número requerido de elementos de datos y vuelva a enviar el intercambio.